---
title: hash_map::operator(STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator[] member [STL/CLR]
ms.assetid: b0b8c1bd-4250-447d-9c69-3f8c34e9b6af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 98644343e942940f86b1f41bcfef88145f93f4aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapoperatorstlclr"></a>hash_map::operator(STL/CLR)
Asigna una clave a su valor asignado asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
mapped_type operator[](key_type key);  
```  
  
#### <a name="parameters"></a>Parámetros  
 key  
 Valor de clave que se va a buscar.  
  
## <a name="remarks"></a>Comentarios  
 Las funciones miembro esfuerzos en el ámbito para buscar un elemento con una ordenación equivalente a `key`. Si lo encuentra, devuelve el valor asignado asociado; de lo contrario, inserta `value_type(key, mapped_type())` y devuelve los asociados (valor predeterminado) asigna el valor. Usarlo para buscar un valor asignado según su clave asociada, o para asegurarse de que existe una entrada para la clave si no se encuentra ninguno.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_map_operator_sub.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'A', c1[L'A']);   
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'b', c1[L'b']);   
  
// redisplay altered contents   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// alter mapped values and redisplay   
    c1[L'A'] = 10;   
    c1[L'c'] = 13;   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
c1[A] = 0  
c1[b] = 2  
 [a 1] [A 0] [b 2] [c 3]  
 [a 1] [A 10] [b 2] [c 13]  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map:: Find (STL/CLR)](../dotnet/hash-map-find-stl-clr.md)   
 [hash_map::insert (STL/CLR)](../dotnet/hash-map-insert-stl-clr.md)