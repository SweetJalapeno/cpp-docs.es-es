---
title: 'hash_multimap:: rend (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: 7cbed963-7615-40bf-80f2-37b878a64453
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7978c0bba27b34997fdbd2500e578fdb785c2425
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimaprend-stlclr"></a>hash_multimap::rend (STL/CLR)
Designa el final de la secuencia controlada inversa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Comentarios  
 La función miembro devuelve un iterador inverso que apunta inmediatamente después del principio de la secuencia controlada. Por tanto, designa el `end` de la secuencia inversa. Utilícelo para obtener un iterador que designa el `current` final de la secuencia controlada mostrada en orden inverso, pero su estado puede cambiar si cambia la longitud de la secuencia controlada.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_multimap_rend.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_multimap::reverse_iterator rit = c1.rend();   
    --rit;   
    --rit;   
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*--rend() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*-- --rend() = [b 2]  
*--rend() = [a 1]  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md)   
 [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)   
 [hash_multimap::rbegin (STL/CLR)](../dotnet/hash-multimap-rbegin-stl-clr.md)