---
title: operador&lt; (map) (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: 9ff87b44-663e-4b99-9dba-d775d9f6f853
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d66b8463676cf0cc20876bc444cecfb8084a1a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="operatorlt-map-stlclr"></a>operador&lt; (map) (STL/CLR)
Lista inferior comparación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator<(map<Key, Mapped>% left,  
        map<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>Parámetros  
 izquierda  
 Contenedor izquierdo que se va a comparar.  
  
 right  
 Contenedor derecho que se va a comparar.  
  
## <a name="remarks"></a>Comentarios  
 El operador función devuelve true si, para la posición más baja `i` que `!(right[i] < left[i])` es también true que `left[i] < right[i]`. De lo contrario, devuelve `left->size() < right->size()` se usa para comprobar si `left` está ordenado antes `right` cuando los dos mapas son comparado elemento por elemento.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_map_operator_lt.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymap c2;   
    c2.insert(Mymap::make_value(L'a', 1));   
    c2.insert(Mymap::make_value(L'b', 2));   
    c2.insert(Mymap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [d 4]  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/mapa >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [asignar (STL/CLR)](../dotnet/map-stl-clr.md)   
 [operador == (map) (STL/CLR)](../dotnet/operator-equality-map-stl-clr.md)   
 [operador! = (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)   
 [operador > = (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)   
 [operador > (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)   
 [operator<= (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)