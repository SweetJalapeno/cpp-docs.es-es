---
title: -VERBOSE (imprimir mensajes de progreso) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
dev_langs:
- C++
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee1bf99cdf27e432bf8bdf6b7c0e48a84aeaac21
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (Mostrar mensajes de progreso)
```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## <a name="remarks"></a>Comentarios  
 El vinculador envía información sobre el progreso de la sesión de vinculación a la **salida** ventana. En la línea de comandos, la información se envía a la salida estándar y puede redirigirse a un archivo.  
  
|Opción|Descripción|  
|------------|-----------------|  
|/VERBOSE|Muestra detalles sobre el proceso de vinculación.|  
|/VERBOSE:ICF|Mostrar información acerca de la actividad del vinculador que resulta del uso de [/OPT: ICF](../../build/reference/opt-optimizations.md).|  
|/VERBOSE:INCR|Muestra información sobre el proceso de vinculación incremental.|  
|/VERBOSE:LIB|Muestra mensajes de progreso que indican solamente las bibliotecas de búsqueda.<br /><br /> La información presentada incluye el proceso de búsqueda en las bibliotecas y enumera los nombres de las bibliotecas y objetos (con la ruta de acceso completa), el símbolo que se esté resolviendo de cada biblioteca y una lista de los objetos que hacen referencia al símbolo.|  
|/VERBOSE:REF|Muestra información acerca de la actividad del vinculador que resulta del uso de [/OPT: ref](../../build/reference/opt-optimizations.md).|  
|/VERBOSE:SAFESEH|Muestra información acerca de los módulos que no son compatibles con cuando control de excepciones seguro [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) no se ha especificado.|  
|/VERBOSE:UNUSEDLIBS|Muestra información sobre los archivos de biblioteca que no se usan cuando se crea la imagen.|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Expanda el **vinculador** carpeta.  
  
3.  Seleccione el **línea de comandos** página de propiedades.  
  
4.  Agregar la opción de la **opciones adicionales** cuadro.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación  
  
-   Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)   
 [Opciones del vinculador](../../build/reference/linker-options.md)