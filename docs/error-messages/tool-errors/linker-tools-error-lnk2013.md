---
title: Las herramientas del vinculador LNK2013 Error | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2013
dev_langs:
- C++
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9320b9ead0276b6fb5e1b9773260049a01520e12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2013"></a>Error de las herramientas del vinculador LNK2013
Desbordamiento de la corrección tipo de corrección. 'symbol name' de destino fuera del intervalo  
  
 El vinculador no puede ajustar la dirección o desplazamiento requeridos en la instrucción dada, porque el símbolo de destino se encuentra demasiado lejos de la ubicación de la instrucción.  
  
 Puede resolver este problema creando varias imágenes o usando la [/orden](../../build/reference/order-put-functions-in-order.md) opción por lo que la instrucción y el destino estén más cerca.  
  
 Cuando el nombre del símbolo es un símbolo definido por el usuario (y no uno generado por el compilador) también pueden probarse las siguientes acciones para resolver el error:  
  
-   Cambiar la función estática para que no sea estática.  
  
-   Cambiar el nombre de la sección de código que contiene la función estática para que sea el mismo que el de la sección que realiza la llamada.  
  
 Utilice `DUMPBIN /SYMBOLS` para ver si una función es estática.