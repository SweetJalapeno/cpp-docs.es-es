---
title: Grabar ver código creado por el Asistente para aplicaciones (acceso a datos MFC) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15355d156b3c85c8f99ba638b30f831da96686af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Código de vista de registros creado por el Asistente para aplicaciones (acceso a datos MFC)
El [Asistente para aplicaciones MFC](../mfc/reference/database-support-mfc-application-wizard.md) invalida la vista `OnInitialUpdate` y `OnGetRecordset` funciones miembro. Después de que el marco cree la ventana de marco, el documento y la vista, llamará a `OnInitialUpdate` para inicializar la vista. `OnInitialUpdate` obtiene un puntero al conjunto de registros desde el documento. Una llamada a la clase base [CView:: OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) función abre el conjunto de registros. El código siguiente muestra este proceso para una `CRecordView`:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 Cuando se abre el conjunto de registros, selecciona los registros. [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) convierte el primer registro en el registro actual y DDX mueve los datos de miembros de datos de campo del conjunto de registros a los correspondientes controles de formulario en la vista. Para obtener más información sobre RFX, consulte [intercambio de campos de registros (RFX)](../data/odbc/record-field-exchange-rfx.md). Para obtener más información sobre DDX, consulte [intercambio de datos de cuadros de diálogo y validación](../mfc/dialog-data-exchange-and-validation.md). Para obtener información sobre el proceso de creación de documento/vista, vea [usar las clases para escribir aplicaciones para Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
> [!NOTE]
>  Debe ofrecer a los usuarios finales la capacidad de actualizar los controles de vista de registros desde el conjunto de registros. Sin esta capacidad, si un usuario cambia el valor de un control a un valor no válido, puede quedarse bloqueado en el registro actual. Para actualizar los controles, se llama a la `CWnd` función miembro [UpdateData](../mfc/reference/cwnd-class.md#updatedata) con un parámetro de **FALSE**.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar una vista de registros](../data/using-a-record-view-mfc-data-access.md)