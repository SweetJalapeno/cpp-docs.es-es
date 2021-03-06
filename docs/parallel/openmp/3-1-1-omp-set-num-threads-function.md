---
title: 3.1.1 omp_set_num_threads (función) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99c82ff324cbf21612d2459511877d152e2757f5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads (Función)
El `omp_set_num_threads` función establece el número predeterminado de subprocesos que se utilizarán para posteriores regiones en paralelo que no especifican un `num_threads` cláusula. El formato es como se detalla a continuación:  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 El valor del parámetro *num_threads* debe ser un entero positivo. Su efecto depende de si está habilitado el ajuste dinámico del número de subprocesos. Para un conjunto completo de reglas sobre la interacción entre el `omp_set_num_threads` función y realizar un ajuste dinámico de subprocesos, vea la sección 2.3 en página 8.  
  
 Esta función tiene los efectos que se ha descrito anteriormente, cuando se llama desde una parte del programa donde la `omp_in_parallel` función devuelve cero. Si se llama desde una parte del programa donde la `omp_in_parallel` función devuelve un valor distinto de cero, el comportamiento de esta función es indefinido.  
  
 Esta llamada tiene prioridad sobre la `OMP_NUM_THREADS` variable de entorno. El valor predeterminado para el número de subprocesos, lo que puede establecerse mediante una llamada a `omp_set_num_threads` o estableciendo la `OMP_NUM_THREADS` variable de entorno, se pueden reemplazar explícitamente en un único servidor **paralelo** directiva mediante la especificación de la `num_threads` cláusula.  
  
## <a name="cross-references"></a>Referencias cruzadas:  
  
-   `omp_set_dynamic` función, vea [sección 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) en página 39.  
  
-   `omp_get_dynamic` función, vea [sección 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) en la página 40.  
  
-   `OMP_NUM_THREADS` vea de variable de entorno [sección 4.2](../../parallel/openmp/4-2-omp-num-threads.md) en página 48 y la sección 2.3 en página 8.  
  
-   `num_threads` cláusula, vea [sección 2.3](../../parallel/openmp/2-3-parallel-construct.md) en página 8