---
title: 'Nociones OLE: Estrategias de implementación | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe15690b50c9398d660ca53effbec23cc35f49e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ole-background-implementation-strategies"></a>Nociones de OLE: Estrategias de implementación
Dependiendo de la aplicación, hay cuatro estrategias de implementación posibles para agregar compatibilidad con OLE:  
  
-   Se escribe una nueva aplicación.  
  
     Esta situación suele requerir menos trabajo. Ejecutar al Asistente para aplicaciones MFC y seleccione características avanzadas o compatibilidad con documentos compuestos para crear una aplicación esquema. Para obtener información sobre estas opciones y qué hacer, vea el artículo [crear un programa EXE de MFC](../mfc/reference/mfc-application-wizard.md).  
  
-   Tiene un programa escrito con la biblioteca Microsoft Foundation Class versión 2.0 o superior que no es compatible con OLE.  
  
     Cree una nueva aplicación con el Asistente para aplicaciones de MFC como se mencionó anteriormente y, a continuación, copie y pegue el código de la nueva aplicación en la aplicación existente. Esto funcionará para servidores, contenedores o aplicaciones automatizadas. Vea la MFC [SCRIBBLE](../visual-cpp-samples.md) ejemplo para obtener un ejemplo de esta estrategia.  
  
-   Tiene un programa de Microsoft Foundation Class Library que implementa la compatibilidad de la versión 1.0 de OLE.  
  
     Vea [41 de nota técnica de MFC](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) para que esta estrategia de conversión.  
  
-   Tiene una aplicación que no se escribió con Microsoft Foundation Classes y que puede o no ha implementado compatibilidad con OLE.  
  
     Esta situación requiere más trabajo. Un enfoque consiste en crear una nueva aplicación, como se muestra en la primera estrategia y, a continuación, copie y pegue el código existente en él. Si el código existente está escrito en C, debe modificarla para poder compilarlo como código de C++. Si el código de C llama a la API de Windows, no tendrá que cambiarlo para utilizar Microsoft Foundation classes. Este enfoque es probable que requerirá cierta reestructuración del programa para admitir la arquitectura documento/vista que se usaba en las versiones 2.0 y posteriores de Microsoft Foundation Classes. Para obtener más información sobre esta arquitectura, consulte [Nota técnica 25](../mfc/tn025-document-view-and-frame-creation.md).  
  
 Una vez que haya decidido en una estrategia, debe leer la [contenedores](../mfc/containers.md) o [servidores](../mfc/servers.md) artículos (según el tipo de aplicación que está escribiendo) o examinar los programas de ejemplo, o ambos. Los ejemplos de MFC OLE [OCLIENT](../visual-cpp-samples.md) y [HIERSVR](../visual-cpp-samples.md) se muestra cómo implementar los distintos aspectos de los contenedores y servidores, respectivamente. En varios puntos a lo largo de estos artículos, hará referencia a determinadas funciones de estas aplicaciones como ejemplos de las técnicas que se analice.  
  
## <a name="see-also"></a>Vea también  
 [Nociones de OLE](../mfc/ole-background.md)   
 [Contenedores: Implementar un contenedor](../mfc/containers-implementing-a-container.md)   
 [Servidores: Implementar un servidor](../mfc/servers-implementing-a-server.md)   
 [Asistente para aplicaciones MFC](../mfc/reference/mfc-application-wizard.md)

