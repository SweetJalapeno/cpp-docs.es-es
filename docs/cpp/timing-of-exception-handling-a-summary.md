---
title: 'Control de tiempo de control de excepciones: un resumen | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 446925b6e00f4771229357effee0707af3fae52a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="timing-of-exception-handling-a-summary"></a>Intervalos de control de excepciones: resumen
Los controladores de terminación se ejecutan independientemente de cómo finalice el bloque de instrucciones `__try`. La terminación se puede producir cuando se sale del bloque `__try`, cuando una instrucción `longjmp` transfiere el control fuera del bloque y cuando se desenreda la pila debido al control de excepciones.  
  
> [!NOTE]
>  Visual C++ admite dos versiones de las instrucciones `setjmp` y `longjmp`. La versión rápida omite el control de terminación pero es más eficaz. Para usar esta versión, incluya el archivo \<setjmp.h >. La otra versión admite el control de terminación como se describe en el párrafo anterior. Para usar esta versión, incluya el archivo \<setjmpex.h >. El aumento del rendimiento de la versión rápida depende de la configuración de hardware.  
  
 El sistema operativo ejecuta todos los controladores de terminación en el orden adecuado antes de que cualquier otro código pueda ejecutarlos, incluido el cuerpo de un controlador de excepciones.  
  
 Cuando la causa de la interrupción es una excepción, el sistema debe ejecutar primero la parte del filtro de uno o varios controladores de excepciones antes de decidir qué debe terminar. El orden de los eventos es:  
  
1.  Se produce una excepción.  
  
2.  El sistema busca en la jerarquía de controladores de excepciones activos y ejecuta el filtro del controlador de mayor prioridad, que es el controlador de excepciones instalado más recientemente y más profundamente anidado, en términos de bloques y llamadas de función.  
  
3.  Si este filtro pasa el control (devuelve 0), el proceso continúa hasta que se encuentra un filtro que no pase el control.  
  
4.  Si este filtro devuelve -1, la ejecución continúa donde se produjo la excepción y realiza sin terminación.  
  
5.  Si el filtro devuelve 1, se producen los eventos siguientes:  
  
    -   El sistema desenreda la pila, borrando todos los marcos de pila entre el código que se está ejecutando actualmente (donde se produjo la excepción) y el marco de pila que contiene el controlador de excepciones que obtiene el control.  
  
    -   Cuando se desenreda la pila, se ejecuta cada controlador de terminación de la pila.  
  
    -   Se ejecuta el propio controlador de excepciones.  
  
    -   El control se pasa a la línea de código después del final de este controlador de excepciones.  
  
## <a name="see-also"></a>Vea también  
 [Escribir un controlador de terminación](../cpp/writing-a-termination-handler.md)   
 [Control de excepciones estructurado (C/C++)](../cpp/structured-exception-handling-c-cpp.md)