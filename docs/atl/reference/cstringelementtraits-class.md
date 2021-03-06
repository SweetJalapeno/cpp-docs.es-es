---
title: Clase CStringElementTraits | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ddce07ed7f79c167d4cf819b85de1484346bba93
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="cstringelementtraits-class"></a>Clase CStringElementTraits
Esta clase proporciona funciones estáticas utilizadas por las clases de colección para almacenar `CString` objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 El tipo de datos que se almacenará en la colección.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-typedefs"></a>Definiciones de tipos públicas  
  
|Name|Descripción|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|El tipo de datos que se usará para agregar elementos al objeto de clase de colección.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|El tipo de datos que se usará para recuperar los elementos de objeto de la clase de colección.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Estático) Llame a esta función para comparar dos elementos de cadena para la igualdad.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Estático) Llame a esta función para comparar dos elementos de cadena.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Estático) Llame a esta función para copiar `CString` elementos almacenados en un objeto de clase de colección.|  
|[CStringElementTraits::Hash](#hash)|(Estático) Llame a esta función para calcular un valor hash para el elemento de la cadena especificada.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Estático) Llame a esta función para reubicar `CString` elementos almacenados en un objeto de clase de colección.|  
  
## <a name="remarks"></a>Comentarios  
 Esta clase proporciona funciones estáticas para copiar, mover y comparar cadenas y para crear un valor hash. Estas funciones son útiles cuando se usa una clase de colección para almacenar los datos de cadena. Use [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) cuando se requieren las comparaciones entre mayúsculas y minúsculas. Use [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) cuando los objetos de cadena deben tratarse como referencias.  
  
 Para obtener más información, consulte [clases de colección ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** cstringt.h  
  
##  <a name="compareelements"></a>  CStringElementTraits::CompareElements  
 Llame a esta función estática para comparar dos elementos de cadena para la igualdad.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parámetros  
 `str1`  
 El primer elemento de cadena.  
  
 `str2`  
 El segundo elemento de cadena.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si los elementos en caso contrario, son iguales, false.  
  
##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered  
 Llame a esta función estática para comparar dos elementos de cadena.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parámetros  
 `str1`  
 El primer elemento de cadena.  
  
 `str2`  
 El segundo elemento de cadena.  
  
### <a name="return-value"></a>Valor devuelto  
 Cero si las cadenas son idénticas, < 0 si `str1` es menor que `str2`, o 0 > Si `str1` es mayor que `str2`. El [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) método se usa para realizar las comparaciones.  

  
##  <a name="copyelements"></a>  CStringElementTraits::CopyElements  
 Llame a esta función estática para copiar `CString` elementos almacenados en un objeto de clase de colección.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parámetros  
 `pDest`  
 Puntero al primer elemento que va a recibir los datos copiados.  
  
 `pSrc`  
 Puntero para el primer elemento que se va a copiar.  
  
 `nElements`  
 Número de elementos que se van a copiar.  
  
### <a name="remarks"></a>Comentarios  
 No deben superponerse a los elementos de origen y de destino.  
  
##  <a name="hash"></a>  CStringElementTraits::Hash  
 Llame a esta función estática para calcular un valor hash para el elemento de la cadena especificada.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>Parámetros  
 `str`  
 El elemento de la cadena.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un valor de hash, que se calcula con el contenido de la cadena.  
  
##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE  
 El tipo de datos que se usará para agregar elementos al objeto de clase de colección.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE  
 El tipo de datos que se usará para recuperar los elementos de objeto de la clase de colección.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements  
 Llame a esta función estática para reubicar `CString` elementos almacenados en un objeto de clase de colección.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parámetros  
 `pDest`  
 Puntero al primer elemento que va a recibir los datos reubicados.  
  
 `pSrc`  
 Puntero al primer elemento para cambiar la posición.  
  
 `nElements`  
 El número de elementos que se va a cambiar la ubicación.  
  
### <a name="remarks"></a>Comentarios  
 Llama a esta función estática [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), lo que es suficiente para la mayoría de los tipos de datos. Si los objetos que se mueven contienen punteros a sus propios miembros, esta función estática deberá reemplazarse.  
  
## <a name="see-also"></a>Vea también  
 [Clase CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Clase CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)   
 [Información general de clases](../../atl/atl-class-overview.md)
