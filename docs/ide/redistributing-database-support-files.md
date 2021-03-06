---
title: Redistribuir archivos de compatibilidad de base de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing database support files
- database support files [C++], redistributing
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51697367480569e2d27a4cb67791f5fe4d39a8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-database-support-files"></a>Redistribuir archivos de compatibilidad con bases de datos
Puede redistribuir archivos de compatibilidad para objetos de acceso a datos (DAO) y para las tecnologías de base de datos en el Kit de desarrollo de software (SDK) de Microsoft Data Access.  
  
## <a name="installing-dao-support-files"></a>Instalar archivos de compatibilidad DAO  
 Para obtener la última versión de DAO, vea [artículo 239114: cómo obtener el service pack más reciente para el motor de base de datos de Microsoft Jet 4.0](http://go.microsoft.com/fwlink/p/?linkid=198014) en el sitio Web Microsoft Support.  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Instalar los archivos de compatibilidad del Microsoft Data Access SDK  
 Use Mdac_typ.exe para instalar los archivos de compatibilidad con ODBC, OLE DB, ActiveX Data Objects (ADO) y Remote Data Services (RDS). Mdac_typ.exe se encuentra en la carpeta ..\WCU\MDAC28\ del disco de instalación de Visual Studio. También puede descargar Mdac_typ.exe desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=198015) sitio Web.  
  
 Para obtener más información, en la [MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) sitio Web, busque "Redistribución de MDAC 2.8 SP1". Si utiliza proyectos de instalación de Visual Studio para implementar la aplicación, consulte [implementación y dependencias](http://msdn.microsoft.com/en-us/49e9b84d-bd6a-4388-b9ac-46ea79cf0733).  
  
## <a name="see-also"></a>Vea también  
 [Redistribuir archivos de Visual C++](../ide/redistributing-visual-cpp-files.md)