---
title: Línea de comandos BSCMAKE | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7866d2960acdd89c3015470ef3971307ba162cd3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="bscmake-command-line"></a>Línea de comandos de BSCMAKE
Para ejecutar BSCMAKE, use la siguiente sintaxis de línea de comandos:  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Opciones solo pueden aparecer en el `options` campo en la línea de comandos.  
  
 El *sbrfiles* campo especifica uno o más archivos .sbr creados mediante un compilador o ensamblador. Separe los nombres de los archivos .sbr con espacios o tabulaciones. Debe especificar la extensión; No hay ningún valor predeterminado. Puede especificar una ruta de acceso con el nombre de archivo y se pueden utilizar comodines de sistema operativo (* y?).  
  
 Durante una generación incremental, puede especificar nuevos archivos .sbr que no formaban parte de la generación original. Si desea que todas las contribuciones que se mantiene en el archivo de información de examen, debe especificar todos los archivos .sbr (incluidos los archivos truncados) que se usaron originalmente para crear el archivo .bsc. Si se omite un archivo .sbr, se quita la contribución de ese archivo para el archivo de información de examen.  
  
 No especifique un archivo .sbr truncado para una compilación completa. Una compilación completa requiere las contribuciones de todos los archivos .sbr especificados. Antes de realizar una compilación completa, vuelva a compilar el proyecto y crear un nuevo archivo .sbr para cada archivo vacío.  
  
 El comando siguiente ejecuta BSCMAKE para generar un archivo denominado Main.bsc a partir de tres archivos. sbr:  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Para obtener información relacionada, consulte [archivo de comandos de BSCMAKE](../../build/reference/bscmake-command-file-response-file.md) y [opciones de BSCMAKE](../../build/reference/bscmake-options.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de BSCMAKE](../../build/reference/bscmake-reference.md)