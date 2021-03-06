---
title: 'ICommandImpl:: CreateRowset | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6909f8f6825aacf55c000bfd87e0282365180559
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
Llamado por el método [Execute](../../data/oledb/icommandimpl-execute.md) para crear un único conjunto de filas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `RowsetClass`  
 Un miembro de clase de plantilla que representa la clase de conjunto de filas del usuario. Normalmente, generado por el asistente.  
  
 `pUnkOuter`  
 [in] Un puntero a controlar **IUnknown** interfaz si se está creando el conjunto de filas como parte de un agregado; en caso contrario, es null.  
  
 `riid`  
 [in] Corresponde a `riid` en `ICommand::Execute`.  
  
 `pParams`  
 [los in/out] Corresponde a `pParams` en `ICommand::Execute`.  
  
 `pcRowsAffected`  
 Corresponde a `pcRowsAffected` en `ICommand::Execute`.  
  
 `ppRowset`  
 [los in/out] Corresponde a `ppRowset` en `ICommand::Execute`.  
  
 `pRowsetObj`  
 [out] Un puntero a un objeto de conjunto de filas. Normalmente no se utiliza este parámetro, pero se puede usar si debe realizar más trabajo en el conjunto de filas antes de pasarlo a un objeto COM. La duración de `pRowsetObj` está limitado por `ppRowset`.  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar. Consulte `ICommand::Execute` para obtener una lista de los valores típicos.  
  
## <a name="remarks"></a>Comentarios  
 Para crear más de un conjunto de filas, o para proporcionar sus propias condiciones para la creación de conjuntos de filas diferentes, realizar llamadas diferentes a `CreateRowset` desde **Execute**.  
  
 Vea [ICommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) en el *referencia del programador OLE DB.*  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldb.h  
  
## <a name="see-also"></a>Vea también  
 [ICommandImpl (Clase)](../../data/oledb/icommandimpl-class.md)