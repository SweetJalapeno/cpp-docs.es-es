---
title: threadprivate | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e7edaa36f929750087e3c81f42204ff20e9f62
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="threadprivate"></a>threadprivate
Especifica que una variable privada a un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>Comentarios  
 donde,  
  
 `var`  
 Una lista separada por comas de variables que desea convertir en privado a un subproceso. `var` debe ser una variable global o espacio de nombres de ámbito o una variable local estática.  
  
## <a name="remarks"></a>Comentarios  
 El `threadprivate` directiva es compatible con ningún cláusulas de OpenMP.  
  
 Para obtener más información, consulte [2.7.1 threadprivate (directiva)](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 El `threadprivate` directiva se basa en el [subproceso](../../../cpp/thread.md) `__declspec` atributo; límites en **__declspec (Thread)** se aplican a `threadprivate`.  
  
 No se puede utilizar `threadprivate` en cualquier archivo DLL que se van a cargar a través de [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  Esto incluye archivos DLL que se cargan con [/DELAYLOAD (Retrasar importación de carga)](../../../build/reference/delayload-delay-load-import.md), que también utiliza **LoadLibrary**.  
  
 Puede usar `threadprivate` en un archivo DLL que se carga de forma estática al iniciarse el proceso.  
  
 Dado que `threadprivate` se basa en **__declspec (Thread)**, un `threadprivate` variable existirá en cualquier subproceso que se inicia en el proceso, no solo los subprocesos que forman parte de un equipo de subproceso generado por una región paralela.  Se trata de un detalle de implementación que desea tener en cuenta, ya que se pueden observar, por ejemplo, los constructores de una `threadprivate` llamada más a menudo, a continuación, espera al tipo definido por el usuario.  
  
 Un `threadprivate` no se garantiza que la variable de un tipo destructable tiene su destructor denominado.  Por ejemplo:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Los usuarios no tienen ningún control sobre cuándo se cerrará los subprocesos que constituyen la región paralela.  Si esos subprocesos existen cuando se cierra el proceso, los subprocesos no será informados acerca de la salida del proceso y el destructor no se llamará para `threaded_var` en cualquier subproceso excepto el que se cierra (aquí, el subproceso principal).  Por lo que el código no debería contar con la destrucción adecuada de `threadprivate` variables.  
  
## <a name="example"></a>Ejemplo  
 Para obtener un ejemplo del uso de `threadprivate`, consulte [privada](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Vea también  
 [Directivas](../../../parallel/openmp/reference/openmp-directives.md)