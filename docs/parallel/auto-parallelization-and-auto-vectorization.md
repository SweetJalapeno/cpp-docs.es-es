---
title: Paralelización y vectorización automática | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1ec19065647f78b4d9b2665003c0aa3a2795ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Paralelización y vectorización automáticas
El paralelizador automático y el vectorizador automático se han diseñado para proporcionar mejoras automáticas de rendimiento de los bucles en el código.  
  
## <a name="auto-parallelizer"></a>Paralelizador automático  
 El [/Qpar](../build/reference/qpar-auto-parallelizer.md) modificador del compilador permite *paralelización automática* de bucles en el código. Cuando se especifica este marcador sin cambiar el código existente, el compilador evalúa el código para buscar los bucles que podrían beneficiarse de la paralelización. Dado que podría encontrar bucles que no hacen mucho trabajo y, por tanto, no se beneficiarán de la paralelización, y debido a que cada paralelización innecesaria puede acaparar un grupo de subprocesos o producir sincronización adicional u otro procesamiento que tendería a disminuir el rendimiento en lugar de mejorarlo, el compilador es conservador en la selección de los bucles que ejecuta en paralelo. Por ejemplo, considere el siguiente ejemplo en el que el límite superior del bucle no se conoce en tiempo de compilación:  
  
```cpp  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Dado que `u` puede ser un valor pequeño, el compilador no paralelizará automáticamente este bucle. Sin embargo, es posible que el usuario todavía desee paralelizarlo porque sabe que `u` siempre será grande. Para habilitar la paralelización automática, especifique [#pragma loop(hint_parallel(n))](../preprocessor/loop.md), donde `n` es el número de subprocesos en paralelo para paralelizar a través de. En el ejemplo siguiente, el compilador intentará paralelizar el bucle entre 8 subprocesos.  
  
```cpp  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Al igual que con todos los [directivas pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md), la sintaxis de la directiva pragma alternativa `__pragma(loop(hint_parallel(n)))` también se admite.  
  
 Hay algunos bucles que el compilador no puede paralelizar aunque lo desee. Por ejemplo:  
  
```cpp  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 La función `upper_bound()` puede cambiar cada vez que se la llama. Dado que el límite superior no puede conocerse, el compilador puede emitir un mensaje de diagnóstico que explica por qué no se puede paralelizar este bucle. En el ejemplo siguiente se muestra un bucle que se puede paralelizar, un bucle que no se puede paralelizar, la sintaxis del compilador que se usa en el símbolo del sistema y la salida del compilador para cada opción de línea de comandos:  
  
```cpp  
int A[1000];  
void test() {  
#pragma loop(hint_parallel(0))  
    for (int i=0; i<1000; ++i) {  
        A[i] = A[i] + 1;  
    }  
  
    for (int i=1000; i<2000; ++i) {  
        A[i] = A[i] + 1;  
    }  
}  
  
```  
  
 La compilación con este comando:  
  
 **CL d:\myproject\mylooptest.cpp/O2 /Qpar /Qpar-report: 1**  
  
 produce este resultado:  
  
 **---Analizar la función: void __cdecl test(void)**   
 **d:\myproject\mytest.cpp(4): bucle paralelizado**  
  
 La compilación con este comando:  
  
 **CL d:\myproject\mylooptest.cpp/O2 /Qpar /Qpar-report: 2**  
  
 produce este resultado:  
  
 **---Analizar la función: void __cdecl test(void)**   
 **d:\myproject\mytest.cpp(4): bucle paralelizado**   
 **d:\myproject\mytest.cpp(4): bucle no paralelizado por el motivo '1008'**  
  
 Observe la diferencia en la salida de las dos [/qpar-Report (nivel de información de Paralelizador automático)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) opciones. **/ Qpar-report: 1** genera mensajes del paralelizador solo para los bucles que se paralelizan correctamente. **/ Qpar-report: 2** genera mensajes del paralelizador para las paralelizaciones de bucles correctas e incorrectas.  
  
 Para obtener más información sobre los códigos de motivo y mensajes, vea [mensajes del Vectorizador y Paralelizador](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
## <a name="auto-vectorizer"></a>Vectorizador automático  
 El vectorizador automático analiza los bucles del código y usa los registros y las instrucciones de vector en el equipo de destino para ejecutarlos si puede. Esto puede mejorar el rendimiento del código. El compilador tiene como destino las instrucciones SSE2, AVX y AVX2 en procesadores Intel o AMD, o en las instrucciones NEON en procesadores ARM, según la [/arch](../build/reference/arch-minimum-cpu-architecture.md) cambiar.  
  
 El Vectorizador automático puede generar instrucciones diferentes de las que especifica la **/arch** cambiar. Estas instrucciones estarán protegidas por una comprobación en tiempo de ejecución para asegurarse de que código se ejecuta correctamente. Por ejemplo, cuando se compila **/arch: SSE2**, se pueden emitir instrucciones SSE4.2. Una comprobación en tiempo de ejecución comprueba que SSE4.2 está disponible en el procesador de destino y salta a una versión no SSE4.2 del bucle si el procesador no admite las instrucciones.  
  
 De forma predeterminada, se habilita el vectorizador automático. Si desea comparar el rendimiento del código sometido a la vectorización, puede usar [#pragma Loop (no_vector)](../preprocessor/loop.md) para deshabilitar la vectorización de un bucle concreto.  
  
```  
  
      #pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 Al igual que con todos los [directivas pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md), la sintaxis de la directiva pragma alternativa `__pragma(loop(no_vector))` también se admite.  
  
 Como con el Paralelizador automático, puede especificar el [/Qvec-report (nivel de información de Vectorizador automático)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) opción de línea de comandos para notificar correctamente solo los bucles vectorizados:**/Qvec-report: 1**: o tanto correcta e incorrectamente los bucles vectorizados:**/Qvec-report: 2**).  
  
 Para obtener más información sobre los códigos de motivo y mensajes, vea [mensajes del Vectorizador y Paralelizador](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
 Para obtener un ejemplo que muestra cómo funciona el vectorizador en la práctica, consulte [proyecto Austin, parte 2 de 6: volver una página](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)  
  
## <a name="see-also"></a>Vea también  
 [bucle](../preprocessor/loop.md)   
 [Programación paralela en código nativo](http://go.microsoft.com/fwlink/p/?linkid=263662)   
 [/Qpar (Paralelizador automático)](../build/reference/qpar-auto-parallelizer.md)   
 [/ Qpar-informe (Paralelizador automático Reporting nivel)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [/ Qvec-informe (Vectorizador automático Reporting nivel)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [Mensajes del vectorizador y paralelizador](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)