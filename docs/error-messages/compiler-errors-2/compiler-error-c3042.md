---
title: Error del compilador C3042 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3042
dev_langs:
- C++
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32d2f88702bb3c1c2439dd2931ee269c9c1413ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3042"></a>Error del compilador C3042
Las cláusulas 'copyprivate' y 'nowait' no pueden aparecer juntas en la directiva 'directive' de OpenMP  
  
 Las cláusulas [copyprivate](../../parallel/openmp/reference/copyprivate.md) y [nowait](../../parallel/openmp/reference/nowait.md) son mutuamente excluyentes en la directiva especificada. Para corregir este error, quite una de las cláusulas `copyprivate` o `nowait` , o bien ambas.  
  
 El ejemplo siguiente genera la advertencia C3042:  
  
```  
// C3042.cpp  
// compile with: /openmp /c  
#include <stdio.h>  
#include "omp.h"  
  
double d;  
  
int main() {  
    #pragma omp parallel private(d)  
   {  
      #pragma omp single copyprivate(d) nowait   // C3042  
      {  
      }  
   }  
}  
```