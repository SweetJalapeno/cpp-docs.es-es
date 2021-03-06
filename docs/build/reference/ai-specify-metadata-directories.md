---
title: -AI (especificar directorios de metadatos) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bde5c93c8a211bb0fc66028932a0a7d50415236d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ai-specify-metadata-directories"></a>/AI (Especificar directorios de metadatos)
Especifica un directorio en el que el compilador debe buscar para resolver las referencias de archivos que se pasan a la directiva `#using`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/AIdirectory  
```  
  
## <a name="arguments"></a>Argumentos  
 `directory`  
 Directorio o ruta de acceso donde debe buscar el compilador.  
  
## <a name="remarks"></a>Comentarios  
 Solo un directorio puede pasarse a una **/AI** invocación. Especifique una **/AI** opción para cada ruta de acceso que desea que el compilador para buscar. Por ejemplo, para agregar C:\Project\Meta y C:\Common\Meta a la ruta de acceso de búsqueda de compilador para `#using` directivas, agregue `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` a la línea de comandos del compilador o agregue cada directorio a la **adicionales # directorios using** propiedad en Visual Studio.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [trabajar con configuraciones de proyecto](../../ide/working-with-project-properties.md).  
  
2.  En el panel de navegación, seleccione **propiedades de configuración**, **C/C++**, **General**.  
  
3.  Modificar el **adicionales # directorios using** propiedad.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación  
  
-   Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador](../../build/reference/compiler-options.md)   
 [Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)   
 [#using (directiva)](../../preprocessor/hash-using-directive-cpp.md)