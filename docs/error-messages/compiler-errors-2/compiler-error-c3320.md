---
title: Error del compilador C3320 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08810d38b74081cfb8573d1e33ea3a8ec4dabd4c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3320"></a>Error del compilador C3320
'tipo': el tipo no puede tener el mismo nombre que la propiedad de módulo 'nombre'  
  
Un exportados definidos por el usuario tipo (UDT), que podría ser una estructura, clase, enumeración o unión, no puede tener el mismo nombre que el parámetro pasado a la [módulo](../../windows/module-cpp.md) la propiedad de nombre del atributo.  
  
## <a name="example"></a>Ejemplo  
El ejemplo siguiente genera la advertencia C3320:  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```