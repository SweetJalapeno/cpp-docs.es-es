---
title: CSimpleRow (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68f1983eaad36494892c9a18dcb2dbebe2da1f11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="csimplerow-class"></a>CSimpleRow (Clase)
Proporciona una implementación predeterminada para el identificador de fila, que se utiliza en el [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) clase.  
  
## <a name="syntax"></a>Sintaxis

```cpp
class CSimpleRow  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="methods"></a>Métodos  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|Agrega un recuento de referencias a un identificador de fila existente.|  
|[Compare](../../data/oledb/csimplerow-compare.md)|Compara dos filas para comprobar si hacen referencia a la misma instancia de fila.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|El constructor.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|Versiones de filas.|  
  
### <a name="data-members"></a>Miembros de datos  
  
|||  
|-|-|  
|[m_dwRef](../../data/oledb/csimplerow-m-dwref.md)|Recuento de referencias para un identificador de fila existente.|  
|[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)|Un índice en el conjunto de filas que representa el cursor.|  
  
## <a name="remarks"></a>Comentarios  
 Un identificador de fila es, lógicamente, una etiqueta única para una fila de resultados. `IRowsetImpl` crea un nuevo `CSimpleRow` para todas las filas solicitaron en [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` También se puede reemplazar con su propia implementación del identificador de fila, ya que es un argumento de plantilla predeterminado a `IRowsetImpl`. El único requisito para reemplazar esta clase es que la clase de reemplazo proporciona un constructor que acepta un único parámetro de tipo **largo**.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldb.h  
  
## <a name="see-also"></a>Vea también  
 [Plantillas del proveedor OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Arquitectura de la plantilla de proveedores OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl (Clase)](../../data/oledb/irowsetimpl-class.md)