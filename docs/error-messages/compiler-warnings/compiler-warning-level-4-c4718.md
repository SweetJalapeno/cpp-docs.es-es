---
title: Compilador advertencia (nivel 4) C4718 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a92ab7a32babd181f282c799568e3a9dea436c49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4718"></a>Advertencia del compilador (nivel 4) C4718
'llamada a función': la llamada recursiva no tiene efectos secundarios; se eliminará  
  
 Una función contiene una llamada recursiva, pero no tiene efectos secundarios. Se está eliminando una llamada a esta función. La precisión del programa no se ve afectada, pero sí el comportamiento. Dado que si se deja la llamada entrante podría producirse una excepción de desbordamiento de pila en tiempo de ejecución, la eliminación de la llamada evita esa posibilidad.