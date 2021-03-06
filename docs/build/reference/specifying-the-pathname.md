---
title: Especificar la ruta de acceso | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dd121909fbe0aa2f9305b7bd5779b995a69719
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-the-pathname"></a>Especificar la ruta de acceso
Cada opción de archivo de salida acepta un *pathname* argumento que se puede especificar una ubicación y un nombre para el archivo de salida. El argumento puede incluir un nombre de la unidad y el directorio y el nombre de archivo. No se permiten espacios entre la opción y el argumento.  
  
 Si *pathname* incluye un nombre de archivo sin extensión, el compilador asigna al resultado una extensión predeterminada. Si *pathname* incluye un directorio, pero ningún nombre de archivo, el compilador crea un archivo con un nombre predeterminado en el directorio especificado. El nombre predeterminado se basa en el nombre base del archivo de código fuente y una extensión de valor predeterminado según el tipo del archivo de salida. Si se deja *pathname* por completo, el compilador crea un archivo con un nombre predeterminado en un directorio predeterminado.  
  
 Como alternativa, el *pathname* argumento puede ser un nombre de dispositivo (AUX, CON, PRN o NUL) en lugar de un nombre de archivo. No use un espacio entre la opción y el nombre de dispositivo o un signo de dos puntos como parte del nombre del dispositivo.  
  
|Nombre de dispositivo|Representa|  
|-----------------|----------------|  
|AUX|Dispositivo auxiliar|  
|CON|Consola|  
|PRN|Impresora|  
|NUL|Dispositivo nulo (no se crea ningún archivo)|  
  
## <a name="example"></a>Ejemplo  
 La línea de comandos siguiente envía un archivo de asignaciones a la impresora:  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## <a name="see-also"></a>Vea también  
 [Archivo de salida (/ F) opciones](../../build/reference/output-file-f-options.md)   
 [Opciones del compilador](../../build/reference/compiler-options.md)   
 [Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)