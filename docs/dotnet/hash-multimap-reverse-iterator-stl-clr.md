---
title: 'hash_multimap:: reverse_iterator (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- reverse_iterator member [STL/CLR]
ms.assetid: 000d3250-befa-4604-b042-11424cb179dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e651aeb4aae56e5f4b9281cc11d64b8e83e5da2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimapreverseiterator-stlclr"></a>hash_multimap::reverse_iterator (STL/CLR)
El tipo de un iterador invertido para la secuencia controlada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef T3 reverse_iterator;  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo describe un objeto de tipo no especificado `T3` que puede actuar como un iterador inverso de la secuencia controlada.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_multimap_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Myhash_multimap::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" [{0} {1}]", rit->first, rit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[c 3] [b 2] [a 1]  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: const_iterator (STL/CLR)](../dotnet/hash-multimap-const-iterator-stl-clr.md)   
 [hash_multimap:: const_reverse_iterator (STL/CLR)](../dotnet/hash-multimap-const-reverse-iterator-stl-clr.md)   
 [hash_multimap::iterator (STL/CLR)](../dotnet/hash-multimap-iterator-stl-clr.md)