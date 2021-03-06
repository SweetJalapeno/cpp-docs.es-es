---
title: Con la versión de depuración para comprobar si se ha sobrescrito memoria | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c89242a63484eaccd0330eddac28c4e543ec61b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Utilizar la versión de depuración para comprobar si se ha sobrescrito la memoria
Para usar la versión de depuración para comprobar si se ha sobrescrito de memoria, se debe recompilar el proyecto para la depuración. A continuación, ir al principio de la aplicación `InitInstance` funcione y agregue la siguiente línea:  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 El asignador de memoria de depuración coloca bytes de protección para todas las asignaciones de memoria. Sin embargo, estos bytes de protección no proporcionan ningún beneficio, a menos que se compruebe si se han cambiado (lo que podría indicar una sobrescritura en memoria). En caso contrario, esto simplemente proporciona un búfer que podría, de hecho, permitirle seguir adelante con una sobrescritura en memoria.  
  
 Activando el `checkAlwaysMemDF`, forzará MFC para realizar una llamada a la `AfxCheckMemory` cada vez que una llamada a la función para **nueva** o **eliminar** se realiza. Si se ha detectado una sobrescritura en memoria, generará un mensaje de seguimiento que tiene un aspecto similar al siguiente:  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Si ve alguno de estos mensajes, debe recorrer el código para determinar dónde se produjo el daño. Para aislar con mayor precisión dónde se produjo la sobrescritura de memoria, puede realizar llamadas explícitas a `AfxCheckMemory` usted mismo. Por ejemplo:  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 Si el primer ASSERT se realiza correctamente y la segunda se produce un error, significa que la sobrescritura en memoria debe haber ocurrido en la función entre las dos llamadas.  
  
 Según la naturaleza de la aplicación, es posible que `afxMemDF` hace que el programa se ejecute muy lentamente, incluso para pruebas. El `afxMemDF` variable hace `AfxCheckMemory` llamará para todas las llamadas a las nuevas y eliminar. En ese caso, debería separar sus propias llamadas a `AfxCheckMemory`() como se indicó anteriormente e intente aislar la memoria sobrescriben de ese modo.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas de versiones de lanzamiento](../../build/reference/fixing-release-build-problems.md)