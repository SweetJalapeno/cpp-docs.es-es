---
title: 'CDBPropSet:: CDBPropSet | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class, constructor
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58c3639d6c849a4b57ba1b0a75a7840def977556
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropsetcdbpropset"></a>CDBPropSet::CDBPropSet
El constructor. Inicializa el **rgProperties**, **cProperties**, y **guidPropertySet** campos de la [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
      CDBPropSet(const GUID& guid);  

CDBPropSet(const CDBPropSet& propset);  

CDBPropSet();  
```  
  
#### <a name="parameters"></a>Parámetros  
 `guid`  
 [in] Un GUID que se utiliza para inicializar el **guidPropertySet** campo.  
  
 *conjunto de propiedades*  
 [in] Otro `CDBPropSet` objeto para la construcción de copia.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [CDBPropSet (clase)](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet:: SetGuid](../../data/oledb/cdbpropset-setguid.md)   
 [Estructura DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)