---
title: Funciones globales de asignación COM | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 509479a923203acd80eaac1ef90aa64125d208c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="com-map-global-functions"></a>Funciones globales de asignación COM
Estas funciones proporcionan compatibilidad para la asignación COM **IUnknown** implementaciones.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Delega en el **IUnknown** de un objeto no agregado.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Genera un código eficaz para comparar interfaces con **IUnknown**.|  

  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface  
 Recupera un puntero a la interfaz solicitada.  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parámetros  
 `pThis`  
 [in] Un puntero al objeto que contiene el mapa de COM de las interfaces expuestas a `QueryInterface`.  
  
 `pEntries`  
 [in] Una matriz de **_ATL_INTMAP_ENTRY** estructuras que tienen acceso a un mapa de las interfaces disponibles.  
  
 `iid`  
 [in] El GUID de la interfaz que se solicita.  
  
 `ppvObject`  
 [out] Un puntero al puntero de interfaz especificado en `iid`, o **NULL** si no se encuentra la interfaz.  
  
### <a name="return-value"></a>Valor devuelto  
 Uno de los valores HRESULT estándar.  
  
### <a name="remarks"></a>Comentarios  
 `AtlInternalQueryInterface` solo administra interfaces de la tabla de asignación COM. Si el objeto es agregado, `AtlInternalQueryInterface` no delegar en el desconocido externo. Puede especificar interfaces en la tabla de asignación de COM con la macro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) o uno de sus variantes.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown  
 Llame a esta función, en el caso especial de prueba de **IUnknown**.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Parámetros  
 *rguid1*  
 [in] El GUID que se comparará con **IID_IUnknown**.  
  
## <a name="see-also"></a>Vea también  
 [Funciones](../../atl/reference/atl-functions.md)   
 [Macros de mapa COM](../../atl/reference/com-map-macros.md)
