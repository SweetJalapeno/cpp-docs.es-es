---
title: Clase CSimpleArrayEqualHelper | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6660f72dbd91a41670b3c5f8772d21caf4b8abc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="csimplearrayequalhelper-class"></a>Clase CSimpleArrayEqualHelper
Esta clase es una aplicación auxiliar para la [CSimpleArray](../../atl/reference/csimplearray-class.md) clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 Una clase derivada.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Estático) Comprueba si dos `CSimpleArray` elementos para la igualdad de objetos.|  
  
## <a name="remarks"></a>Comentarios  
 Esta clase de rasgos es un complemento para el `CSimpleArray` clase. Proporciona un método para comparar dos elementos almacenados en un `CSimpleArray` objeto. De forma predeterminada, los elementos se comparan mediante **operator=()**, pero si la matriz contiene los tipos de datos complejos que no tienen su propio operador de igualdad, será necesario invalidar esta clase.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual  
 Comprueba si dos `CSimpleArray` elementos para la igualdad de objetos.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>Parámetros  
 *T1*  
 Un objeto de tipo T.  
  
 *T2*  
 Un objeto de tipo T.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si los elementos en caso contrario, son iguales, false.  
  
## <a name="see-also"></a>Vea también  
 [Clase CSimpleArray](../../atl/reference/csimplearray-class.md)   
 [Clase CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Información general de clases](../../atl/atl-class-overview.md)
