---
title: Usar listas de imágenes en un Control de barra de herramientas | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76325d2b078f51860cad7fa3fab61ed7c518a41c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Usar listas de imágenes en un control de barra de herramientas
De forma predeterminada, las imágenes utilizadas por los botones en un control de barra de herramientas se almacenan como un solo mapa de bits. Sin embargo, también puede almacenar imágenes de los botones en un conjunto de listas de imágenes. El objeto de control de barra de herramientas puede utilizar hasta tres listas de imágenes independientes:  
  
-   Habilitar contiene imágenes de lista de imágenes para los botones de barra de herramientas que actualmente están habilitados.  
  
-   Deshabilitado contiene imágenes de lista de imágenes para los botones de barra de herramientas que actualmente están deshabilitadas.  
  
-   Resalta contiene imágenes de lista de imágenes para los botones de barra de herramientas que están actualmente resaltados. Esta lista de imágenes sólo se utiliza cuando la barra de herramientas usa la **TBSTYLE_FLAT** estilo.  
  
 Estas listas de imágenes son utilizadas por el control de barra de herramientas cuando se asocia con la `CToolBarCtrl` objeto. Esta asociación se realiza mediante la realización de llamadas a [CToolBarCtrl:: SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), y [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).  
  
 De forma predeterminada, MFC usa la `CToolBar` clase para implementar barras de herramientas de aplicación MFC. Sin embargo, el `GetToolBarCtrl` función miembro puede usarse para recuperar los datos incrustados `CToolBarCtrl` objeto. A continuación, puede realizar llamadas a `CToolBarCtrl` funciones miembro utilizando el objeto devuelto.  
  
 En el ejemplo siguiente se muestra esta técnica asignando un habilitado (`m_ToolBarImages`) y deshabilitadas (`m_ToolBarDisabledImages`) lista de imágenes a un `CToolBarCtrl` objeto (`m_ToolBarCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  Las listas de imágenes utilizadas por el objeto de barra de herramientas deben tener objetos permanentes. Por esta razón, normalmente son miembros de datos de una clase MFC; en este ejemplo, la clase de ventana de marco principal.  
  
 Una vez que las listas de imágenes están asociadas a la `CToolBarCtrl` de objeto, el marco de trabajo muestra automáticamente la imagen correcta del botón.  
  
## <a name="see-also"></a>Vea también  
 [Usar CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Controles](../mfc/controls-mfc.md)

