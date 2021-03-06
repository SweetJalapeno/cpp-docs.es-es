---
title: 'Conjunto de registros: Marcadores y posiciones absolutas (ODBC) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
f1_keywords:
- SetAbsolutePosition
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e5e45d2f9dd942e76ccce4231e8280a142e66e56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Conjunto de registros: Marcadores y posiciones absolutas (ODBC)
Este tema es aplicable a las clases ODBC de MFC.  
  
 Al navegar a través de un conjunto de registros, a menudo necesitan una manera de devolver a un registro concreto. Marcador y la posición absoluta de un registro proporcionan dos de estos métodos.  
  
 En este tema se explica:  
  
-   [Cómo usar marcadores](#_core_bookmarks_in_mfc_odbc).  
  
-   [Cómo establecer el registro actual usando posiciones absolutas](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> Marcadores en ODBC de MFC  
 Un marcador identifica de forma única un registro. Al navegar a través de un conjunto de registros, no puede confiar siempre en la posición absoluta de un registro porque se pueden eliminar los registros del conjunto de registros. La manera confiable de realizar un seguimiento de la posición de un registro es utilizar su correspondiente marcador. Clase `CRecordset` proporciona funciones miembro para:  
  
-   Obtener el marcador del registro actual, por lo que puede guardarlo en una variable ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).  
  
-   Mover rápidamente a un registro dado especificando su marcador, que guardó anteriormente en una variable ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).  
  
 En el ejemplo siguiente se muestra cómo utilizar estas funciones miembro para marcar el registro actual y volver a él:  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 No es necesario extraer el tipo de datos subyacente de la [CDBVariant (clase)](../../mfc/reference/cdbvariant-class.md) objeto. Asigne el valor con `GetBookmark` y volver a ese marcador con `SetBookmark`.  
  
> [!NOTE]
>  Dependiendo del controlador ODBC y el tipo de conjunto de registros, se podrían no admitir marcadores. Se puede determinar con facilidad si se admiten marcadores mediante una llamada a [CRecordset:: CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Además, si se admiten marcadores, debe elegir explícitamente implementarlos especificando la **CRecordset:: useBookmarks** opción en el [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) función miembro. También debe comprobar la persistencia de los marcadores después de ciertas operaciones de conjunto de registros. Por ejemplo, si se **Requery** un conjunto de registros, los marcadores ya no podrían ser válidos. Llame a [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) para comprobar si puede llamar con seguridad a `SetBookmark`.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> Posiciones absolutas en ODBC de MFC  
 Además de los marcadores, clase `CRecordset` permite establecer el registro actual especificando una posición ordinal. Esto se denomina posición absoluta.  
  
> [!NOTE]
>  Posiciones absolutas no está disponible en conjuntos de registros solo hacia delante. Para obtener más información acerca de los conjuntos de registros solo hacia delante, vea [conjunto de registros (ODBC)](../../data/odbc/recordset-odbc.md).  
  
 Para mover el puntero del registro actual usando la colocación absoluta, llame a [CRecordset:: SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition). Cuando se pasa un valor para `SetAbsolutePosition`, el registro correspondiente para que la posición ordinal se convierte en el registro actual.  
  
> [!NOTE]
>  La posición absoluta de un registro es potencialmente no confiable. Si el usuario elimina registros del conjunto de registros, cambia la posición ordinal de los registros posteriores. Los marcadores son el método recomendado para mover el registro actual. Para obtener más información, consulte [marcadores en ODBC de MFC](#_core_bookmarks_in_mfc_odbc).  
  
 Para obtener más información sobre la navegación de conjunto de registros, vea [conjunto de registros: desplazamiento (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## <a name="see-also"></a>Vea también  
 [Conjunto de registros (ODBC)](../../data/odbc/recordset-odbc.md)