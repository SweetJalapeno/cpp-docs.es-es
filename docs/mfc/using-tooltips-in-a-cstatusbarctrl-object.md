---
title: Usar informaciones sobre herramientas en un objeto CStatusBarCtrl | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 323f2861da9fcc498e34792c30c763b4dffb2fd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Usar informaciones sobre herramientas en un objeto CStatusBarCtrl
Para habilitar la información sobre herramientas para un control de barra de estado, cree el `CStatusBarCtrl` objeto con el **SBT_TOOLTIPS** estilo.  
  
> [!NOTE]
>  Si usas un `CStatusBar` objeto para implementar la barra de estado, use la `CStatusBar::CreateEx` función. Permite especificar estilos adicionales para el objeto incrustado **CStatusBarCtrl** objeto.  
  
 Una vez el `CStatusBarCtrl` se ha creado correctamente el objeto, use [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) y [CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) para establecer y recuperar el texto de sugerencia para un panel específico.  
  
 Una vez que se ha establecido la información sobre herramientas, se muestra solo si el elemento incluye un icono y ningún texto, o si todo el texto no se pueden mostrar dentro del elemento. Información sobre herramientas no se admite en el modo básico.  
  
## <a name="see-also"></a>Vea también  
 [Usar CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Controles](../mfc/controls-mfc.md)

