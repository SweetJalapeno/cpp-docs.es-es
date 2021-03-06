---
title: Implementar una aplicación de Visual C++ en una carpeta local de la aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a02e585dc2b82c8b8ad675907e4205db6ad7279
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Tutorial: Implementar una aplicación de Visual C++ en una carpeta local de la aplicación
Describe cómo implementar una aplicación de Visual C++ copiando archivos en su carpeta.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Un equipo que tiene instalado Visual Studio.  
  
-   Otro equipo que no tenga las bibliotecas de Visual C++.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Para implementar una aplicación a una carpeta local de la aplicación  
  
1.  Crear y compilar una aplicación MFC siguiendo los pasos descritos en [Tutorial: implementar una Visual C++ aplicación mediante un proyecto de instalación](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Copie los archivos de biblioteca MFC y tiempo de ejecución de C (CRT) correspondientes, por ejemplo, para un x86 plataforma y compatibilidad con Unicode, copia mfc100u.dll y msvcr100.dll desde \Program Visual Studio 10.0\VC\redist\x86\—and, a continuación, pegan en la carpeta \Release\ de un proyecto MFC. Para obtener más información sobre otros archivos que es posible que deba copiar, consulte [determinar qué archivos DLL se redistribuirán](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Ejecute la aplicación MFC en un segundo equipo que no tenga las bibliotecas de Visual C++.  
  
    1.  Copie el contenido de la carpeta \Release\ y péguelos en la carpeta de aplicación en el segundo equipo.  
  
    2.  Ejecute la aplicación en el segundo equipo.  
  
     La aplicación se ejecuta correctamente porque las bibliotecas de Visual C++ están disponibles en la carpeta local de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de implementación](../ide/deployment-examples.md)