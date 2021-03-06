---
title: SCHEMA_ENTRY | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 665b337861959b28670a0b2e57649814853a7384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
Asocia un GUID a una clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
      SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>Parámetros  
 `guid`  
 Un conjunto de filas de esquema GUID. Vea [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) en el *referencia del programador de OLE DB* para obtener una lista de conjuntos de filas de esquema y sus GUID.  
  
 *rowsetClass*  
 La clase que va a crear para representar el conjunto de filas de esquema.  
  
## <a name="remarks"></a>Comentarios  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) puede, a continuación, consulta el mapa para obtener una lista de GUID, o puede crear un conjunto de filas si se le asigna un GUID. El conjunto de filas de esquema `IDBSchemaRowsetImpl` crea es similar a un estándar `CRowsetImpl`-clase derivada, salvo que debe proporcionar un **Execute** método que tiene la siguiente firma:  
  
```  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 Esto **Execute** función rellena los datos del conjunto de filas. Crea el Asistente para proyectos ATL, como se describe en [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) en el *referencia del programador de OLE DB*, tres inicial conjuntos de filas de esquema en el proyecto para cada uno de los tres esquemas de OLE DB obligatorios:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **DBSCHEMA_PROVIDER_TYPES**  
  
 El asistente también agrega tres entradas correspondientes en la asignación de esquema. Vea [crear un proveedor de plantillas OLE DB](../../data/oledb/creating-an-ole-db-provider.md) para obtener más información acerca de cómo utilizar el Asistente para crear un proveedor.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldb.h  
  
## <a name="see-also"></a>Vea también  
 [Macros para plantillas de proveedores OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)