---
title: 'Windows Sockets: Bloquear | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 400114e557632c9a1dd11cc2f9ec5b3101eb8c37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-blocking"></a>Windows Sockets: Bloquear
En este artículo y dos artículos complementarios explican varios aspectos de la programación de Windows Sockets. En este artículo se explica el bloqueo. Los otros temas se tratan en los artículos: [Windows Sockets: orden de bytes](../mfc/windows-sockets-byte-ordering.md) y [Windows Sockets: convertir cadenas](../mfc/windows-sockets-converting-strings.md).  
  
 Si usa o derivan de la clase [CAsyncSocket](../mfc/reference/casyncsocket-class.md), deberá administrar estos problemas usted mismo. Si usa o derivan de la clase [CSocket](../mfc/reference/csocket-class.md), MFC los administra automáticamente.  
  
## <a name="blocking"></a>Bloqueo  
 Un socket puede estar en "modo de bloqueo" o "modo de no bloqueo". Las funciones de sockets en modo de bloqueo (o sincrónico) no vuelve hasta que puede completar su acción. Esto se denomina bloqueo porque el socket se llamó a cuya función no puede hacer nada, se bloquea, hasta que devuelva la llamada. Una llamada a la **recepción** función miembro, por ejemplo, puede tardar un arbitrariamente mucho tiempo en completarse cuando se espera por la aplicación de envío enviar (Esto es si utilizas `CSocket`, o mediante `CAsyncSocket` con bloqueo). Si un `CAsyncSocket` objeto está en modo de no bloqueo (funciona de forma asincrónica), la llamada devuelve inmediatamente y el código de error actual, puede recuperar con el [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) es la función miembro, **WSAEWOULDBLOCK**, que indica que la llamada se habría bloqueado si no se devuelve inmediatamente a causa del modo. (`CSocket` nunca devuelve **WSAEWOULDBLOCK**. La clase administra bloqueo automáticamente.)  
  
 El comportamiento de los sockets es diferente en 32 bits y 64 bits sistemas operativos (como Windows 95 o Windows 98) que en sistemas operativos de 16 bits (como Windows 3.1). A diferencia de los sistemas operativos de 16 bits, los sistemas operativos de 32 bits y 64 bits utilizan la multitarea preferente y proporcionan subprocesamiento múltiple. En los sistemas operativos de 32 bits y 64 bits, puede colocar los sockets en subprocesos de trabajo independientes. Puede bloquear un socket en un subproceso sin interferir con otras actividades en la aplicación y sin necesidad de dedicar el tiempo de proceso en el bloqueo. Para obtener información sobre la programación multiproceso, vea el artículo [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
> [!NOTE]
>  En las aplicaciones multiproceso, puede usar la característica de bloqueo de `CSocket` para simplificar el diseño del programa sin que afecte a la capacidad de respuesta de la interfaz de usuario. Controlando las interacciones del usuario en el subproceso principal y `CSocket` de procesamiento en subprocesos alternativos, puede separar estas operaciones lógicas. En una aplicación que no es multiproceso, deben combinar y controlarse como un único subproceso, lo que suele significa utilizando estas dos actividades `CAsyncSocket` por lo que puede controlar las solicitudes de las comunicaciones a petición o reemplazar `CSocket::OnMessagePending` para controlar las acciones del usuario durante la actividad sincrónica larga.  
  
 El resto de este tema es para los programadores de sistemas operativos de 16 bits de destino:  
  
 Normalmente, si está utilizando `CAsyncSocket`, debe evitar el uso de operaciones de bloqueo y funcione de forma asincrónica en su lugar. En las operaciones asincrónicas, desde el punto en que se recibe un **WSAEWOULDBLOCK** código de error después de llamar a **recepción**, por ejemplo, esperar hasta que su `OnReceive` función miembro se llama para notificar se puede volver a leer. Llamadas asincrónicas se realizan mediante una llamada a volver función de notificación de devolución de llamada adecuada del socket, como [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).  
  
 En Windows, las llamadas que causan bloqueos se consideran práctica incorrecta. De forma predeterminada, [CAsyncSocket](../mfc/reference/casyncsocket-class.md) admite las llamadas asincrónicas y se debe administrar el bloqueo mediante notificaciones de devolución de llamada. Clase [CSocket](../mfc/reference/csocket-class.md), por otro lado, es sincrónico. Proporciona mensajes de Windows y administrar los bloqueos.  
  
 Para obtener más información acerca del bloqueo, vea la especificación de Windows Sockets. Para obtener más información acerca de "En" funciones, vea [Windows Sockets: sockets de notificación](../mfc/windows-sockets-socket-notifications.md) y [Windows Sockets: derivar desde clases de Socket](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Para obtener más información, consulte:  
  
-   [Windows Sockets: Usar la clase CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Usar Sockets con archivos](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Nociones](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Sockets de flujos](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Sockets de datagramas](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Vea también  
 [Windows Sockets en MFC](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)

