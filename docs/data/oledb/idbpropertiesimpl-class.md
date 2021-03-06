---
title: IDBPropertiesImpl (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3685e6a77e4293ef65b5ee98a0aa326500cfdb2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl (Clase)
Proporciona una implementación para el `IDBProperties` interfaz.  
  
## <a name="syntax"></a>Sintaxis

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 La clase derivada de `IDBPropertiesImpl`.  
  
## <a name="members"></a>Miembros  
  
### <a name="interface-methods"></a>Métodos de interfaz  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Devuelve los valores de propiedades de los grupos de propiedades de origen de datos, información de origen de datos y la inicialización que están establecidos actualmente en el objeto de origen de datos o los valores de propiedades en el grupo de propiedades de inicialización que están establecidas actualmente en el enumerador.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Devuelve información acerca de todas las propiedades admitidas por el proveedor.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Establece propiedades en los grupos de propiedades origen de datos y la inicialización de objetos de origen de datos, o el grupo de propiedades de inicialización de los enumeradores.|  
  
## <a name="remarks"></a>Comentarios  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) es una interfaz obligatoria para los objetos de origen de datos y una interfaz opcional para los enumeradores. Sin embargo, si expone un enumerador [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), debe exponer `IDBProperties`. `IDBPropertiesImpl` implementa `IDBProperties` mediante el uso de una función estática definida por [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldb.h  
  
## <a name="see-also"></a>Vea también  
 [Plantillas del proveedor OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Arquitectura de plantillas de proveedores OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)