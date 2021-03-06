---
title: SyncLockT (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e05a1be5d84db52573d3c3235936ecf82dde5894
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="synclockt-class"></a>SyncLockT (clase)
Admite la infraestructura WRL y no está diseñada para utilizarse directamente desde el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `SyncTraits`  
 El tipo que puede tomar posesión de un recurso.  
  
## <a name="remarks"></a>Comentarios  
 Representa un tipo que puede llevar a cabo exclusivo o compartido posesión de un recurso.  
  
 SyncLockT (clase) se utiliza, por ejemplo, para ayudar a implementar la [SRWLock](../windows/srwlock-class.md) clase.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[SyncLockT::SyncLockT (constructor)](../windows/synclockt-synclockt-constructor.md)|Inicializa una nueva instancia de la clase SyncLockT.|  
|[SyncLockT::~SyncLockT (destructor)](../windows/synclockt-tilde-synclockt-destructor.md)|Desinicializa una instancia de la clase SyncLockT.|  
  
### <a name="protected-constructors"></a>Constructores protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[SyncLockT::SyncLockT (constructor)](../windows/synclockt-synclockt-constructor.md)|Inicializa una nueva instancia de la clase SyncLockT.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[SyncLockT::IsLocked (método)](../windows/synclockt-islocked-method.md)|Indica si el objeto de SyncLockT actual es propietario de un recurso; es decir, el objeto SyncLockT *bloqueado*.|  
|[SyncLockT::Unlock (método)](../windows/synclockt-unlock-method.md)|Devuelve el control de los recursos mantenidos por el objeto de SyncLockT actual, si existe.|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[SyncLockT::sync_ (miembro de datos)](../windows/synclockt-sync-data-member.md)|Contiene el recurso subyacente representado por la clase SyncLockT.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `SyncLockT`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** corewrappers.h  
  
 **Namespace:** Wrappers  
  
## <a name="see-also"></a>Vea también  
 [Wrappers Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock (clase)](../windows/srwlock-class.md)