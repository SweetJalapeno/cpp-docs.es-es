---
title: 'CDataConnection:: operator BOOL | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: ad0bea7f-61ff-47f7-8127-32a31e3e9b9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5597e99b23a928df1d5052ed6354baf2dae21864
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectionoperator-bool"></a>CDataConnection::operator BOOL
Determina si la sesión actual está abierta o no.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
operator BOOL() throw();  
  
```  
  
## <a name="remarks"></a>Comentarios  
 Devuelve **BOOL** valor (definición de tipo MFC). **TRUE** significa que la sesión actual está abierta; **FALSE** significa que se cierra la sesión actual.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [CDataConnection (clase)](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection:: operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)