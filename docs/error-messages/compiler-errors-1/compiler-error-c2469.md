---
title: Error del compilador C2469 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2469
dev_langs:
- C++
helpviewer_keywords:
- C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37decb55a2f24f7f29d28519e2f87eba90ff56bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2469"></a>Error del compilador C2469
'operator': no se puede asignar un objeto 'type'  
  
 Se pasó un tipo no válido a un operador.  
  
 El ejemplo siguiente genera la advertencia C2469:  
  
```  
// C2469.cpp  
int main() {  
   int *i = new void;   // C2469  
   int *i = new int;   // OK  
}  
```