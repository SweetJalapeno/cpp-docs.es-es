---
title: operador = (deque) (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: 0851c6e2-29a2-45da-8c5a-e0b2f5357fb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e44eff576f4bcafcf234eefd228dec7b07596661
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="operator-deque-stlclr"></a>operator= (deque) (STL/CLR)
Reemplaza la secuencia controlada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
deque<Value>% operator=(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parámetros  
 right  
 Contenedor que se va a copiar.  
  
## <a name="remarks"></a>Comentarios  
 Las copias de operador de miembro `right` en el objeto, a continuación, devuelve `*this`. Se usa para reemplazar la secuencia controlada por una copia de la secuencia controlada de `right`.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_deque_operator_as.cpp   
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
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)