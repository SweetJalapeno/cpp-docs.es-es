---
title: Las herramientas del vinculador LNK1106 Error | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3dedaa2bd500b11f06f9cfa98802fdd6ca84534
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1106"></a>Error de las herramientas del vinculador LNK1106
archivo no válido o disco lleno: no se puede buscar en ubicación  
  
 La herramienta no pudo leer o escribir en `location` en un archivo asignado a memoria.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Posibles causas del error:  
  
1.  Disco está lleno.  
  
     Libere espacio y volver a vincular.  
  
2.  Intentar vincular a través de una red.  
  
     Algunas redes no son totalmente compatibles con los archivos asignados a memoria utilizados por el vinculador. Intente vincular en el disco local.  
  
3.  Bloque no válido en el disco.  
  
     Aunque el sistema operativo y el hardware del disco deben ha detectado un error de este tipo, puede que desee ejecutar un programa de comprobación de disco.  
  
4.  Espacio de montón.  
  
     Vea [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) para obtener más información.