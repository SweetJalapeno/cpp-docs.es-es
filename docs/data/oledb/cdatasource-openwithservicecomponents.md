---
title: 'CDataSource:: Openwithservicecomponents | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
dev_langs:
- C++
helpviewer_keywords:
- OpenWithServiceComponents method
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 793f1fcb22ac0c57bc1cccb375a0be24b18116ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourceopenwithservicecomponents"></a>CDataSource::OpenWithServiceComponents
Abre un objeto de origen de datos usando los componentes del servicio en oledb32.dll.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  


HRESULT OpenWithServiceComponents (LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `clsid`  
 [in] El **CLSID** de un proveedor de datos.  
  
 `szProgID`  
 [in] Identificador de programa del proveedor de datos.  
  
 `pPropset`  
 [in] Un puntero a una matriz de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) las estructuras que contienen propiedades y valores que desea establecer. Vea [conjuntos de propiedades y grupos de propiedades](https://msdn.microsoft.com/en-us/library/ms713696.aspx) en el *referencia del programador OLE DB* en el SDK de Windows. Si el objeto de origen de datos se inicializa, las propiedades tienen que pertenecer al grupo de propiedades Data Source. Si la misma propiedad se especifica más de una vez en `pPropset`, el valor que se use será específico del proveedor. Si `ulPropSets` es cero, este parámetro no se tiene en cuenta.  
  
 `ulPropSets`  
 [in] El número de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) estructuras pasan en el *pPropSet* argumento. Si es cero, el proveedor omite `pPropset`.  
  
## <a name="return-value"></a>Valor devuelto  
 Un `HRESULT` estándar.  
  
## <a name="remarks"></a>Comentarios  
 Este método abre un objeto de origen de datos con los componentes del servicio en oledb32.dll; este archivo DLL contiene la implementación de características de componentes de servicio, como la agrupación de recursos y la inscripción automática de transacciones, entre otras. Para obtener más información, vea "Servicios OLE DB" en referencia del programador de OLE DB de [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [CDataSource (Clase)](../../data/oledb/cdatasource-class.md)