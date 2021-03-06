---
title: collection_adapter::Size (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 71866719-9e29-4572-bfb9-60321f2937c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b2e8ae7183d54badfcd379f059efd21cd7f63f1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="collectionadaptersize-stlclr"></a>collection_adapter::size (STL/CLR)
Cuenta el número de elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Comentarios  
 La función miembro devuelve la longitud de la secuencia controlada. No está definido en una especialización para `IEnumerable` o `IEnumerable<Value>`.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/adaptador >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)