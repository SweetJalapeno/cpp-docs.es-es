---
title: CViews, CViewInfo | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_bCheckOption
- CViews
- CHECK_OPTION
- CViewInfo
- m_szTableCatalog
- IS_UPDATABLE
- m_szDefinition
- m_szTableName
- m_bIsUpdatable
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CHECK_OPTION
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- m_bCheckOption
- TABLE_SCHEMA
- m_szTableCatalog
- m_szDescription
- m_szDefinition
- m_szTableName
- CViewInfo parameter class
- m_bIsUpdatable
- IS_UPDATABLE
- CViews typedef class
ms.assetid: ad864181-4fab-4919-b0fd-45df5da230d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b17df30dac07222f026f23f778a201cc5824d72a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cviews-cviewinfo"></a>CViews, CViewInfo
Llamar a la clase de typedef **CViews** para implementar su clase de parámetro **CViewInfo**.  
  
## <a name="remarks"></a>Comentarios  
 Vea [clases de conjunto de filas de esquema y clases Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) para obtener más información sobre el uso de clases typedef.  
  
 Esta clase identifica las tablas en que se ven tablas, definidas en el catálogo y pertenecen a un usuario determinado, son dependientes.  
  
 En la tabla siguiente se enumera los miembros de datos de la clase y sus columnas OLE DB correspondiente. Vea [conjunto de filas VIEWS](https://msdn.microsoft.com/en-us/library/ms723122.aspx) en el *referencia del programador de OLE DB* para obtener más información sobre el esquema y las columnas.  
  
|Miembros de datos|Columnas de OLE DB|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szDefinition|VIEW_DEFINITION|  
|m_bCheckOption|CHECK_OPTION|  
|m_bIsUpdatable|IS_UPDATABLE|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbsch.h  
  
## <a name="see-also"></a>Vea también  
 [CRestrictions (Clase)](../../data/oledb/crestrictions-class.md)