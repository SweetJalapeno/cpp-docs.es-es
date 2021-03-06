---
title: library_block | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbd97897138edffba12baf47d64465b1f6ca0df4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="libraryblock"></a>library_block
Coloca una construcción dentro del bloque de biblioteca IDL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
[library_block]  
  
```  
  
## <a name="remarks"></a>Comentarios  
 Cuando se coloca una construcción dentro del bloque de biblioteca, asegúrese de que se pasará en la biblioteca de tipos, independientemente de si se hace referencia. De forma predeterminada, solo las construcciones modificación la [coclase](../windows/coclass.md), [dispinterface](../windows/dispinterface.md), y [idl_module](../windows/idl-module.md) atributos se colocan en el bloque de biblioteca.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente, una interfaz personalizada se coloca dentro del bloque de biblioteca.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
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
