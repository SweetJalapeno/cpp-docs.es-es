---
title: C2032 de Error del compilador | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1db268222f3b9f7ca6f9ce297680866185e6661d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2032"></a>C2032 de Error del compilador
'identificador': función no puede ser miembro de 'estructuraounión' struct/union  
  
 La estructura o unión tiene una función miembro, que se admite en C++, pero no en C. Para resolver el error, compile como un programa de C++ o quite la función miembro.  
  
 El ejemplo siguiente genera C2032:  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Posible resolución:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```