---
title: Compilador advertencia (nivel 1) C4376 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4376
dev_langs:
- C++
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 615faaaa586e60a32ce670cd554a8b0b1c157a25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4376"></a>Advertencia del compilador (nivel 1) C4376
el especificador de acceso 'especificador_antiguo:' ya no se admite: utilice 'especificador_nuevo:' en su lugar  
  
 Para obtener más información sobre cómo especificar la accesibilidad de los tipos y miembros en los metadatos, vea [escriba visibilidad](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) y [visibilidad de miembros](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) en [Cómo: definir y utilizar clases y Structs (C++ / CLI) ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera C4376.  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```