---
title: -vmb, - vmg (método de representación) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vmb
- /vmg
dev_langs:
- C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5263b6c7ca227a10b34c32e0b0801eeddf07b9cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Método de representación)
Seleccione el método que usa el compilador para representar los punteros a miembros de clase.  
  
 Use **/vmb** si siempre se define una clase antes de declarar un puntero a un miembro de la clase.  
  
 Use **/vmg** para declarar un puntero a un miembro de una clase antes de definir la clase. Esto puede ser necesario si define miembros en dos clases diferentes que hacen referencia a entre sí. Para estas clases de referencia mutuamente, debe hacerse referencia de una clase antes de definirla.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/vmb  
/vmg  
```  
  
## <a name="remarks"></a>Comentarios  
 También puede usar [pointers_to_members](../../preprocessor/pointers-to-members.md) o [palabras clave de herencia](../../cpp/inheritance-keywords.md) en el código para especificar una representación de puntero.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [trabajar con configuraciones de proyecto](../../ide/working-with-project-properties.md).  
  
2.  Haga clic en la carpeta **C/C++** .  
  
3.  Haga clic en la página de propiedades **Línea de comandos** .  
  
4.  Escriba la opción del compilador en el cuadro **Opciones adicionales** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación  
  
-   Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador](../../build/reference/compiler-options.md)   
 [Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)