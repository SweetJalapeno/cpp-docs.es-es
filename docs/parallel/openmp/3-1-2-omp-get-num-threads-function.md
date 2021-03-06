---
title: 3.1.2 omp_get_num_threads (función) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df01d571b67ff6d252d85128fcc8c1d26a6e94a9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads (Función)
El **omp_get_num_threads ()** función devuelve el número de subprocesos actualmente en el equipo que ejecuta la región paralela desde el que se llama. El formato es como se detalla a continuación:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 El **num_threads** cláusula, el **omp_set_num_threads ()** función y el **OMP_NUM_THREADS** variable de entorno controlan el número de subprocesos en un equipo.  
  
 Si el número de subprocesos no se ha establecido explícitamente por el usuario, el valor predeterminado es definido por la implementación. Esta función se enlaza a los más próximo incluye **paralelo** directiva. Si se llama desde una serie parte de un programa, o de una región paralela anidada que se serializa, esta función devuelve 1.  
  
## <a name="cross-references"></a>Referencias cruzadas:  
  
-   **OMP_NUM_THREADS** vea variable de entorno [sección 4.2](../../parallel/openmp/4-2-omp-num-threads.md) en página 48.  
  
-   **num_threads** cláusula, vea [sección 2.3](../../parallel/openmp/2-3-parallel-construct.md) en página 8.  
  
-   **paralelo** construir, consulte [sección 2.3](../../parallel/openmp/2-3-parallel-construct.md) en página 8.