---
title: Methodreleasenotifier (Constructor) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91540ca3fff03f1f0a449413c2d1ca72781c70f1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier (Constructor)
Inicializa una nueva instancia de la clase methodreleasenotifier.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `object`  
 Un objeto cuya función miembro es un controlador de eventos.  
  
 `method`  
 La función miembro de parámetro `object` que es el controlador de eventos.  
  
 `release`  
 Especifique `true` para habilitar la llamada subyacente [módulo:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) método; en caso contrario, especifique `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** module.h  
  
 **Espacio de nombres:** Microsoft::WRL  
  
## <a name="see-also"></a>Vea también  
 [Module::MethodReleaseNotifier (clase)](../windows/module-methodreleasenotifier-class.md)