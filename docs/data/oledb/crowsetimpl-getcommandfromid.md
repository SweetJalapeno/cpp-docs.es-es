---
title: 'CRowsetImpl:: Getcommandfromid | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f79e9287bf8d546ba5007257899a6b6ddc27ad40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
Comprueba si uno o ambos parámetros contienen valores de cadena y si es así, copia los valores de cadena a los miembros de datos [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) y [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pTableID`  
 [in] Un puntero a la **DBID** que representa el identificador de tabla.  
  
 `pIndexID`  
 [in] Un puntero a la **DBID** que representa el identificador de índice.  
  
## <a name="return-value"></a>Valor devuelto  
 Un `HRESULT` estándar.  
  
## <a name="remarks"></a>Comentarios  
 Se llama a este método a través de una conversión hacia arriba estático por `CRowsetImpl` para rellenar los miembros de datos [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) y [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). De forma predeterminada, este método comprueba si uno o ambos parámetros contienen valores de cadena. Si contienen valores de cadena, este método copia los valores de cadena a los miembros de datos. Mediante la colocación de un método con esta firma en el `CRowsetImpl`-clase derivada, se llamará al método en lugar de la implementación base.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldb.h  
  
## <a name="see-also"></a>Vea también  
 [CRowsetImpl (clase)](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)