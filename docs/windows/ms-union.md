---
title: ms_union | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.ms_union
dev_langs:
- C++
helpviewer_keywords:
- ms_union attribute
ms.assetid: bb548689-6962-457e-af56-8ffdf68987eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a377995149fda8efd565c30caff9b7791748ed79
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="msunion"></a>ms_union
Controla la alineación de representación de datos de red de uniones nonencapsulated.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
[ms_union]  
  
```  
  
## <a name="remarks"></a>Comentarios  
 El **ms_union** atributo C++ tiene la misma funcionalidad que la [ms_union](http://msdn.microsoft.com/library/windows/desktop/aa367100) atributo MIDL.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra la colocación de **ms_union**:  
  
```  
// cpp_attr_ref_ms_union.cpp  
// compile with: /LD  
#include <unknwn.h>  
[object, ms_union, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl {  
   HRESULT DisplayString([in, string] char * p1);  
};  
  
[export, switch_type(short)] union _WILLIE_UNION_TYPE  {  
   [case(24)]  
      float fMays;  
   [case(25)]  
      double dMcCovey;  
   [default]  
      int x;  
 };  
  
[public] typedef _WILLIE_UNION_TYPE WILLIE_UNION_TYPE;  
  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="attribute-context"></a>Contexto de atributo  
  
|||  
|-|-|  
|**Se aplica a**|Uniones nonencapsulated|  
|**Reiterativo**|No|  
|**Atributos requeridos**|Ninguna|  
|**Atributos no válidos**|**dispinterface**|  
  
 Para obtener más información, vea [Contextos de atributo](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Vea también  
 [Atributos IDL](../windows/idl-attributes.md)   
 [Typedef, Enum, Union y Struct (atributos)](../windows/typedef-enum-union-and-struct-attributes.md)   
