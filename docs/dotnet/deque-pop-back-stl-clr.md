---
title: 'deque:: pop_back (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::pop_back
dev_langs:
- C++
helpviewer_keywords:
- pop_back member [STL/CLR]
ms.assetid: 528d2c89-104c-45f7-8f05-41fe217ee37c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 74ee3030b203c66f63e87ac4a9725785078a7017
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dequepopback-stlclr"></a>deque::pop_back (STL/CLR)
Quita el último elemento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void pop_back();  
```  
  
## <a name="remarks"></a>Comentarios  
 La función miembro quita el último elemento de la secuencia controlada, que debe ser no está vacío. Se usar para acortar el deque por un elemento en la parte posterior.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_deque_pop_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)   
 [push_back (STL/CLR)](../dotnet/deque-push-back-stl-clr.md)   
 [deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)