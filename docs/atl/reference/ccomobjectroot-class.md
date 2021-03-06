---
title: CComObjectRoot (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6a7d350f7bd50476c1c327d824089981d3e8321
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot (clase)
Esta definición de tipo de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) se hace plantilla en el valor predeterminado modelo del servidor de subprocesos.  
  
## <a name="syntax"></a>Sintaxis  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Comentarios  
 `CComObjectRoot` es un `typedef` de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) hace plantilla en el valor predeterminado modelo del servidor de subprocesos. Por lo tanto [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) hará referencia cualquiera [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) o [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx` controla la administración de recuento de referencia de objeto para los objetos y agregados. Contiene el recuento de referencias de objeto si el objeto no se está agregando y mantiene el puntero para el desconocido externo si se agrega el objeto. Para los objetos agregados, `CComObjectRootEx` métodos pueden usarse para controlar los errores del objeto interno para construir y proteger el objeto contra eliminación cuando se publiquen interfaces internas externo o el objeto interno se elimina.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcom.h  
  
## <a name="see-also"></a>Vea también  
 [Miembros de CComObjectRootEx (clase)](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx (clase)](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject (clase)](../../atl/reference/ccomaggobject-class.md)   
 [CComObject (clase)](../../atl/reference/ccomobject-class.md)   
 [Clase CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [Información general de clases](../../atl/atl-class-overview.md)
