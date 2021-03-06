---
title: -VERSION (información de versión) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs:
- C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 092fd11d7bf062afb59c9b33d620624c63b5e01f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="version-version-information"></a>/VERSION (Información de versión)
```  
/VERSION:major[.minor]  
```  
  
## <a name="remarks"></a>Comentarios  
 donde:  
  
 *principales*y *secundaria*  
 El número de versión que desee en el encabezado del archivo .exe o. dll.  
  
## <a name="remarks"></a>Comentarios  
 La opción /VERSION le indica al vinculador que ponga un número de versión en el encabezado del archivo .exe o. dll. Utilice DUMPBIN [/HEADERS](../../build/reference/headers.md) para ver el campo de versión de imagen de los valores de encabezado opcional para ver el efecto de/Version.  
  
 El *principal* y *secundaria* argumentos son números decimales comprendidos en el intervalo comprendido entre 0 y 65.535. El valor predeterminado es la versión 0.0.  
  
 La información especificada con /VERSION no afecta a la información de versión que aparece para una aplicación cuando ve sus propiedades en el Explorador de archivos. Esa información de versión procede de un archivo de recursos que se utiliza para compilar la aplicación. Vea [Editor de información de versión](../../windows/version-information-editor.md) para obtener más información.  
  
 Otra manera de insertar un número de versión es con la [versión](../../build/reference/version-c-cpp.md) instrucción de definición de módulo.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Haga clic en el **vinculador** carpeta.  
  
3.  Haga clic en el **General** página de propiedades.  
  
4.  Modificar el **versión** propiedad.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación  
  
-   Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)   
 [Opciones del vinculador](../../build/reference/linker-options.md)