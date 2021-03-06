---
title: Compilador advertencia (nivel 1) C4401 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4401
dev_langs:
- C++
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8b8a7a2bced261bbff09422c3dfa6454061f636
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4401"></a>Advertencia del compilador (nivel 1) C4401
'campo de bits': miembro es el campo de bits  
  
 Código ensamblador en línea intenta obtener acceso a un miembro de campo de bits. Código ensamblador en línea no puede tener acceso a miembros de un campo de bits, por lo que se utiliza el último límite de empaquetado antes del miembro de campo de bits.  
  
 Para evitar esta advertencia, convierta el campo de bits al tipo apropiado antes de crear la referencia en el código de ensamblado alineado. El ejemplo siguiente genera C4401:  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```