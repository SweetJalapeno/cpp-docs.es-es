---
title: Compilador advertencia (nivel 3) C4534 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b765f5f654c8d533b0ae22d874e7657cd10d667
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4534"></a>Advertencia del compilador (nivel 3) C4534
'constructor' no será un constructor predeterminado para la clase 'class' debido al argumento predeterminado  
  
 Una clase no administrada puede tener un constructor con parámetros que tienen valores predeterminados y el compilador lo utilizará como el constructor predeterminado. Una clase marcada con el `value` palabra clave no usará un constructor con valores predeterminados para sus parámetros como un constructor predeterminado.  
  
 Para obtener más información, consulte [clases y Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 El ejemplo siguiente genera C4534:  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```