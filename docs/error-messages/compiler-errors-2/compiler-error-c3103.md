---
title: C3103 de Error del compilador | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3103
dev_langs:
- C++
helpviewer_keywords:
- C3103
ms.assetid: 7984bd3e-d51d-43e4-b6f4-08c1e9fb9704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d20fae5584c9d410c8aade1722497c9010c83f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3103"></a>C3103 de Error del compilador
'argumento': argumento con nombre repetido  
  
 Un atributo no puede repetir argumentos con nombre.  
  
 Para obtener más información, consulte [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera C3103.  
  
```  
// C3103.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref class Attr : public Attribute {  
public:  
   int m_t;  
};  
  
[Attr(m_t = 10, m_t = 1)]   // C3103  
// try the following line instead  
// [Attr(m_t = 10)]  
ref class A {};  
```