---
title: Vinculación en nombres con ámbito de archivo | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 770b30516d16cf9ffccaae4724b368ca8fa33be0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="linkage-in-names-with-file-scope"></a>Vinculación en nombres con ámbito de archivo
Las siguientes reglas de vinculación se aplican a los nombres (que no sean `typedef` y nombres de enumerador) con ámbito de archivo:  
  
-   Si un nombre se declara explícitamente como **estático**, tiene vinculación interna e identifica un elemento de programa dentro de su propia unidad de traducción.  
  
-   Los nombres de enumeradores y nombres `typedef` no tienen ninguna vinculación.  
  
-   El resto de los nombres con ámbito de archivo tienen vinculación externa.  
  
 **Específicos de Microsoft**  
  
-   Si un nombre de función con ámbito de archivo se declara explícitamente como **en línea**, tiene una vinculación externa si se crea una instancia o se hace referencia a su dirección. Por consiguiente, es posible que una función con ámbito de archivo tenga vinculación interna o externa.  
  
 **FIN de Específicos de Microsoft**  
  
 Una clase tiene vinculación interna si:  
  
-   No utiliza ninguna funcionalidad de C++ (por ejemplo, control de acceso a miembros, funciones miembro, constructores, destructores, etc.).  
  
-   No se utiliza en la declaración de otro nombre con vinculación externa. Esta restricción significa que los objetos de tipo de clase que se pasan a funciones con vinculación externa hacen que la clase tenga vinculación externa.  
  
## <a name="see-also"></a>Vea también  
 [Programa y vinculación](../cpp/program-and-linkage-cpp.md)