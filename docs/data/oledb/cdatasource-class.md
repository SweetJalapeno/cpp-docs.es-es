---
title: CDataSource (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs:
- C++
helpviewer_keywords:
- CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7835cd7401c13ab167a9236db4f7e2fc98f3e175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasource-class"></a>CDataSource (Clase)
Corresponde a un objeto de origen de datos OLE DB, que representa una conexión a través de un proveedor a un origen de datos.  
  
## <a name="syntax"></a>Sintaxis

```cpp
class CDataSource  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="methods"></a>Métodos  
  
|||  
|-|-|  
|[Cerrar](../../data/oledb/cdatasource-close.md)|Cierra la conexión.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Recupera la cadena de inicialización del origen de datos que está actualmente abierto.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Obtiene los valores de propiedades establecidas actualmente para el origen de datos conectado.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Obtiene el valor de una sola propiedad establecido actualmente para el origen de datos conectado.|  
|[Abrir](../../data/oledb/cdatasource-open.md)|Crea una conexión a un proveedor (origen de datos) utilizando un **CLSID**, **ProgID**, o un `CEnumerator` moniker proporcionado por el llamador.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Abre un origen de datos desde un archivo especificado por el nombre de archivo proporcionado por el usuario.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Abre el origen de datos especificado por una cadena de inicialización.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Permite al usuario seleccionar un archivo de vínculo de datos creado anteriormente para abrir el origen de datos correspondiente.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Abre un objeto de origen de datos utilizando el cuadro de diálogo de vínculo de datos.|  
  
## <a name="remarks"></a>Comentarios  
 Una o varias sesiones de base de datos pueden crearse para una sola conexión. Estas sesiones se representan mediante `CSession`. Debe llamar a [CDataSource:: Open](../../data/oledb/cdatasource-open.md) para abrir la conexión antes de crear una sesión con `CSession::Open`.  
  
 Para obtener un ejemplo de cómo usar `CDataSource`, consulte el [CatDB](../../visual-cpp-samples.md) ejemplo.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [Plantillas de consumidor OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referencia de plantillas de consumidor OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)