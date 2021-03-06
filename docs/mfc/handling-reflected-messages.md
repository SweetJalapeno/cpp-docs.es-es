---
title: Controlar los mensajes reflejados | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05b5f62169d2b65010ec75ab8c8b5c30959b77b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="handling-reflected-messages"></a>Controlar los mensajes reflejados
Reflexión de mensajes permite controlar los mensajes para un control, como `WM_CTLCOLOR`, **WM_COMMAND**, y **WM_NOTIFY**, dentro del propio control. Esto hace que el control más independiente y portátil. El mecanismo funciona con controles comunes de Windows, así como con controles ActiveX (anteriormente denominados controles OLE).  
  
 Reflexión de mensajes permite reutilizar los `CWnd`-las clases derivadas más fácilmente. Funciona a través de la reflexión de mensajes [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), uso especial **ON_XXX_REFLECT** entradas del mapa de mensajes: por ejemplo, **ON_CTLCOLOR_REFLECT** y **ON_CONTROL_REFLECT**. [Nota técnica 62](../mfc/tn062-message-reflection-for-windows-controls.md) explica la reflexión de mensajes con más detalle.  
  
## <a name="what-do-you-want-to-do"></a>Qué quieres hacer  
  
-   [Obtener más información sobre la reflexión de mensajes](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implementar la reflexión de mensajes para un control común](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implementar la reflexión de mensajes para un control ActiveX](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>Vea también  
 [Declaración de funciones del controlador de mensajes](../mfc/declaring-message-handler-functions.md)
