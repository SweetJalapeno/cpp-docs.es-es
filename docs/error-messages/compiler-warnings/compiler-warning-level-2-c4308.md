---
title: Compilador advertencia (nivel 2) C4308 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4308
dev_langs:
- C++
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3daff15f8e6eee179f04fd466f3595af1154e035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4308"></a>Advertencia del compilador (nivel 2) C4308
constante integral negativa convertida a tipo sin signo  
  
 Una expresión convierte una constante entera negativa a un tipo sin signo. El resultado de la expresión es probablemente no tenga sentido.  
  
## <a name="example"></a>Ejemplo  
  
```  
// C4308.cpp  
// compile with: /W2  
unsigned int u = (-5 + 3U);   // C4308  
  
int main()  
{  
}  
```