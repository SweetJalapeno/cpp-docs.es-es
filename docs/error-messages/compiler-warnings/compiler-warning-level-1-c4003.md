---
title: Compilador (nivel 1) de la advertencia C4003 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a90202bfc06d50089e2ac283a5060bc431b9549c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4003"></a>Compilador C4003 de advertencia (nivel 1)
no hay suficientes parámetros reales para la macro 'identificador'  
  
 El número de parámetros formales de la definición de macro supera el número de parámetros reales de la macro. Expansión de macro reemplaza el texto vacío para los parámetros que faltan.  
  
 El ejemplo siguiente genera C4003:  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```