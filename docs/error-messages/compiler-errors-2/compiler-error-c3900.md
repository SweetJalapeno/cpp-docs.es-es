---
title: Error del compilador C3900 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3900
dev_langs:
- C++
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc940d174edc337422818bc233c1ef9952b66276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3900"></a>Error del compilador C3900
'member': no se permite en el ámbito actual  
  
 Bloques de propiedades pueden contener declaraciones de función y definiciones de funciones insertadas solo. No hay miembros que no son de se permiten en bloques de propiedades. Se permiten sin definiciones de tipos, operadores ni funciones friend. Para obtener más información, consulta [property](../../windows/property-cpp-component-extensions.md).  
  
 Las definiciones de eventos sólo pueden contener las funciones y métodos de acceso.  
  
 El ejemplo siguiente genera C3900:  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 El ejemplo siguiente genera C3900:  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```