---
title: -ASSEMBLYMODULE (agregar un módulo MSIL al ensamblado) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f408bcf58808f64c652f0b1715c47aba7237c160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (Agregar un módulo MSIL al ensamblado)
```  
/ASSEMBLYMODULE:filename  
```  
  
## <a name="remarks"></a>Comentarios  
 donde:  
  
 *filename*  
 El módulo que van a incluir en este ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 La opción /ASSEMBLYMODULE permite agregar una referencia al módulo a un ensamblado. Información de tipo en el módulo no estará disponible para el programa de ensamblado que se ha agregado la referencia de módulo. Sin embargo, la información de tipo en el módulo estará disponible para cualquier programa que hace referencia al ensamblado.  
  
 Use [#using](../../preprocessor/hash-using-directive-cpp.md) agregar una referencia al módulo a un ensamblado y de disponer de información de tipo del módulo para el programa de ensamblado.  
  
 Por ejemplo, considere el siguiente escenario:  
  
1.  Crear un módulo con [/LN](../../build/reference/ln-create-msil-module.md).  
  
2.  Use /ASSEMBLYMODULE en otro proyecto para incluir el módulo en la compilación actual, lo cual creará un ensamblado. Este proyecto no hará referencia al módulo con `#using`.  
  
3.  Cualquier proyecto que hace referencia a este ensamblado ahora también puede utilizar los tipos del módulo.  
  
 Otras opciones del vinculador que afectan a la generación de ensamblado son:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 El vinculador de Visual C++ acepta archivos .netmodule como entrada y el archivo de salida generado por el vinculador será un ensamblado o archivo .netmodule sin ninguna dependencia de tiempo de ejecución en cualquiera de los archivos .netmodule que se utilizaron como entrada al vinculador.  Para más información, consulte [Archivos .netmodule como entrada del vinculador](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Haga clic en el **vinculador** carpeta.  
  
3.  Haga clic en el **entrada** página de propiedades.  
  
4.  Modificar el **Agregar módulo al ensamblado** propiedad.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación  
  
-   Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)   
 [Opciones del vinculador](../../build/reference/linker-options.md)