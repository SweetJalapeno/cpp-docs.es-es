---
title: Clase CDefaultCompareTraits | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5b06bf475c60c0190fc6ab78f4357e1b247f1d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="cdefaultcomparetraits-class"></a>Clase CDefaultCompareTraits
Esta clase proporciona las funciones de comparación de elementos de predeterminado.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 El tipo de datos que se almacenará en la colección.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Estático) Llame a esta función para comparar la igualdad de dos elementos.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Estático) Llame a esta función para determinar el elemento mayor y menor.|  
  
## <a name="remarks"></a>Comentarios  
 Esta clase contiene dos funciones estáticas para comparar los elementos almacenados en un objeto de clase de colección. Esta clase se utiliza por la [CDefaultElementTraits clase](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Para obtener más información, consulte [clases de colección ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcoll.h  
  
##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements  
 Llame a esta función para comparar la igualdad de dos elementos.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parámetros  
 `element1`  
 El primer elemento.  
  
 `element2`  
 El segundo elemento.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si los elementos en caso contrario, son iguales, false.  
  
### <a name="remarks"></a>Comentarios  
 La implementación predeterminada de esta función es la igualdad ( `==`) operador. Para los objetos distintos de los tipos de datos simple, esta función puede deben invalidarse.  
  
##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered  
 Llame a esta función para determinar el elemento mayor y menor.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parámetros  
 `element1`  
 El primer elemento.  
  
 `element2`  
 El segundo elemento.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un entero que se basa en la tabla siguiente:  
  
|Condición|Valor devuelto|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Comentarios  
 La implementación predeterminada de esta función usa la `==`, **\<**, y **>** operadores. Para los objetos distintos de los tipos de datos simple, esta función puede deben invalidarse.  
  
## <a name="see-also"></a>Vea también  
 [Información general de clases](../../atl/atl-class-overview.md)
