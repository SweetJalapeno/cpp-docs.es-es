---
title: 'Vector:: Resize (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::resize
dev_langs:
- C++
helpviewer_keywords:
- resize member [STL/CLR]
ms.assetid: a3556fbc-67d9-463a-9ffc-cb43ee15657f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f7327b62906746ef3bb561d88f8c6ddc2134aa65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="vectorresize-stlclr"></a>vector::resize (STL/CLR)
Cambia el número de elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Parámetros  
 NEW_SIZE  
 Nuevo tamaño de la secuencia controlada.  
  
 Val  
 Valor del elemento de relleno.  
  
## <a name="remarks"></a>Comentarios  
 Las funciones de miembro tanto asegúrese de que [vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()` de ahora en adelante devuelve `new_size`. Si la secuencia controlada tiene que ser más larga, la primera función miembro anexa elementos con el valor `value_type()`, mientras que la segunda función miembro anexa elementos con el valor `val`. Para realizar la secuencia controlada más corta, ambas funciones miembro borrar eficazmente el último elemento [vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` veces. Úsela para asegurarse de que la secuencia controlada tiene tamaño `new_size`, recortar o relleno de la secuencia controlada actual.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector:: Clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)   
 [Vector:: Erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md)   
 [vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)