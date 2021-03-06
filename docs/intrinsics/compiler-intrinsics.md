---
title: Funciones intrínsecas del compilador | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c05a2843e5daff980d1c84d4d3f2185ac361144d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-intrinsics"></a>Intrínsecos del controlador
La mayoría de las funciones está recogida en bibliotecas, pero algunas funciones están incorporadas en el compilador (es decir, son intrínsecas). Estas se conocen como funciones intrínsecas o intrínsecos.  
  
## <a name="remarks"></a>Comentarios  
 Si una función es un intrínseco, el código de dicha función suele estar insertado, con lo que se evita la sobrecarga de una llamada de función y se emiten instrucciones de código máquina altamente eficientes para dicha función. Un intrínseco suele ser más rápido que el ensamblado en línea equivalente, ya que el optimizador tiene un conocimiento integrado de cómo se comportan numerosos intrínsecos, por lo que pueden estar disponibles algunas optimizaciones de las que no se dispone cuando se utiliza el código ensamblado en línea. Además, el optimizador puede expandir el intrínseco de forma diferente, alinear los búferes de forma diferente o realizar otros ajustes según el contexto y los argumentos de la llamada.  
  
 El uso de intrínsecos afecta a la portabilidad del código, ya que los intrínsecos que están disponibles en Visual C++ podrían no estar disponibles si el código se compila con otros compiladores, y algunos intrínsecos que podrían estar disponibles para ciertas arquitecturas de destino no están disponibles para todas las arquitecturas. Sin embargo, los intrínsecos son generalmente mucho más portátiles que el ensamblado en línea. Los intrínsecos son necesarios en las arquitecturas de 64 bits donde no se admite el ensamblado en línea.  
  
 Algunos intrínsecos, como `__assume` y `__ReadWriteBarrier`, proporcionan información al compilador, lo que afecta al comportamiento del optimizador.  
  
 Algunos intrínsecos están disponibles solo como tal, mientras que otros están disponibles en implementaciones de intrínseco y de función. Puede indicarle al compilador que utilice la implementación de intrínseco de dos maneras, en función de si desea habilitar solo funciones específicas o de si desea habilitar todos los intrínsecos. La primera manera consiste en usar `#pragma intrinsic(` *función intrínseca-nombre-lista*`)`. La directiva pragma puede utilizarse para especificar un solo intrínseco o varios intrínsecos separados por comas. El segundo consiste en usar la [/Oi (generar funciones intrínsecas)](../build/reference/oi-generate-intrinsic-functions.md) opción del compilador, que hace que todos los intrínsecos disponibles en una plataforma determinada. En **/Oi**, use `#pragma function(` *función intrínseca-nombre-lista* `)` para forzar una llamada de función que se utilizará en lugar de una función intrínseca. Si la documentación de un intrínseco específico da cuenta de que la rutina solo está disponible como función intrínseca, se utiliza la implementación de intrínseco independientemente de si **/Oi** o `#pragma intrinsic` se especifica. En todos los casos, **/Oi** o `#pragma intrinsic` permite, pero no fuerza al optimizador a usar la función intrínseca. El optimizador todavía puede llamar a la función.  
  
 Algunas funciones de biblioteca estándar de C o C++ están disponibles en las implementaciones de intrínseco de algunas arquitecturas. Al llamar a una función de CRT, se utiliza la implementación de intrínseco si **/Oi** se especifica en la línea de comandos.  
  
 Un archivo de encabezado \<intrin.h >, está disponible para declarar los prototipos las funciones intrínsecas comunes. Intrínsecos específicos del fabricante están disponibles en la \<immintrin.h > y \<ammintrin.h > archivos de encabezado. Además, algunos encabezados de Windows declaran funciones que se asignan a un intrínseco del compilador.  
  
 En las secciones siguientes se enumeran todos los intrínsecos que están disponibles en varias arquitecturas. Para obtener más información acerca de cómo funcionan los intrínsecos en un procesador de destino determinado, consulte la documentación de referencia del fabricante.  
  
-   [Intrínsecos ARM](../intrinsics/arm-intrinsics.md)  
  
-   [Lista de intrínsecos de x86](../intrinsics/x86-intrinsics-list.md)  
  
-   [Lista de intrínsecos de x64 (amd64)](../intrinsics/x64-amd64-intrinsics-list.md)  
  
-   [Intrínsecos disponibles en todas las arquitecturas](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [Lista alfabética de funciones intrínsecas](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## <a name="see-also"></a>Vea también  
 [Referencia del ensamblador de ARM](../assembler/arm/arm-assembler-reference.md)   
 [Referencia de Microsoft Macro Assembler](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [Palabras clave](../cpp/keywords-cpp.md)   
 [Referencia de la biblioteca en tiempo de ejecución de C](../c-runtime-library/c-run-time-library-reference.md)