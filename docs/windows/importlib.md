---
title: importlib | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importlib
dev_langs:
- C++
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c21b97e50fa03861245a0c0881963387dd8a3102
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="importlib"></a>importlib
Hace que los tipos que ya se han compilado en otra biblioteca de tipos estén disponibles en la biblioteca de tipos que se está creando.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>Parámetros  
 *tlb_file*  
 El nombre de un archivo .tlb, entre comillas, que desea importar en la biblioteca de tipos del proyecto actual.  
  
## <a name="remarks"></a>Comentarios  
 El **importlib** C++ atributo da lugar a un `importlib` instrucción que se colocarán en el bloque de biblioteca del archivo .idl generado. El **importlib** atributo tiene la misma funcionalidad que la [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) atributo MIDL.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra un ejemplo de cómo usar **importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="attribute-context"></a>Contexto de atributo  
  
|||  
|-|-|  
|**Se aplica a**|En cualquier lugar|  
|**Reiterativo**|No|  
|**Atributos requeridos**|Ninguna|  
|**Atributos no válidos**|Ninguna|  
  
 Para obtener más información, vea [Contextos de atributo](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Vea también  
 [Atributos de compilador](../windows/compiler-attributes.md)   
 [Atributos independientes](../windows/stand-alone-attributes.md)   
 [Importación](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [Incluir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)