---
title: Error del compilador C2571 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dea582cf5d1211d57eac94a7f70458a51542ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2571"></a>Error del compilador C2571
'función': función virtual no puede estar en la unión 'unión'  
  
 Se declara una unión con una función virtual. Puede declarar una función virtual solo en una clase o estructura.  Soluciones posibles:  
  
1.  Cambie la unión a una clase o estructura.  
  
2.  Hacer que la función no virtual.  
  
 El ejemplo siguiente genera C2571:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```