---
title: 4.2 OMP_NUM_THREADS | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b4208d7fe7d453dd1f701d820a85fce5cd68ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
El **OMP_NUM_THREADS** variable de entorno establece el número predeterminado de subprocesos que se utilizarán durante la ejecución, a menos que dicho número se cambia explícitamente mediante una llamada a la **omp_set_num_threads ()** rutina de biblioteca o por explícito **num_threads** cláusula en una **paralelo** directiva.  
  
 El valor de la **OMP_NUM_THREADS** variable de entorno debe ser un entero positivo. Su efecto depende de si está habilitado el ajuste dinámico del número de subprocesos. Para un conjunto completo de reglas sobre la interacción entre el **OMP_NUM_THREADS** entorno ajuste variable y dinámico de subprocesos, vea la sección 2.3 en página 8.  
  
 Si se especifica ningún valor para el **OMP_NUM_THREADS** variable de entorno, o si el valor especificado no es un entero positivo, o si el valor es mayor que el número máximo de subprocesos que el sistema puede admitir, el número de subprocesos que se utilizarán está definido por la implementación.  
  
 Ejemplo:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>Referencias cruzadas:  
  
-   **num_threads** cláusula, vea [sección 2.3](../../parallel/openmp/2-3-parallel-construct.md) en página 8.  
  
-   **omp_set_num_threads ()** función, vea [punto 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) en la página 36.  
  
-   **omp_set_dynamic ()** función, vea [sección 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) en página 39.