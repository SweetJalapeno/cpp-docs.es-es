---
title: Palabras clave de herencia | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs:
- C++
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1088a920e5d023e4dea78e55610bebc0f20c2bac
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="inheritance-keywords"></a>Palabras clave de herencia
**Específicos de Microsoft**  
  
```  
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;  
```  
  
 donde:  
  
 *nombre de clase*  
 Nombre de la clase que se está declarando.  
  
 C++ permite declarar un puntero a un miembro de clase antes de la definición de clase. Por ejemplo:  
  
```  
class S;  
int S::*p;  
```  
  
 En el código anterior, `p` se declara como un puntero a miembro entero de clase S. Sin embargo, `class S` tiene no se ha definido en este código; solo se ha declarado. Cuando el compilador encuentra un puntero así, debe crear una representación generalizada del puntero. El tamaño de la representación depende del modelo de herencia especificado. Hay cuatro maneras de especificar un modelo de herencia al compilador:  
  
-   En el IDE bajo **representación de puntero a miembro**  
  
-   En la línea de comandos utilizando la [/vmg](../build/reference/vmb-vmg-representation-method.md) cambiar  
  
-   Mediante el [pointers_to_members](../preprocessor/pointers-to-members.md) pragma  
  
-   Mediante las palabras clave de herencia `__single_inheritance`, `__multiple_inheritance` y `__virtual_inheritance`. Esta técnica controla el modelo de herencia clase por clase.  
  
    > [!NOTE]
    >  Si siempre se declara un puntero a un miembro de una clase después de definir la clase, no se necesita usar ninguna de estas opciones.  
  
 Declarar un puntero a un miembro de una clase antes de la definición de clase afecta al tamaño y la velocidad del archivo ejecutable resultante. Cuanto más compleja es la herencia usada por una clase, mayor será el número de bytes necesarios para representar un puntero a un miembro de la clase y cuando mayor es el código necesario para interpretar el puntero. La herencia única es la menos compleja y la herencia virtual la más compleja.  
  
 Si se cambia el ejemplo anterior a:  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 independientemente de las opciones de la línea de comandos o las pragmas, los punteros a miembros de `class S` usarán la representación más pequeña posible.  
  
> [!NOTE]
>  La misma declaración adelantada de una representación de puntero a miembro de la clase debe aparecer en cada unidad de traducción que declare punteros a miembros de esa clase y la declaración debe aparecer antes de que se declaren los punteros a miembros.  
  
 **FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave](../cpp/keywords-cpp.md)