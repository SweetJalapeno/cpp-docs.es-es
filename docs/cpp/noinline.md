---
title: noinline | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f81ab892fd7f406292925f424bebc7514fd7ea0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Específicos de Microsoft  
 **__declspec (noinline)** indica al compilador que nunca alinee una función miembro determinada (función de una clase).  
  
 Puede merecer la pena no alinear una función si es pequeña y no es crítica para el rendimiento del código. Es decir, si la función es pequeña y no se la llamará a menudo, por ejemplo, una función que controla una condición de error.  
  
 Tenga en cuenta que si una función se marca como `noinline`, la función de llamada será más pequeña y, por tanto, será por sí misma un candidato para la alineación del compilador.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [__declspec](../cpp/declspec.md)   
 [Palabras clave](../cpp/keywords-cpp.md)   
 [inline, __inline, \__forceinline](inline-functions-cpp.md)

