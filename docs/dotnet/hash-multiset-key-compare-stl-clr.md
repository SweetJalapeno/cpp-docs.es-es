---
title: 'hash_multiset:: key_compare (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::key_compare
dev_langs:
- C++
helpviewer_keywords:
- key_compare member [STL/CLR]
ms.assetid: 7382d18b-3cac-4a93-98db-fab486a8d275
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9486cfedd9e4808cdb0de30d23d9ef6fc53846c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisetkeycompare-stlclr"></a>hash_multiset::key_compare (STL/CLR)
El delegado para dos claves de ordenación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo es un sinónimo para el delegado que determina el orden de sus argumentos de la claves.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_multiset_key_compare.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    Myhash_multiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myhash_multiset c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = True  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: key_comp (STL/CLR)](../dotnet/hash-multiset-key-comp-stl-clr.md)   
 [hash_multiset:: KEY_TYPE (STL/CLR)](../dotnet/hash-multiset-key-type-stl-clr.md)   
 [hash_multiset::value_compare (STL/CLR)](../dotnet/hash-multiset-value-compare-stl-clr.md)