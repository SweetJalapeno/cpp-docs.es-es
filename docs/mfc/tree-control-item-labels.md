---
title: Las etiquetas de elemento de Control de árbol | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 598dca9f0d5f394a8e742c1b886588eab3518bf4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-labels"></a>Etiquetas de elemento de control de árbol
Normalmente se especifica el texto de etiqueta de un elemento cuando se agrega el elemento al control de árbol ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). El `InsertItem` función miembro puede pasar un [estructura TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) estructura que define las propiedades del elemento, incluida una cadena que contiene el texto de la etiqueta. `InsertItem` tiene varias sobrecargas que se pueden llamar con distintas combinaciones de parámetros.  
  
 Un control de árbol asigna memoria para almacenar cada elemento; el texto de las etiquetas de elemento ocupa una parte importante de esta memoria. Si la aplicación mantiene una copia de las cadenas en el control de árbol, puede reducir los requisitos de memoria del control especificando el **LPSTR_TEXTCALLBACK** valor en el **pszText** miembro de `TV_ITEM` o `lpszItem` parámetro en lugar de pasar cadenas reales al control de árbol. Usar **LPSTR_TEXTCALLBACK** hace que el control de árbol recuperar el texto de etiqueta de un elemento de la aplicación siempre que sea necesario volver a dibujar el elemento. Para recuperar el texto, el control de árbol envía un [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) mensaje de notificación, que incluye la dirección de un [estructura NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) estructura. Se debe responder estableciendo los miembros correspondientes de la estructura incluye.  
  
 Un control de árbol utiliza memoria asignada desde el montón del proceso que crea el control de árbol. El número máximo de elementos en un control de árbol se basa en la cantidad de memoria disponible en el montón. Cada elemento ocupa 64 bytes.  
  
## <a name="see-also"></a>Vea también  
 [Usar CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Controles](../mfc/controls-mfc.md)

