---
title: unary_delegate (STL/CLR) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unary_delegate
dev_langs:
- C++
helpviewer_keywords:
- unary_delegate function [STL/CLR]
ms.assetid: b3ee253c-98e8-466e-a272-505e47aed061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 689fc3afba26d4b20816f3513262b6c1fc269e2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="unarydelegate-stlclr"></a>unary_delegate (STL/CLR)
La clase genereic describe un delegado de un argumento. Se usa especificar un delegado en cuanto a sus tipos de argumentos y valores devueltos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### <a name="parameters"></a>Parámetros  
 Arg  
 Tipo del argumento.  
  
 Resultado  
 Tipo de valor devuelto.  
  
## <a name="remarks"></a>Comentarios  
 El delegado genereic describe una función de un argumento.  
  
 Tenga en cuenta que para:  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 los tipos de `Fun1` y `Fun2` son sinónimos, mientras que para:  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 no son del mismo tipo.  
  
## <a name="example"></a>Ejemplo  
  
```  
// cliext_unary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
int hash_val(wchar_t val)   
    {   
    return ((val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate<wchar_t, int> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 5  
hash(L'b') = 22  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<cliext/funcional >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Vea también  
 [binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)