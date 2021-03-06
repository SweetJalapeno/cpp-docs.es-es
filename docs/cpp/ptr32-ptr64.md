---
title: __ptr32, __ptr64 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53fafb1e7be45cd4b48ce51e787b6338dd0f7324
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64
## <a name="microsoft-specific"></a>Específicos de Microsoft  
 `__ptr32` representa un puntero nativo en un sistema de 32 bits, mientras que `__ptr64` representa un puntero nativo en un sistema de 64 bits.  
  
 En el ejemplo siguiente se muestra cómo declarar cada uno de estos tipos de puntero:  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 En un sistema de 32 bits, un puntero declarado con `__ptr64` se trunca a un puntero de 32 bits. En un sistema de 64 bits, un puntero declarado con `__ptr32` se convierte a un puntero de 64 bits.  
  
> [!NOTE]
>  No se puede utilizar `__ptr32` o `__ptr64` cuando se compila con **/CLR: pure**. De lo contrario se generará `Compiler Error C2472`. Las opciones del compilador **/clr:pure** y **/clr:safe** están en desuso en Visual Studio 2015.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar y asignar punteros con las palabras clave `__ptr32` y `__ptr64`.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
```Output  
32  
64  
```  
  
**FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [Tipos fundamentales](../cpp/fundamental-types-cpp.md)