---
title: 'Stack:: Stack (STL/CLR) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::stack
dev_langs:
- C++
helpviewer_keywords:
- stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e1ed49049a04f41e5a82ba7d25a52ce19c9a4898
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="stackstack-stlclr"></a>stack::stack (STL/CLR)
Construye un objeto de adaptador de contenedor.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Parámetros  
 right  
 Objeto que se va a copiar.  
  
 ajustado  
 Contenedor ajustada que se va a usar.  
  
## <a name="remarks"></a>Comentarios  
 El constructor:  
  
 `stack();`  
  
 crea un contenedor vacío ajustado. Se usa para especificar una secuencia controlada inicial vacía.  
  
 El constructor:  
  
 `stack(stack<Value, Container>% right);`  
  
 crea un contenedor ajustado que es una copia de `right.get_container()`. Se usa para especificar una secuencia controlada inicial que es una copia de la secuencia controlada por el objeto de pila `right`.  
  
 El constructor:  
  
 `stack(stack<Value, Container>^ right);`  
  
 crea un contenedor ajustado que es una copia de `right->get_container()`. Se usa para especificar una secuencia controlada inicial que es una copia de la secuencia controlada por el objeto de pila `*right`.  
  
 El constructor:  
  
 `explicit stack(container_type% wrapped);`  
  
 usa el contenedor existente `wrapped` como el contenedor ajustado. Se utiliza para crear una pila de un contenedor existente.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/pila >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [pila (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)   
 [Stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)