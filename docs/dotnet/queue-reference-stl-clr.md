---
title: Queue::Reference (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: cca05237-5b95-4cca-ac21-b786aa8a3c96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2627d7128944e6beee87eb0eef8fd00a38773314
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="queuereference-stlclr"></a>queue::reference (STL/CLR)
El tipo de una referencia a un elemento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo describe una referencia a un elemento.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_queue_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify back of queue and redisplay   
    Myqueue::reference ref = c1.back();   
    ref = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b x  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/cola >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [cola (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)   
 [queue::value_type (STL/CLR)](../dotnet/queue-value-type-stl-clr.md)