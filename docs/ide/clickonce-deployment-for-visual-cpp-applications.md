---
title: Implementación de ClickOnce para aplicaciones de Visual C++ | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e85ec0dfc011aab4d2b3ac835bbe71782b055000
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Implementación de ClickOnce para aplicaciones de Visual C++
Visual Studio proporciona dos tecnologías diferentes para implementar aplicaciones Windows: implementación ClickOnce o [Windows Installer](http://msdn.microsoft.com/library/cc185688) implementación.  
  
## <a name="clickonce-deployment-in-c"></a>Implementación de ClickOnce en C++  
 El entorno de desarrollo de Visual C++ no admite directamente la implementación de proyectos de Visual C++ con ClickOnce, pero las herramientas están disponibles para su uso.  
  
> [!NOTE]
>  Visual Studio es compatible con ClickOnce en los entornos de desarrollo de Visual C# y Visual Basic. Si el proyecto de Visual C++ es una dependencia de un proyecto de Visual C#, puede publicar la aplicación (incluidas sus dependencias) mediante la implementación de ClickOnce desde el entorno de desarrollo de Visual C#.  
  
 Para implementar una aplicación de Visual C++ con ClickOnce, primero tiene que generar un [manifiesto de aplicación ClickOnce](/visualstudio/deployment/clickonce-application-manifest) y un [manifiesto de implementación de ClickOnce](/visualstudio/deployment/clickonce-deployment-manifest) mediante el [Mage.exe (manifiesto Generación y la herramienta de edición)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) o su versión de interfaz gráfica de usuario (para obtener información, consulte [MageUI.exe (generación de manifiestos y herramienta de edición, cliente gráfico)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 Utilice primero Mage.exe para compilar el manifiesto de aplicación; el archivo resultante tendrá la extensión .manifest. A continuación, utilice Mage.exe para compilar el manifiesto de implementación; el archivo resultante tendrá la extensión .application. Por último, firme los manifiestos.  
  
 El manifiesto de aplicación debe especificar el procesador de destino (**x86**, **x64**, o **ARM**). Vea [los requisitos previos de la implementación de aplicaciones de 64 bits](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) para obtener información sobre estas opciones.  
  
 A su vez, el nombre de la aplicación y de los manifiestos de implementación debe ser diferente del nombre de la aplicación de C++. Esto evita el conflicto entre el manifiesto de aplicación creado por Mage.exe y el manifiesto externo que forma parte de la aplicación de C++.  
  
 La implementación tendrá que instalar las bibliotecas de Visual C++ de los que depende la aplicación. Para determinar las dependencias de una aplicación determinada, puede utilizar depends.exe o la utilidad DUMPBIN con la opción /DEPENDENTS. Para obtener más información acerca de las dependencias, consulte [descripción de las dependencias de una aplicación de Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Es posible que deba ejecutar VCRedist.exe; Esta utilidad instala las bibliotecas de Visual C++ en el equipo de destino.  
  
 También debe crear a un programa previo (instalador de requisitos previos) para que su aplicación implementar componentes de requisitos previos; Para obtener información sobre el programa previo, vea [crear paquetes de arranque](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Para obtener una descripción más detallada de la tecnología, vea [seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Para obtener un ejemplo detallado de la implementación de ClickOnce, vea [Tutorial: implementar manualmente una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>Vea también  
 [Mage.exe (Herramienta de generación y edición de manifiestos)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe (herramienta de creación de certificados)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Implementar aplicaciones de escritorio](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Implementar aplicaciones, servicios y componentes](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Implementación de Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Crear paquetes de arranque](/visualstudio/deployment/creating-bootstrapper-packages)   
 [Programación de .NET con C++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilidad nativa y de .NET](../dotnet/native-and-dotnet-interoperability.md)