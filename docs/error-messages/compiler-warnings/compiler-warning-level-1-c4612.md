---
title: Compilador advertencia (nivel 1) C4612 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0983f5d0bb89eaf1daee94468b318557bc83cd05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4612"></a>Advertencia del compilador (nivel 1) C4612
error en el nombre de archivo de inclusión  
  
 Esta advertencia se produce con **#pragma include_alias** cuando un nombre de archivo es incorrecto o falta.  
  
 Los argumentos de la **#pragma include_alias** instrucción puede usar las comillas (**"***filename***"**) o corchetes angulares ( **\< ***nombre de archivo***>**), pero ambos deben usar la misma forma.  
  
## <a name="example"></a>Ejemplo  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```