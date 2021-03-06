---
title: Error del compilador C3043 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3043
dev_langs:
- C++
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdbb8f3cf9a0e996bc6ace521cd2bdd8b5e5dcc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3043"></a>Error del compilador C3043
la directiva 'critical' de OpenMP no se puede anidar en una directiva 'critical' con el mismo nombre  
  
 Una directiva [critical](../../parallel/openmp/reference/critical.md) no se puede anidar en una directiva `critical` con el mismo nombre.  
  
 El ejemplo siguiente genera la advertencia C3043:  
  
```  
// C3043.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n1 = 1, n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp critical(MyTest)  
      {  
         ++n2;  
  
         #pragma omp critical(MyTest)   // C3043  
         // try the following line instead  
         // #pragma omp critical(MyTest2)  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```