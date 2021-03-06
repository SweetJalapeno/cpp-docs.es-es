---
title: alignof y alignas (C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2988d1260cac91e2614765aba8ae1b9be9b922
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="alignof-and-alignas-c"></a>alignof y alignas (C++)
El especificador de tipo `alignas` es una manera portátil y estándar de C++ de especificar una alineación personalizada de variables y tipos definidos por el usuario. El operador `alignof` también es una forma estándar y portátil de obtener la alineación de una variable o un tipo especificado.  
  
## <a name="example"></a>Ejemplo  
 Puede usar `alignas` en una clase, struct o union, o en miembros individuales. Cuando varios especificadores de `alignas` se encuentran, el compilador elige el más estricto (el que tiene el valor más grande).  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Alineación](../cpp/alignment-cpp-declarations.md)