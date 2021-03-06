---
title: omp_test_lock | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_test_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_test_lock OpenMP function
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4bb63974f5d1864fe7b1c6359f7e8bda19b90c2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="omptestlock"></a>omp_test_lock
Intenta establecer un bloqueo, pero no impide la ejecución de subprocesos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Comentarios  
 donde,  
  
 `lock`  
 Una variable de tipo [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) que se inicializó con [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [3.2.5 omp_test_lock y omp_test_nest_lock funciones](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).  
  
## <a name="example"></a>Ejemplo  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
```Output  
Thread 1 - acquired simple_lock  
Thread 1 - released simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 2 - acquired simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 2 - released simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - acquired simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - released simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 3 - acquired simple_lock  
Thread 3 - released simple_lock  
```  
  
## <a name="see-also"></a>Vea también  
 [Funciones](../../../parallel/openmp/reference/openmp-functions.md)