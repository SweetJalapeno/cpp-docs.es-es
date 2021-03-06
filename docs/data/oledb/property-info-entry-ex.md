---
title: PROPERTY_INFO_ENTRY_EX | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY_EX
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 186c30584c5c5844614994700bf2a7958a73ce2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
Representa una propiedad concreta de un conjunto de propiedades.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>Parámetros  
 *dwPropID*  
 [in] Valor [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) que se puede usar con el GUID del conjunto de propiedades para identificar una propiedad.  
  
 *vt*  
 [in] La [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) de esta entrada de la propiedad.  
  
 `dwFlags`  
 [in] Un valor [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) que describe esta entrada de la propiedad.  
  
 *valor*  
 [in] El valor de la propiedad de tipo `DWORD`.  
  
 `options`  
 **DBPROPOPTIONS_REQUIRED** o **DBPROPOPTIONS_SETIFCHEAP**. Normalmente, un proveedor no necesita establecer `options` ya que lo hace el consumidor.  
  
## <a name="remarks"></a>Comentarios  
 Con esta macro, puede especificar directamente el valor de propiedad de tipo `DWORD` así como opciones y marcas. Para establecer simplemente una propiedad a un valor predeterminado definido en ATLDB.H, use [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Para establecer una propiedad a un valor de su elección, sin establecer opciones ni marcas en ella, use [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## <a name="example"></a>Ejemplo  
 Vea [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldb.h  
  
## <a name="see-also"></a>Vea también  
 [Macros para plantillas de proveedores OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Plantillas del proveedor OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Arquitectura de la plantilla de proveedores OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Crear un proveedor OLE DB](../../data/oledb/creating-an-ole-db-provider.md)