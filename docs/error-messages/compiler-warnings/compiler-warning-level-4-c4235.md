---
title: Compilador advertencia (nivel 4) C4235 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc63640bc58caefa281b9207b9796ffdf387a7a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4235"></a>Advertencia del compilador (nivel 4) C4235
se ha utilizado una extensión no estándar : la palabra clave 'palabra clave' no se admite en esta arquitectura  
  
 El compilador aún no admite la palabra clave utilizada.  
  
 Esta advertencia suele convertirse automáticamente en un error. Si desea modificar este comportamiento, utilice [#pragma warning](../../preprocessor/warning.md). Por ejemplo, para convertir C4235 en una advertencia de nivel 2, utilice la siguiente línea de código  
  
```  
#pragma warning(2:4235)  
```  
  
 en el archivo de código fuente.