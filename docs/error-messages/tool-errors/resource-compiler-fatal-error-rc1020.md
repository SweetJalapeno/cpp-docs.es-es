---
title: Error irrecuperable del compilador de recursos RC1020 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1020
dev_langs:
- C++
helpviewer_keywords:
- RC1020
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c90d3a5bb880ad10dcc4fb24d31fdc107f898840
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rc1020"></a>Error irrecuperable del compilador de recursos RC1020
'#endif' inesperada  
  
 Un `#endif` directiva aparece sin su correspondiente `#if`, **#ifdef**, o **#ifndef** directiva.  
  
 Asegúrese de que hay una coincidencia `#endif` para cada `#if`, **#ifdef**, y **#ifndef** instrucción.