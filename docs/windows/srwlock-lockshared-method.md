---
title: 'SRWLOCK:: Lockshared (método) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
dev_langs:
- C++
helpviewer_keywords:
- LockShared method
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fccc72814ca5c4fff417e0b6221ef0f3c045a5bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="srwlocklockshared-method"></a>SRWLock::LockShared (Método)
Adquiere un objeto SRWLock en modo compartido.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
SyncLockShared LockShared();  
  
static SyncLockShared LockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `lock`  
 Puntero a un objeto SRWLock.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto SRWLock en modo compartido.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** corewrappers.h  
  
 **Namespace:** Wrappers  
  
## <a name="see-also"></a>Vea también  
 [SRWLock (clase)](../windows/srwlock-class.md)