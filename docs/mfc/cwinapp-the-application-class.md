---
title: 'CWinApp: La clase de la aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0c3641441554d73e0c7657dd220be86f0c0cab0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cwinapp-the-application-class"></a>CWinApp: The Application (Clase)
La clase principal de aplicación en MFC encapsula la inicialización, ejecución y terminación de una aplicación para el sistema operativo Windows. Una aplicación compilada en el marco de trabajo debe tener uno y solo un objeto de una clase derivada de [CWinApp](../mfc/reference/cwinapp-class.md). Este objeto se construye antes de crear ventanas.  
  
 `CWinApp` se deriva de `CWinThread`, que representa el subproceso principal de ejecución para la aplicación, que puede que tenga uno o varios subprocesos. En las versiones recientes de MFC, la `InitInstance`, **ejecutar**, `ExitInstance`, y `OnIdle` funciones miembro son realmente en la clase `CWinThread`. Estas funciones se tratan aquí como si fueran `CWinApp` miembros en su lugar, dado que la discusión gira en torno al papel del objeto como objeto de aplicación en lugar de como subproceso principal.  
  
> [!NOTE]
>  La clase de aplicación constituye el subproceso principal de la aplicación de ejecución. Usar funciones de la API de Win32, también puede crear subprocesos secundarios de ejecución. Estos subprocesos pueden utilizar la biblioteca MFC. Para obtener más información, consulte [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Al igual que cualquier programa del sistema operativo Windows, la aplicación de marco de trabajo tiene un `WinMain` (función). En una aplicación de framework, sin embargo, no se escriben `WinMain`. Proporcionado por la biblioteca de clases y se llama cuando se inicia la aplicación. `WinMain` realiza servicios estándar como el registro de clases de ventana. A continuación, llama a funciones miembro del objeto de aplicación para inicializar y ejecutar la aplicación. (Puede personalizar `WinMain` invalidando el `CWinApp` funciones miembro que `WinMain` llamadas.)  
  
 Para inicializar la aplicación, `WinMain` llama a un objeto de la aplicación `InitApplication` y `InitInstance` funciones miembro. Para ejecutar el bucle de mensajes de la aplicación, `WinMain` llamadas el **ejecutar** función miembro. Al finalizar, `WinMain` llama al objeto de aplicación `ExitInstance` función miembro.  
  
> [!NOTE]
>  Nombres que aparecen en **negrita** en esta documentación indican elementos proporcionados por la biblioteca Microsoft Foundation Class y Visual C++. Nombres que aparecen en `monospaced` tipo indica los elementos que se crean o invalidar.  
  
## <a name="see-also"></a>Vea también  
 [Temas generales de MFC](../mfc/general-mfc-topics.md)   
 [CWinApp y el Asistente para aplicaciones MFC](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [Funciones miembro reemplazables de CWinApp](../mfc/overridable-cwinapp-member-functions.md)   
 [Servicios especiales de CWinApp](../mfc/special-cwinapp-services.md)

