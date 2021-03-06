---
title: personalizado (C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b37d87d5380b9d4dac69cee702654285461ead6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="custom-c"></a>custom (C++)
Define los metadatos de un objeto en la biblioteca de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### <a name="parameters"></a>Parámetros  
 *uuid*  
 Identificador único.  
  
 *valor*  
 Un valor que se pueden colocar en una variante.  
  
## <a name="remarks"></a>Comentarios  
 El **personalizado** atributo C++ hará que la información se coloquen en la biblioteca de tipos. Necesitará una herramienta que lee el valor personalizado de la biblioteca de tipos.  
  
 El **personalizado** atributo tiene la misma funcionalidad que la [personalizado](http://msdn.microsoft.com/library/windows/desktop/aa366766) atributo MIDL.  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="attribute-context"></a>Contexto de atributo  
  
|||  
|-|-|  
|**Se aplica a**|COM no `interface`, **clase**, `enum`s, `idl_module` métodos, los miembros de interfaz, los parámetros de la interfaz, `typedef`s, **union**s, `struct`s|  
|**Reiterativo**|Sí|  
|**Atributos requeridos**|**coclase** (cuando se usa en la clase)|  
|**Atributos no válidos**|Ninguna|  
  
 Para obtener más información acerca de los contextos de atributo, consulte [Contextos de atributo](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Vea también  
 [Atributos IDL](../windows/idl-attributes.md)   
 [Atributos independientes](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union y Struct (atributos)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Atributos de parámetro](../windows/parameter-attributes.md)   
 [Atributos de método](../windows/method-attributes.md)   
 [Atributos de clase](../windows/class-attributes.md)   
 [Atributos de interfaz](../windows/interface-attributes.md)   
