---
title: operador&lt; (cola) (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: 2c981e2b-9a88-4b4a-8060-9ac24d5631f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a590a2e1ccb9ea840508084360eecd1cacf62a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="operatorlt-queue-stlclr"></a>operador&lt; (cola) (STL/CLR)
La cola de menos de comparación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parámetros  
 izquierda  
 Contenedor izquierdo que se va a comparar.  
  
 right  
 Contenedor derecho que se va a comparar.  
  
## <a name="remarks"></a>Comentarios  
 El operador función devuelve true si, para la posición más baja `i` que `!(right[i] < left[i])` es también true que `left[i] < right[i]`. De lo contrario, devuelve `left->` [Queue:: Size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() <` `right->size()` se usa para comprobar si `left` está ordenado antes `right` cuando las dos colas están comparado elemento por elemento.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_queue_operator_lt.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/cola >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [cola (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [operador == (cola) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)   
 [operador! = (cola) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)   
 [operador > = (cola) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)   
 [operador > (cola) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)   
 [operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)