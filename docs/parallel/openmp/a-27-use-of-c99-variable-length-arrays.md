---
title: Uso A.27 de matrices de longitud Variable de C99 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96391aa7403a54160cb6ab83b9b28c1527a3e353
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="a27---use-of-c99-variable-length-arrays"></a>A.27 Uso de matrices de longitud variable C99
En el ejemplo siguiente se muestra cómo utilizar matrices de longitud Variable de C99 (VLAs) en un `firstprivate` directiva ([sección 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) en página 26).  
  
> [!NOTE]
>  Actualmente no se admiten matrices de longitud variable en Visual C++.  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```