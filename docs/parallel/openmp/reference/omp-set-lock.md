---
title: omp_set_lock | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_lock OpenMP function
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d905da37b6e3203fcf37611d7404fa2e4f9ea96
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="ompsetlock"></a>omp_set_lock
Bloques de ejecución del subproceso hasta que haya un bloqueo disponible.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void omp_set_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Comentarios  
 donde,  
  
 `lock`  
 Una variable de tipo [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) que se inicializó con [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [3.2.3 omp_set_lock y omp_set_nest_lock funciones](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).  
  
## <a name="examples"></a>Ejemplos  
 Vea [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) para obtener un ejemplo del uso de `omp_set_lock`.  
  
## <a name="see-also"></a>Vea también  
 [Funciones](../../../parallel/openmp/reference/openmp-functions.md)