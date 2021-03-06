---
title: Clase CComSingleThreadModel | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 175cc1b867356949ca861f7015dedb6d64c4282f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ccomsinglethreadmodel-class"></a>Clase CComSingleThreadModel
Esta clase proporciona métodos para aumentar y disminuir el valor de una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-typedefs"></a>Definiciones de tipos públicas  
  
|Name|Descripción|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Hace referencia a clase [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Hace referencia a clase `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Referencias `CComSingleThreadModel`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|Disminuye el valor de la variable especificada. Esta implementación no es segura para subprocesos.|  
|[CComSingleThreadModel::Increment](#increment)|Incrementa el valor de la variable especificada. Esta implementación no es segura para subprocesos.|  
  
## <a name="remarks"></a>Comentarios  
 `CComSingleThreadModel` Proporciona métodos para aumentar y disminuir el valor de una variable. A diferencia de [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) y [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), estos métodos no son seguras para subprocesos.  

 Normalmente, se utiliza `CComSingleThreadModel` a través de uno de dos `typedef` nombres, ya sea [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) o [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). La clase que se hace referencia a cada uno de ellos `typedef` depende del modelo de subprocesos utilizado, tal y como se muestra en la tabla siguiente:  

  
|typedef|Modelo de subprocesamiento sencillo|Modelo de subprocesamiento controlado|Modelo de subprocesamiento libre|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M = `CComMultiThreadModel`  
  
 `CComSingleThreadModel` propio define tres `typedef` nombres. `ThreadModelNoCS` referencias `CComSingleThreadModel`. `AutoCriticalSection` y `CriticalSection` hacen referencia a clase [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), que proporciona métodos vacíos asociados con la obtención y liberación de la propiedad de una sección crítica.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComSingleThreadModel::AutoCriticalSection  
 Cuando se usa `CComSingleThreadModel`, `typedef` nombre `AutoCriticalSection` hace referencia a clase [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Comentarios  
 Dado que `CComFakeCriticalSection` no proporciona una sección crítica, sus métodos no hacen nada.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) y [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) contienen definiciones de `AutoCriticalSection`. En la tabla siguiente muestra la relación entre la clase del modelo de subprocesos y la clase de sección crítica al que hace referencia `AutoCriticalSection`:  
  
|Clase definida en|Clase al que hace referencia|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Además `AutoCriticalSection`, puede usar el `typedef` nombre [CriticalSection](#criticalsection). No se debe especificar `AutoCriticalSection` en objetos globales o miembros de clase estática si desea eliminar el código de inicio de CRT.  
  
### <a name="example"></a>Ejemplo  
 Vea [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>  CComSingleThreadModel::CriticalSection  
 Cuando se usa `CComSingleThreadModel`, `typedef` nombre `CriticalSection` hace referencia a clase [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Comentarios  
 Dado que `CComFakeCriticalSection` no proporciona una sección crítica, sus métodos no hacen nada.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) y [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) contienen definiciones de `CriticalSection`. En la tabla siguiente muestra la relación entre la clase del modelo de subprocesos y la clase de sección crítica al que hace referencia `CriticalSection`:  
  
|Clase definida en|Clase al que hace referencia|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Además `CriticalSection`, puede usar el `typedef` nombre [AutoCriticalSection](#autocriticalsection). No se debe especificar `AutoCriticalSection` en objetos globales o miembros de clase estática si desea eliminar el código de inicio de CRT.  
  
### <a name="example"></a>Ejemplo  
 Vea [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>  CComSingleThreadModel::Decrement  
 Disminuye de esta función estática el valor de la variable que apunta `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `p`  
 [in] Puntero a la variable sea reducido.  
  
### <a name="return-value"></a>Valor devuelto  
 El resultado de la reducción.  
  
##  <a name="increment"></a>  CComSingleThreadModel::Increment  
 Disminuye de esta función estática el valor de la variable que apunta `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `p`  
 [in] Puntero a la variable que se va a incrementar.  
  
### <a name="return-value"></a>Valor devuelto  
 El resultado del incremento.  
  
##  <a name="threadmodelnocs"></a>  CComSingleThreadModel::ThreadModelNoCS  
 Cuando se usa `CComSingleThreadModel`, `typedef` nombre `ThreadModelNoCS` simplemente hace referencia a `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Comentarios  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) y [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) contienen definiciones de `ThreadModelNoCS`. En la tabla siguiente muestra la relación entre la clase del modelo de subprocesos y la clase al que hace referencia `ThreadModelNoCS`:  
  
|Clase definida en|Clase al que hace referencia|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Ejemplo  
 Vea [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Vea también  
 [Información general de clases](../../atl/atl-class-overview.md)
