---
title: HandleT (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99a596bf1e086ac7b1a1a72c3504ce4f41844ba4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="handlet-class"></a>HandleT (clase)
Representa un identificador a un objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `HandleTraits`  
 Una instancia de la [HandleTraits](../windows/handletraits-structure.md) estructura que define las características comunes de un identificador.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-typedefs"></a>Definiciones de tipos públicas  
  
|Name|Descripción|  
|----------|-----------------|  
|`Traits`|Sinónimo de `HandleTraits`.|  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[HandleT::HandleT (constructor)](../windows/handlet-handlet-constructor.md)|Inicializa una nueva instancia de la clase HandleT.|  
|[HandleT::~HandleT (destructor)](../windows/handlet-tilde-handlet-destructor.md)|Desinicializa una instancia de la clase HandleT.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[HandleT::Attach (método)](../windows/handlet-attach-method.md)|Asocia el identificador especificado con el objeto de HandleT actual.|  
|[HandleT::Close (método)](../windows/handlet-close-method.md)|Cierra el actual objeto HandleT.|  
|[HandleT::Detach (método)](../windows/handlet-detach-method.md)|Desasocia el objeto de HandleT actual de su identificador subyacente.|  
|[HandleT::Get (método)](../windows/handlet-get-method.md)|Obtiene el valor del identificador subyacente.|  
|[HandleT::IsValid (método)](../windows/handlet-isvalid-method.md)|Indica si el objeto de HandleT actual representa un identificador.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[HandleT::InternalClose (método)](../windows/handlet-internalclose-method.md)|Cierra el actual objeto HandleT.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[HandleT::operator= (operador)](../windows/handlet-operator-assign-operator.md)|Mueve el valor del objeto HandleT especificado al objeto HandleT actual.|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[HandleT::handle_ (miembro de datos)](../windows/handlet-handle-data-member.md)|Contiene el identificador que se representa mediante el objeto HandleT.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `HandleT`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** corewrappers.h  
  
 **Namespace:** Wrappers  
  
## <a name="see-also"></a>Vea también  
 [Microsoft::WRL::Wrappers (espacio de nombres)](../windows/microsoft-wrl-wrappers-namespace.md)