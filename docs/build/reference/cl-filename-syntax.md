---
title: Sintaxis de nombre de archivo de CL | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 121cd8971be65e15ad6445cb347baf478046bf3e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="cl-filename-syntax"></a>Sintaxis de nombres de archivo de CL
CL acepta archivos con nombres que siguen las convenciones de nomenclatura FAT, HPFS o NTFS. Todos los nombres de archivo pueden incluir una ruta de acceso completa o parcial. Una ruta de acceso completa incluye un nombre de unidad y uno o más nombres de directorio. CL acepta nombres de archivo separan por barras diagonales inversas (\\) o barras diagonales (/). Los nombres de archivo que contienen espacios deben encerrarse entre comillas dobles. Una ruta de acceso parcial omite el nombre de la unidad, que CL supone que es la unidad actual. Si no se especifica una ruta de acceso, CL supone que el archivo se encuentra en el directorio actual.  
  
 La extensión del nombre de archivo determina cómo se procesan los archivos. Los archivos de C y C++, que tienen la extensión .c, .cxx o .cpp, se compilan. Otros archivos, incluidos los archivos .obj, las bibliotecas (.lib) y los archivos de definición de módulos (.def), se transfieren al vinculador sin procesarse.  
  
## <a name="see-also"></a>Vea también  
 [Sintaxis de la línea de comandos del compilador](../../build/reference/compiler-command-line-syntax.md)