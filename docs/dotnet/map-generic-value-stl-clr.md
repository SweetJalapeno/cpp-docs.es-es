---
title: Map::generic_value (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::generic_value
dev_langs:
- C++
helpviewer_keywords:
- generic_value member [STL/CLR]
ms.assetid: bd42ec86-fb9e-4c0d-8cae-7187a8742a94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 319e4c890672d9725bfa6dfd2dbdd5cf9e0c025e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="mapgenericvalue-stlclr"></a>map::generic_value (STL/CLR)
El tipo de un elemento para su uso con la interfaz genérica para el contenedor.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo describe un objeto de tipo `GValue` que describe el valor del elemento almacenado para su uso con la interfaz genérica para esta clase de contenedor de plantilla.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_map_generic_value.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymap::generic_container^ gc1 = %c1;   
    for each (Mymap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymap::generic_iterator gcit = gc1->begin();   
    Mymap::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
[a 1]  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/mapa >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [asignar (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)   
 [Map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)   
 [map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)