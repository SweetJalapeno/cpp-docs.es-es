---
title: Exclusión mutua Class1 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a9e9674dd8ac5aa7d444a77df66c1aff4a70299
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="mutex-class1"></a>Exclusión mutua Class1
Representa un objeto de sincronización que controla de forma exclusiva un recurso compartido.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-typedefs"></a>Definiciones de tipos públicas  
  
|Name|Descripción|  
|----------|-----------------|  
|**SyncLock**|Sinónimo de una clase que admita bloqueos sincrónicos.|  
  
### <a name="public-constructor"></a>Constructor público  
  
|nombre|Descripción|  
|----------|-----------------|  
|[Mutex::Mutex (constructor)](../windows/mutex-mutex-constructor.md)|Inicializa una nueva instancia de la clase de exclusión mutua.|  
  
### <a name="public-members"></a>Miembros públicos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[Mutex::Lock (método)](../windows/mutex-lock-method.md)|Espera a que el objeto actual o el objeto de exclusión mutua asociado con el identificador especificado, libera la exclusión mutua o ha transcurrido el intervalo de tiempo de espera especificado.|  
  
### <a name="public-operator"></a>Operador público  
  
|nombre|Descripción|  
|----------|-----------------|  
|[Mutex::operator= (operador)](../windows/mutex-operator-assign-operator.md)|Asigna (se desplaza) la exclusión mutua especificada del objeto para el objeto actual de la exclusión mutua.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `Mutex`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** corewrappers.h  
  
 **Namespace:** Wrappers  
  
## <a name="see-also"></a>Vea también  
 [Microsoft::WRL::Wrappers (espacio de nombres)](../windows/microsoft-wrl-wrappers-namespace.md)