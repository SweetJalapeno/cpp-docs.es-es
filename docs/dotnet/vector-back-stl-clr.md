---
title: 'Vector:: back (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::back
dev_langs:
- C++
helpviewer_keywords:
- back member [STL/CLR]
ms.assetid: 5edb3fcc-74c5-4f04-b8dd-edab49ba45a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a42e44f0eb04390200529148eb6917a4cb56be0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="vectorback-stlclr"></a>vector::back (STL/CLR)
Obtiene acceso al último elemento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
reference back();  
```  
  
## <a name="remarks"></a>Comentarios  
 La función miembro devuelve una referencia al último elemento de la secuencia controlada, que debe ser no está vacío. Usa para tener acceso al último elemento, cuando se sabe que existe.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_vector_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)   
 [Vector:: front (STL/CLR)](../dotnet/vector-front-stl-clr.md)   
 [vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)