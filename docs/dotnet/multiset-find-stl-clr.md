---
title: 'MULTISET:: Find (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: 162c9002-fb34-44f9-8e42-6bacecd0ebbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bd202b1ed73243f6f7135aced9ad2a8ec506d657
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="multisetfind-stlclr"></a>multiset::find (STL/CLR)
Busca un elemento que coincide con una clave especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parámetros  
 key  
 Valor de clave que se va a buscar.  
  
## <a name="remarks"></a>Comentarios  
 Si al menos un elemento de la secuencia controlada tiene una ordenación equivalente con `key`, la función miembro devuelve un iterador que designa uno de esos elementos; de lo contrario, devuelve [MULTISET:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `()`. Usa para buscar un elemento actualmente en la secuencia controlada que coincida con una clave especificada.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_multiset_find.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  
  
## <a name="description"></a>Descripción  
 Tenga en cuenta que `find` no garantiza que varios elemento que se encuentra.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [MULTISET (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [MULTISET:: equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)   
 [MULTISET:: lower_bound (STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md)   
 [multiset::upper_bound (STL/CLR)](../dotnet/multiset-upper-bound-stl-clr.md)