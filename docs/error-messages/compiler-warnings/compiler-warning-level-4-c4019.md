---
title: Compilador advertencia (nivel 4) C4019 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4019
dev_langs:
- C++
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d015b5674ad8f64a68b86979ce93313fa098c867
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4019"></a>Advertencia del compilador (nivel 4) C4019
instrucción vacía en ámbito global  
  
 Un punto y coma en el ámbito global no está precedido por una instrucción.  
  
 Esta advertencia se puede corregir si se quita el punto y coma adicional.  
  
## <a name="example"></a>Ejemplo  
  
```  
// C4019.c  
// compile with: /Za /W4  
#define declint( varname ) int varname;  
declint( a );   // C4019, int a;;  
declint( b )   // OK, int b;  
  
int main()  
{  
}  
```