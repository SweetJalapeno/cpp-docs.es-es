---
title: Funciones globales de contexto de dispositivo | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37d54fbe9391cb53cca1d84401e90bb6fd47a479
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="device-context-global-functions"></a>Funciones globales de contexto de dispositivo
Esta función crea un contexto de dispositivo para un dispositivo determinado.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Crea un contexto de dispositivo.|  
  
##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC  
 Crea un contexto de dispositivo para el dispositivo especificado en el [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) estructura.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Parámetros  
 *HDC*  
 [in] El identificador existente de un contexto de dispositivo, o **NULL**.  
  
 `ptd`  
 [in] Un puntero a la **DVTARGETDEVICE** estructura que contiene información sobre el dispositivo de destino.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el identificador en un contexto de dispositivo para el dispositivo especificado en el **DVTARGETDEVICE**. Si no se especifica ningún dispositivo, devuelve el identificador en el dispositivo de presentación predeterminado.  
  
### <a name="remarks"></a>Comentarios  
 Si la estructura es **NULL** y *hdc* es **NULL**, crea un contexto de dispositivo para el dispositivo de pantalla de manera predeterminada.  
  
 Si *hdc* no **NULL** y `ptd` es **NULL**, la función devuelve existente *hdc*.  

## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlwin.h  
   
## <a name="see-also"></a>Vea también  
 [Funciones](../../atl/reference/atl-functions.md)
