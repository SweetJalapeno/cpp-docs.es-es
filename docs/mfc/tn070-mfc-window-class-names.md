---
title: 'TN070: Nombres de clase de ventana MFC | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.classes
dev_langs:
- C++
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c66c434503bbd2c6d7ee1b0557fa73d843e0caaa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tn070-mfc-window-class-names"></a>TN070: Nombres de clases de ventana
> [!NOTE]
>  La nota técnica siguiente no se ha actualizado desde que se incluyó por primera vez en la documentación en línea. Como resultado, algunos procedimientos y temas podrían estar obsoletos o ser incorrectos. Para obtener información más reciente, se recomienda buscar el tema de interés en el índice de la documentación en línea.  
  
 Windows MFC utiliza un nombre de clase creado dinámicamente que refleja las características de la ventana. MFC generará los nombres de clase dinámicamente para ventanas de marco, vistas y ventanas emergentes producidos por la aplicación. Cuadros de diálogo y controles generados por una aplicación MFC tienen el nombre proporcionado por Windows para la clase de ventana en cuestión.  
  
 Puede reemplazar el nombre de clase dinámicamente proporcionada por registrar su propia clase de ventana y su uso con una invalidación de [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). Sus nombres de clase proporcionado por MFC ajustan a uno de los dos formatos siguientes:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 Los dígitos hexadecimales que reemplacen la `%x` caracteres se rellenan de datos de la [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) estructura. MFC utiliza esta técnica para que varias clases de C++ que requieren idénticos **WNDCLASS** estructuras pueden compartir la misma clase de ventana registrados. A diferencia de la mayoría de aplicaciones Win32 simple, las aplicaciones MFC tienen solo una **/ / WNDPROC**, por lo que pueden compartir fácilmente **WNDCLASS** estructuras para ahorrar tiempo y memoria. Los valores reemplazables para el `%x` caracteres mostrados anteriormente son los siguientes:  
  
- **WNDCLASS.hInstance**  
  
- **WNDCLASS.style**  
  
- **WNDCLASS.hCursor**  
  
- **WNDCLASS.hbrBackground**  
  
- **WNDCLASS.hIcon**  
  
 La primera forma (`Afx:%x:%x`) se utiliza cuando **hCursor**, **hbrBackground**, y **hIcon** son todos los **NULL**.  
  
## <a name="see-also"></a>Vea también  
 [Notas técnicas por número](../mfc/technical-notes-by-number.md)   
 [Notas técnicas por categoría](../mfc/technical-notes-by-category.md)   
 [TN020: Convenciones de nomenclatura y numeración de identificadores](../mfc/tn020-id-naming-and-numbering-conventions.md)

