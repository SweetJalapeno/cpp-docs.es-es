---
title: COLUMN_ENTRY_LENGTH | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_LENGTH macro
ms.assetid: 1758babf-204c-4d1d-b82a-f9a607072e9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a923f4474f15ffbb2011611bc1f8de476fc399c7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="columnentrylength"></a>COLUMN_ENTRY_LENGTH
Representa un enlace en el conjunto de filas a la columna concreta de la base de datos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)  
  
```  
  
#### <a name="parameters"></a>Parámetros  
 Vea [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) en el *referencia del programador OLE DB*.  
  
 `nOrdinal`  
 [in] El número de columna, a partir de uno. Marcador que se corresponde con la columna cero.  
  
 `data`  
 [in] El miembro de datos correspondiente en el registro de usuario.  
  
 *length*  
 [in] La variable se puede enlazar a la longitud de columna.  
  
## <a name="remarks"></a>Comentarios  
 Esta macro es compatible con la *longitud* variable. Se utiliza en los lugares siguientes:  
  
-   Entre los [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) y [END_COLUMN_MAP](../../data/oledb/end-column-map.md) macros.  
  
-   Entre los [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) y [END_ACCESSOR](../../data/oledb/end-accessor.md) macros.  
  
-   Entre los [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) y [END_PARAM_MAP](../../data/oledb/end-param-map.md) macros.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [Macros y funciones globales para las plantillas de consumidor OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)