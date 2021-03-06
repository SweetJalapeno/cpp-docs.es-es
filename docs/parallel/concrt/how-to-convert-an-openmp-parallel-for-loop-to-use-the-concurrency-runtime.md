---
title: 'Cómo: convertir un bucle usar el Runtime de simultaneidad OpenMP paralelo | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93538e3188f0086039ecc0b681f936954d82ae97
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Cómo: Convertir un bucle OpenMP paralelo para usar el runtime de simultaneidad

En este ejemplo se muestra cómo convertir un bucle básico que usa el OpenMP [paralelo](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) y [para](../../parallel/openmp/reference/for-openmp.md) directivas para usar el Runtime de simultaneidad [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usan OpenMP y el runtime de simultaneidad para calcular el contador de números primos en una matriz de valores aleatorios.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 Este ejemplo produce el siguiente resultado:  
  
```Output  
Using OpenMP...  
found 107254 prime numbers.  
Using the Concurrency Runtime...  
found 107254 prime numbers.  
```  
  
 El algoritmo `parallel_for` y OpenMP 3.0 permiten que el tipo de índice sea un tipo entero con signo o un tipo entero sin signo. El algoritmo `parallel_for` también se asegura de que el intervalo especificado no desborde un tipo con signo. Las versiones 2.0 y 2.5 de OpenMP solo permiten los tipos enteros de índice con signo. Además, OpenMP no valida el intervalo de índices.  
  
 La versión de este ejemplo se usa el Runtime de simultaneidad también utiliza un [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) objeto en lugar de la [atómica](../../parallel/openmp/reference/atomic.md) directiva para incrementar el valor del contador sin necesidad de sincronización.  
  
 Para obtener más información acerca de `parallel_for` y otros algoritmos paralelos, vea [algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md). Para obtener más información sobre la `combinable` de clases, consulte [contenedores y objetos paralelos](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="example"></a>Ejemplo  

 Este ejemplo modifica el ejemplo anterior para actuar sobre un [std:: Array](../../standard-library/array-class-stl.md) en lugar del objeto en una matriz nativa. Porque permite que las versiones 2.0 y 2.5 de OpenMP para firmados solo en tipos de índice entero un `parallel_for` construcción, no se puede usar iteradores para tener acceso a los elementos de un contenedor de la biblioteca estándar de C++ en paralelo. Parallel Patterns Library (PPL) proporciona el [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmo, que lleva a cabo las tareas, en paralelo, en un contenedor iterativo como los proporcionados por la biblioteca estándar de C++. Usa la misma lógica de creación de particiones que el algoritmo `parallel_for`. El `parallel_for_each` algoritmo es similar a la biblioteca estándar de C++ [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmo, salvo que la `parallel_for_each` algoritmo ejecuta las tareas de forma simultánea.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o péguelo en un archivo denominado `concrt-omp-count-primes.cpp` y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 **cl.exe/EHsc/OpenMP concrt-omp-count-primes.cpp**  
  
## <a name="see-also"></a>Vea también  
 [Migrar de OpenMP al Runtime de simultaneidad](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md)   
 [Contenedores y objetos paralelos](../../parallel/concrt/parallel-containers-and-objects.md)

