---
title: Error del compilador C2356 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2356
dev_langs:
- C++
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9dfb13f388c6c40c6c1853ab8e87b2e39edbc1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2356"></a>Error del compilador C2356
el segmento de inicialización no debe cambiar durante la unidad de traducción  
  
 Causas posibles:  
  
-   `#pragma init_seg` precedido por código de inicialización de segmento  
  
-   `#pragma init_seg` precedido por otro `#pragma init_seg`  
  
 Para resolver, mueva el código de inicialización del segmento al principio del módulo. Si se deben inicializar con varias áreas de moverlos a módulos separados.  
  
 El ejemplo siguiente genera C2356:  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```