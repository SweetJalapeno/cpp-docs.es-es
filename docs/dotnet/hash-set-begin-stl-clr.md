---
title: 'hash_set:: begin (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::begin
dev_langs:
- C++
helpviewer_keywords:
- begin member [STL/CLR]
ms.assetid: 1bd02b6b-0e24-4f42-ad13-fd7776f7f811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57be3862ca30187af409c013a8e7669a2c43e80b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hashsetbegin-stlclr"></a>hash_set::begin (STL/CLR)
Designa el principio de la secuencia controlada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>Comentarios  
 La función miembro devuelve un iterador bidireccional que designa el primer elemento de la secuencia controlada o más allá del final de una secuencia vacía. Utilícelo para obtener un iterador que designa el `current` a partir de la secuencia controlada, pero su estado puede cambiar si cambia la longitud de la secuencia controlada.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_hash_set_begin.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
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
  
// inspect first two items   
    Myhash_set::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)