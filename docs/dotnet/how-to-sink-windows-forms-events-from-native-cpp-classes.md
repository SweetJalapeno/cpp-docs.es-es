---
title: 'Cómo: recibir eventos de Windows Forms de clases de C++ nativo | Documentos de Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0fec32bf179424b5ec0164e4511f74eae44f7320
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Cómo: Recibir eventos de Windows Forms de clases nativas de C++
Puede habilitar clases de C++ nativas recibir devoluciones de llamada desde eventos administrados que se generan a partir de controles de formularios Windows Forms u otros formularios con el formato de mapa de macros de MFC. Recibir eventos en vistas y cuadros de diálogo es similar a utilizar la misma tarea para los controles.  
  
 Para ello, debe:  
  
-   Adjuntar un `OnClick` controlador de eventos para el control mediante [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).  
  
-   Crear un mapa de delegados mediante [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), y [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).  
  
 Este ejemplo continúa el trabajo realizado en [Cómo: realizar enlace de datos DDX/DDV con formularios Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
  
 Ahora, asociará el control MFC (`m_MyControl`) con un delegado de controlador de evento administrado llama a `OnClick` para los recursos administrados <xref:System.Windows.Forms.Control.Click> eventos.  
  
### <a name="to-attach-the-onclick-event-handler"></a>Para asociar el controlador de eventos OnClick:  
  
1.  Agregue el código siguiente a la implementación de BOOL CMFC01Dlg:: OnInitDialog:  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  Agregue el código siguiente a la sección pública de la declaración de clase CMFC01Dlg: CDialog público.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  Por último, agregue la implementación de `OnClick` a CMFC01Dlg.cpp:  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## <a name="see-also"></a>Vea también  
 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)   
 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)   
 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)