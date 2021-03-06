---
title: 3.1.9 omp_set_nested (función) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df08d6eb1a93ff5852c239757d5f917e9777919b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested (Función)
El **omp_set_nested ()** función habilita o deshabilita el paralelismo anidado. El formato es como se detalla a continuación:  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 Si *anidada* se evalúa como 0, anidada paralelismo está deshabilitado, que es el valor predeterminado y regiones anidadas en paralelo se serialice y se ejecuta en el subproceso actual. Si *anidada* evalúa en un valor distinto de cero, se habilita el paralelismo anidado y regiones en paralelo que están anidadas pueden implementar subprocesos adicionales para formar equipos anidados.  
  
 Esta función tiene los efectos que se ha descrito anteriormente, cuando se llama desde una parte del programa donde la **omp_in_parallel ()** función devuelve cero. Si se llama desde una parte del programa donde la **omp_in_parallel ()** función devuelve un valor distinto de cero, el comportamiento de esta función es indefinido.  
  
 Esta llamada tiene prioridad sobre la **OMP_NESTED** variable de entorno.  
  
 Cuando se habilita el paralelismo anidado, el número de subprocesos utilizados para ejecutar regiones anidadas en paralelo es definido por la implementación. Como resultado, las implementaciones compatibles con OpenMP puedan serializar regiones anidadas en paralelo incluso cuando se habilita el paralelismo anidado.  
  
## <a name="cross-references"></a>Referencias cruzadas:  
  
-   **OMP_NESTED** vea variable de entorno [sección 4.4](../../parallel/openmp/4-4-omp-nested.md) en la página 49.  
  
-   **omp_in_parallel ()** función, vea [sección 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) en página 38.