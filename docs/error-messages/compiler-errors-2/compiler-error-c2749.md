---
title: C2749 de Error del compilador | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2749
dev_langs:
- C++
helpviewer_keywords:
- C2749
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1738bdcc66e05512932fcd9029484dc55e3fc4a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2749"></a>C2749 de Error del compilador
'type': solamente puede producir o detectar el identificador a una clase administrada con/CLR: safe  
  
 Cuando se usa **/CLR: safe**, solo se puede producir o detectar un tipo de referencia.  
  
 Para obtener más información, consulte [/clr (Compilación de Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera C2749:  
  
```  
// C2749.cpp  
// compile with: /clr:safe  
ref struct MyStruct {  
public:  
   int i;  
};  
  
int main() {  
   MyStruct ^x = gcnew MyStruct;  
  
   // Delete the following 4 lines to resolve.  
   try {   
      throw (1);   // C2749  
   }  
   catch(int){}  
  
   // OK  
   try {  
      throw (x);  
   }  
   catch(MyStruct ^){}   
}  
```