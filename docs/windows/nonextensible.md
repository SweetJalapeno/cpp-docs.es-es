---
title: nonextensible | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87cdbf66676ed2a3e6054006270b39ad80325857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="nonextensible"></a>nonextensible
Especifica que el `IDispatch` implementación incluye solo las propiedades y métodos aparecen en la descripción de interfaz y no se puede ampliar con miembros adicionales en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
[nonextensible]  
  
```  
  
## <a name="remarks"></a>Comentarios  
 El **nonextensible** atributo C++ tiene la misma funcionalidad que la [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) atributo MIDL.  
  
 El uso de **nonextensible** también requiere la [oleautomation](../windows/oleautomation.md) atributo.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra un uso de la **nonextensible** atributo:  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="attribute-context"></a>Contexto de atributo  
  
|||  
|-|-|  
|**Se aplica a**|`interface`|  
|**Reiterativo**|No|  
|**Atributos requeridos**|**dual** y **oleautomation**, o **dispinterface**|  
|**Atributos no válidos**|Ninguna|  
  
 Para obtener más información acerca de los contextos de atributo, consulte [Contextos de atributo](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Vea también  
 [Atributos IDL](../windows/idl-attributes.md)   
 [Atributos de interfaz](../windows/interface-attributes.md)   
