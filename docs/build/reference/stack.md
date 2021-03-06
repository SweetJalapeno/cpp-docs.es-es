---
title: -PILA | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82111ce950d14bc6b3e270ee9a658d806b28b62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta opción establece el tamaño de la pila en bytes y toma argumentos en notación decimal o de lenguaje C. La opción /STACK sólo se aplica a un archivo ejecutable.  
  
 El *reservar* argumento especifica la asignación de pila total en la memoria virtual. EDITBIN redondeará el valor especificado a los 4 bytes más cercanos.  
  
 Opcional `commit` argumento está sujeto a interpretación por el sistema operativo. En Windows NT, Windows 95 y Windows 98, `commit` especifica la cantidad de memoria física para asignar a la vez. La memoria virtual confirmada hace que se reserve espacio en el archivo de paginación. Una mayor `commit` valor, ahorrará tiempo cuando la aplicación necesite más espacio de pila, pero aumentarán los requisitos de memoria y, posiblemente, tiempo de inicio.  
  
## <a name="see-also"></a>Vea también  
 [Opciones de EDITBIN](../../build/reference/editbin-options.md)