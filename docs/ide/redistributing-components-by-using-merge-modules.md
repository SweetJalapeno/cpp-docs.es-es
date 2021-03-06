---
title: Redistribuir componentes mediante módulos de combinación | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d95b6d2a69b4b40c4464136dd33a8c5231185f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-components-by-using-merge-modules"></a>Redistribuir componentes mediante módulos de fusión mediante combinación
Visual Studio incluye [módulos de combinación](http://msdn.microsoft.com/library/aa367434) para cada componente de Visual C++ que se para puede redistribuir con una aplicación. Cuando un módulo de fusión mediante combinación se compila en un archivo de instalación de Windows Installer, habilita la implementación de determinados archivos DLL en los equipos que tienen una plataforma específica. En el archivo de instalación, especifique que los módulos de fusión mediante combinación son requisitos previos para la aplicación. Cuando se instala Visual Studio, los módulos de combinación se instalan en \Program Files\Common Files\Merge Modules\\. (Solo las versiones de no son de depuración de archivos DLL de Visual C++ se pueden redistribuir.) Para obtener más información y un vínculo a una lista de módulos de combinación que cuentan con licencia para su redistribución, vea [redistribuir archivos de Visual C++](../ide/redistributing-visual-cpp-files.md).  
  
 Puede utilizar los módulos de combinación para habilitar la instalación de Visual C++ los archivos DLL redistribuibles en la carpeta %SYSTEMROOT%\system32\. (Visual Studio usa esta técnica). Sin embargo, la instalación en esta carpeta producirá un error a menos que el usuario que realiza la instalación tenga derechos de administrador.  
  
 Se recomienda no usar módulos de fusión mediante combinación excepto cuando no tenga que mantener la aplicación y no tenga dependencias en más de una versión de los archivos DLL. Los módulos de fusión mediante combinación para versiones diferentes del mismo archivo DLL no se pueden incluir en un instalador y los módulos de fusión mediante combinación hacen que sea difícil mantener los archivos DLL independientemente de la aplicación. En su lugar, se recomienda que instale un paquete redistribuible de Visual C++.  
  
## <a name="see-also"></a>Vea también  
 [Redistribuir archivos de Visual C++](../ide/redistributing-visual-cpp-files.md)