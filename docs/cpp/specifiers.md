---
title: Especificadores | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2888f8a75e9b7addd2b8f195ffbf875c2b7ae1a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="specifiers"></a>Especificadores
Este tema se describe la *decl-specifiers* componente (especificadores de declaración) de un [declaración](declarations-and-definitions-cpp.md).  
  
 Los siguientes marcadores de posición y palabras clave de lenguaje son especificadores de declaración:  
  
 *especificador de clase de almacenamiento*  
  
 *especificador de tipo*  
  
 *especificador de función*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [__declspec](../cpp/declspec.md) `(` *extended-decl-modifier-seq* `)`  
  
## <a name="remarks"></a>Comentarios  
 El *decl-specifiers* parte de una declaración es la secuencia más larga de *decl-specifiers* que se pueden tomar para indicar un nombre de tipo, sin incluir el puntero o referencia modificadores. El resto de la declaración es la *declarador*, que incluye el nombre introducido.  
  
 En la tabla siguiente se muestran cuatro declaraciones y, a continuación, enumera cada declaración *decl-specifers* y *declarador* componente por separado.  
  
|Declaración|*decl-specifiers*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 Dado que `signed`, `unsigned`, `long`, y `short` implican `int`, un `typedef` nombre siguiente una de estas palabras clave se considera como un miembro de *lista de declaradores,* no sea de *decl-specifiers*.  
  
> [!NOTE]
>  Dado que un nombre se puede declarar de nuevo, su interpretación está sujeta a la declaración más reciente del ámbito actual. La nueva declaración puede afectar al modo en que el compilador interpreta los nombres, especialmente los nombres de `typedef`.  
  
## <a name="see-also"></a>Vea también  
 [Declaraciones y definiciones](declarations-and-definitions-cpp.md)