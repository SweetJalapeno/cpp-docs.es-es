---
title: Efecto de banda elástica y seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2b1b5b0a49fdb59417be04864c9d1ef5341f849
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="rubber-banding-and-trackers"></a>Efecto de banda elástica y seguimiento
Otra característica proporcionada con los objetos de seguimiento es la selección de "banda elástica", lo que permite al usuario seleccionar varios elementos OLE arrastrando un rectángulo de ajuste de tamaño alrededor de los elementos que se seleccione. Cuando el usuario suelta el botón primario del mouse, elementos dentro de la región seleccionada por el usuario se seleccionan y se pueden manipular con el usuario. Por ejemplo, el usuario puede arrastrar la selección en otra aplicación de contenedor.  
  
 La implementación de esta característica requiere código adicional en la aplicación `WM_LBUTTONDOWN` función de controlador.  
  
 El ejemplo de código siguiente implementa la selección de goma elástica y otras características adicionales.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 Si desea permitir una orientación reversible de la herramienta de seguimiento durante el efecto de banda elástica, debería llamar a [CRectTracker:: TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) con el tercer parámetro establecido en **TRUE**. Recuerde que a veces hará que permitir orientación reversible [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) a convertirse en invertido. Esto puede corregirse mediante una llamada a [CRect:: NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).  
  
 Para obtener más información, consulte [elementos de cliente de contenedor](../mfc/containers-client-items.md) y [personalización de arrastrar y colocar](../mfc/drag-and-drop-customizing.md).  
  
## <a name="see-also"></a>Vea también  
 [Objetos de seguimiento: Implementar en una aplicación OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker (clase)](../mfc/reference/crecttracker-class.md)
