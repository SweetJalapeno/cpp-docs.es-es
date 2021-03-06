---
title: Controlar la notificación TTN_NEEDTEXT para información sobre herramientas | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TTN_NEEDTEXT
dev_langs:
- C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce7a4d6dc6edf122b5d9b5301768dea8389e771e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Controlar la notificación TTN_NEEDTEXT para la información sobre herramientas
Como parte de [habilitar información sobre herramientas](../mfc/enabling-tool-tips.md), controlar el **TTN_NEEDTEXT** mensaje agregando la siguiente entrada al mapa de mensajes de la ventana propietaria:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 La función miembro se llama cuando es necesario el texto para que este botón.  
  
 Tenga en cuenta que el identificador de una información sobre herramientas siempre es 0.  
  
 Declare la función del controlador en la definición de clase como sigue:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 donde los parámetros en cursiva son:  
  
 `id`  
 Identificador del control que envía la notificación. No usado. El identificador del control se toma de la **NMHDR** estructura.  
  
 `pNMHDR`  
 Un puntero a la [estructura NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) estructura. Esta estructura también se explica más adelante en [TOOLTIPTEXT (estructura)](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 Un puntero al código resultante puede establecer antes de volver. **TTN_NEEDTEXT** controladores pueden pasar por alto el `pResult` parámetro.  
  
 Como ejemplo de un controlador de notificación de la vista de formulario:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Llame a `EnableToolTips` (este fragmento procedente `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [Información sobre herramientas en ventanas no derivadas de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

