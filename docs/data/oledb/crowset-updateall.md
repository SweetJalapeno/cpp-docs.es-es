---
title: 'CRowset:: UpdateAll | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset::UpdateAll
- ATL.CRowset.UpdateAll
- CRowset<TAccessor>.UpdateAll
- ATL.CRowset<TAccessor>.UpdateAll
- UpdateAll
- CRowset.UpdateAll
- ATL::CRowset<TAccessor>::UpdateAll
- CRowset<TAccessor>::UpdateAll
- ATL::CRowset::UpdateAll
dev_langs:
- C++
helpviewer_keywords:
- UpdateAll method
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9e21cd34a4d758becb12b529fe858e96d18f187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetupdateall"></a>CRowset::UpdateAll
Los cambios pendientes realizados en todas las filas desde la última recuperación transmite o **actualización** llamar en ella.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT UpdateAll(DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pcRows`  
 [out] Un puntero a la ubicación donde `UpdateAll` devuelve el número de filas que intentó actualizar, si es necesario.  
  
 `pphRow`  
 [out] Un puntero a la memoria en el que `UpdateAll` devuelve el identificador de la fila intentó actualizar. No hay ningún identificador se devuelve si `pphRow` es null.  
  
 `ppStatus`  
 [out] Un puntero a la ubicación donde **actualización** devuelve el valor de estado de fila. Si no se devuelve ningún estado `ppStatus` es null.  
  
## <a name="remarks"></a>Comentarios  
 Los cambios pendientes realizados en todas las filas, ya que las filas se capturó en último lugar o actualizan utilizando transmite [actualización](../../data/oledb/crowset-update.md) o `UpdateAll`. `UpdateAll` se actualizarán todas las filas que se ha modificado, independientemente de si todavía tiene el identificador para ellos (vea `pphRow`) o no.  
  
 Por ejemplo, si ha usado **insertar** para insertar cinco filas en un conjunto de filas, se puede llamar a **actualizar** cinco veces o llame `UpdateAll` una vez para actualizar todos ellos.  
  
 Este método requiere que la interfaz opcional `IRowsetUpdate`, que no se admite en todos los proveedores; si éste es el caso, el método devuelve **E_NOINTERFACE**. También debe establecer **DBPROP_IRowsetUpdate** a `VARIANT_TRUE` antes de llamar a **abiertos** en la tabla o el comando que contiene el conjunto de filas.  
  
## <a name="return-value"></a>Valor devuelto  
 Un `HRESULT` estándar.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [CRowset (clase)](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate:: Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)