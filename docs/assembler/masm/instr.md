---
title: INSTR | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- InStr
dev_langs:
- C++
helpviewer_keywords:
- INSTR directive
ms.assetid: fc37f6a2-3c95-47b2-b6bb-1066edd25994
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dd640aafe78f99f50d98569792d0c1c5ef330ee
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="instr"></a>INSTR
Busca la primera aparición de *textitem2* en *textitem1*.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
name  
 INSTR [[position,]] textitem1, textitem2  
```  
  
## <a name="remarks"></a>Comentarios  
 El inicio *posición* es opcional. Cada elemento de texto puede ser una cadena literal, una constante precedida por un `%`, o la cadena devuelta por una función de macro.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de directivas](../../assembler/masm/directives-reference.md)