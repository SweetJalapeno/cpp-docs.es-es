---
title: Constantes de atributo de archivo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
dev_langs:
- C++
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 178082356eb08130879cd3b4f2118cbf75e451ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="file-attribute-constants"></a>Constantes de atributo de archivo
## <a name="syntax"></a>Sintaxis  
  
```  
  
#include <io.h>  
```  
  
## <a name="remarks"></a>Comentarios  
 Estas constantes especifican los atributos actuales del archivo o directorio especificado por la función.  
  
 Los atributos se representan mediante las constantes de manifiesto siguientes:  
  
 `_A_ARCH`  
 Archivo. Establecer siempre que el comando BACKUP cambie y desactive el archivo. Valor: 0x20  
  
 `_A_HIDDEN`  
 Archivo oculto. Generalmente no se ve con el comando DIR, a menos que use la opción /AH. Devuelve información sobre los archivos normales y los que tienen este atributo. Valor: 0x02  
  
 `_A_NORMAL`  
 Normal. Se puede leer el archivo o escribir en él sin ninguna restricción. Valor: 0x00  
  
 `_A_RDONLY`  
 Sólo lectura. No se puede abrir el archivo para escritura ni se puede crear un archivo con el mismo nombre. Valor: 0x01  
  
 `_A_SUBDIR`  
 Subdirectorio. Valor: 0x10  
  
 `_A_SYSTEM`  
 Archivo de sistema. Generalmente no se ve con el comando DIR, a menos que use la opción /AS. Valor: 0x04  
  
 Varias constantes pueden combinarse con el operador OR (&#124;).  
  
## <a name="see-also"></a>Vea también  
 [Funciones de búsqueda de nombre de archivo](../c-runtime-library/filename-search-functions.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)