---
title: 'hash_set:: equal_range (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range member [STL/CLR]
ms.assetid: 502af4c5-f71e-44cf-a180-21e9da4b50ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82d5d47e524b534c642738036d37024ee44dcdab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashsetequalrange-stlclr"></a>hash_set::equal_range (STL/CLR)
Busca el intervalo que coincide con una clave especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>Parámetros  
 key  
 Valor de clave que se va a buscar.  
  
## <a name="remarks"></a>Comentarios  
 La función miembro devuelve un par de iteradores `cliext::pair<iterator, iterator>(` [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md) `(key),` [hash_set:: upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)`(key))`. Usa para determinar el intervalo de elementos actualmente en la secuencia controlada que coinciden con una clave especificada.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_set_equal_range.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
typedef Myhash_set::pair_iter_iter Pairii;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: Count (STL/CLR)](../dotnet/hash-set-count-stl-clr.md)   
 [hash_set:: Find (STL/CLR)](../dotnet/hash-set-find-stl-clr.md)   
 [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)   
 [hash_set::upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)