---
title: Compilador advertencia (nivel 1) C4730 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 467d9fd04e2fef78d480fc4db1417b6e4c8d5641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4730"></a>Advertencia del compilador (nivel 1) C4730
'main': mezcla de _m64 y expresiones pueden derivar en código incorrecto de punto flotante  
  
 Una función usa [__m64](../../cpp/m64.md) y **float**/**doble** tipos. Dado que los registros MMX y punto flotante comparten el mismo físico registrar espacio (no se pueden usar simultáneamente), con `__m64` y **float**/**doble** tipos en el mismo función puede producir daños en los datos, lo que podría provocar una excepción.  
  
 Para utilizar de forma segura `__m64` tipos y tipos de punto flotante en la misma función, cada instrucción que usa uno de los tipos debe estar separado por el **_m_empty** (para MMX) o **_m_femms** (para 3DNow!) función intrínseca.  
  
 El ejemplo siguiente genera C4730:  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```