---
title: make_public | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27db5ac934973178e2485327090ed70f994becec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="makepublic"></a>make_public
Indica que un tipo nativo debe tener accesibilidad pública de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#pragma make_public(type)  
```  
  
### <a name="parameters"></a>Parámetros  
 `type` es el nombre del tipo que desea que tenga accesibilidad pública de ensamblado.  
  
## <a name="remarks"></a>Comentarios  
`make_public` es útil cuando el tipo nativo al que se desea hacer referencia es de un archivo .h que no se puede cambiar. Si desea usar el tipo nativo en signatura de una función pública en un tipo con visibilidad pública de ensamblado, el tipo nativo también debe tener accesibilidad pública de ensamblado o el compilador emitirá una advertencia.  
  
`make_public` debe especificarse en el ámbito global y solo tiene efecto desde el punto en el que se declara hasta el final del archivo de código fuente.  
  
El tipo nativo puede ser privado de forma implícita o explícita; vea [visibilidad de tipos](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) para obtener más información.  
  
## <a name="example"></a>Ejemplo  
El ejemplo siguiente es el contenido de un archivo .h que contiene las definiciones para dos structs nativos.  
  
```cpp  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## <a name="example"></a>Ejemplo  
El ejemplo de código siguiente utiliza el archivo de encabezado e indica que, a menos que marque explícitamente los structs nativos como públicos usando `make_public`, el compilador generará una advertencia cuando intente usar los structs nativos en la signatura de la función pública en un tipo administrado público.  
  
```cpp  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## <a name="see-also"></a>Vea también  
[Directivas pragma y la palabra clave __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)