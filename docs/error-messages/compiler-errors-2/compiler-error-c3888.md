---
title: Error del compilador C3888 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c11c897f35a6c395c4bc6ee6a64be51fa810911b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3888"></a>Error del compilador C3888
'name': C++/CLI no admite la expresión const asociada con este miembro de datos literal  
  
 El miembro de datos *name* que se declara con la palabra clave [literal](../../windows/literal-cpp-component-extensions.md) se inicializa con un valor que no es compatible con el compilador. El compilador solo admite los tipos de constante integral, de enumeración o de cadena. La causa probable del error **C3888** es que el miembro de datos se inicializa con una matriz de bytes.  
  
### <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que el miembro de datos declarado literal es un tipo admitido.  
  
## <a name="see-also"></a>Vea también  
 [literal](../../windows/literal-cpp-component-extensions.md)