---
title: Error del compilador C3071 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 163cb170953c444789e39b906ff4d408739f7514
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3071"></a>Error del compilador C3071
El operador 'operador' solamente se puede aplicar a una instancia de una clase ref o a un tipo de valor.  
  
 Un operador CLR no se puede usar en un tipo nativo. El operador puede usarse en una clase ref o un struct ref (un tipo de valor), pero no en un tipo nativo como int ni en un alias para un tipo nativo como System::Int32. A estos tipos no se les puede aplicar la conversión boxing desde código C++ para que hagan referencia a la variable nativa y, por tanto, no se puede usar el operador.  
  
 Para obtener más información, consulte [operador de referencia de seguimiento](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera el error C3071.  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```