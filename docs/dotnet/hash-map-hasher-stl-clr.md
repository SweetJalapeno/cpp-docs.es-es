---
title: hash_map::hasher (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::hasher
dev_langs:
- C++
helpviewer_keywords:
- hasher member [STL/CLR]
ms.assetid: 72e4c4c9-ea35-4f75-98bb-e53979706de1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fbdad394797de47a9f1ea46a5ca4a100cb80f76d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashmaphasher-stlclr"></a>hash_map::hasher (STL/CLR)
El delegado de hash para una clave.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>  
    hasher;  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo describe a un delegado que convierte un valor de clave en un entero.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_map_hasher.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 1616896120  
hash(L'b') = 570892832  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::hash_delegate (STL/CLR)](../dotnet/hash-map-hash-delegate-stl-clr.md)