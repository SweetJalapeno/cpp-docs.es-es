---
title: Error del compilador C2931 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2931
dev_langs:
- C++
helpviewer_keywords:
- C2931
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e5dd8db3d39ff8aec2084736483c4d325d81314
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2931"></a>Error del compilador C2931
'class': el identificador de clase de tipo redefinido como una función miembro de 'identifier'  
  
 No puede usar una clase genérica o de plantilla como una función miembro de otra clase.  
  
 Este error puede producirse si las llaves no coinciden como es debido.  
  
 El ejemplo siguiente genera la advertencia C2931:  
  
```  
// C2931.cpp  
// compile with: /c  
template<class T>   
struct TC { };   
struct MyStruct {  
   void TC<int>();   // C2931  
};  
  
struct TC2 { };   
struct MyStruct2 {  
   void TC2();  
};  
```  
  
 También se puede producir C2931 al usar genéricos:  
  
```  
// C2931b.cpp  
// compile with: /clr /c  
generic<class T> ref struct GC {};  
struct MyStruct {  
   void GC<int>();   // C2931  
   void GC2();   // OK  
};  
```