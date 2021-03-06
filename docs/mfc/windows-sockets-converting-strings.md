---
title: 'Windows Sockets: Convertir cadenas | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bad57be68ce716cddf2ce44f12e94c545a7bbfd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-converting-strings"></a>Windows Sockets: Convertir cadenas
En este artículo y dos artículos complementarios explican varios aspectos de la programación de Windows Sockets. Este artículo explica la conversión de cadenas. Los otros temas se tratan en [Windows Sockets: bloqueo](../mfc/windows-sockets-blocking.md) y [Windows Sockets: orden de bytes](../mfc/windows-sockets-byte-ordering.md).  
  
 Si usa o derivan de la clase [CAsyncSocket](../mfc/reference/casyncsocket-class.md), deberá administrar estos problemas usted mismo. Si usa o derivan de la clase [CSocket](../mfc/reference/csocket-class.md), MFC los administra automáticamente.  
  
## <a name="converting-strings"></a>Convertir cadenas  
 Si realiza la comunicación entre las aplicaciones que utilizan las cadenas almacenadas en diferentes formatos de caracteres anchos, como juegos de Unicode o juegos de caracteres multibyte (MBCS), o entre uno de estos y una aplicación que utiliza cadenas de caracteres ANSI, debe administrar las conversiones usted mismo en `CAsyncSocket`. El `CArchive` objeto que se usa con un `CSocket` objeto administra esta conversión automáticamente a través de las funciones de clase [CString](../atl-mfc-shared/reference/cstringt-class.md). Para obtener más información, vea la especificación de Windows Sockets, incluida en el SDK de Windows.  
  
 Para obtener más información, consulte:  
  
-   [Windows Sockets: Usar la clase CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Usar Sockets con archivos](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Nociones](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Sockets de flujos](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Sockets de datagramas](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Vea también  
 [Windows Sockets en MFC](../mfc/windows-sockets-in-mfc.md)

