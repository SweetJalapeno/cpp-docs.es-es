---
title: 'multimap:: KEY_TYPE (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::key_type
dev_langs:
- C++
helpviewer_keywords:
- key_type member [STL/CLR]
ms.assetid: e6de1714-6e68-4f64-a2aa-a2571059bd59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 80e4ea26757795dc24123787fe8248fa45adec83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="multimapkeytype-stlclr"></a>multimap::key_type (STL/CLR)
El tipo de una clave de ordenación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef Key key_type;  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo es un sinónimo del parámetro de plantilla `Key`.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_multimap_key_type.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using key_type   
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Mymultimap::key_type val = it->first;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/mapa >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap:: key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)   
 [multimap:: mapped_type (STL/CLR)](../dotnet/multimap-mapped-type-stl-clr.md)   
 [multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)