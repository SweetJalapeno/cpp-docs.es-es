---
title: Clase CComAllocator | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3606df325bfd41dabf99bb790ff154b383ab987f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ccomallocator-class"></a>Clase CComAllocator
Esta clase proporciona métodos para administrar la memoria que usa las rutinas de memoria COM.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Llame a este método estático para asignar memoria.|  
|[CComAllocator::Free](#free)|Llame a este método estático para liberar memoria asignada.|  
|[CComAllocator::Reallocate](#reallocate)|Llame a este método estático para reasignar memoria.|  
  
## <a name="remarks"></a>Comentarios  
 Esta clase se utiliza por [plantilla CComHeapPtr](../../atl/reference/ccomheapptr-class.md) para proporcionar la memoria COM rutinas de asignación. La clase equivalente, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), proporciona los mismos métodos con rutinas de CRT.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlbase.h  
  
##  <a name="allocate"></a>  CComAllocator::Allocate  
 Llame a esta función estática para asignar memoria.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `nBytes`  
 Número de bytes que se van a asignar.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un puntero void al espacio asignado, o NULL si no hay suficiente memoria disponible.  
  
### <a name="remarks"></a>Comentarios  
 Asigna memoria. Vea [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) para obtener más detalles.  
  
##  <a name="free"></a>  CComAllocator::Free  
 Llame a esta función estática para liberar memoria asignada.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `p`  
 Puntero a la memoria asignada.  
  
### <a name="remarks"></a>Comentarios  
 Libera la memoria asignada. Vea [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) para obtener más detalles.  
  
##  <a name="reallocate"></a>  CComAllocator::Reallocate  
 Llame a esta función estática para reasignar memoria.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `p`  
 Puntero a la memoria asignada.  
  
 `nBytes`  
 El número de bytes para reasignar.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un puntero void al espacio asignado, o NULL si no hay memoria suficiente  
  
### <a name="remarks"></a>Comentarios  
 Cambia el tamaño de la cantidad de memoria asignada. Vea [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) para obtener más detalles.  
  
## <a name="see-also"></a>Vea también  
 [Clase de plantilla CComHeapPtr](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator (clase)](../../atl/reference/ccrtallocator-class.md)   
 [Información general de clases](../../atl/atl-class-overview.md)
