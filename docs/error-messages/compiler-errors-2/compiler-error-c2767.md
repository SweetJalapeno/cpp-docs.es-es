---
title: Error de compilador Error C2767 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2767
dev_langs:
- C++
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5ac628d1e02c53b0ed0872873ef23ef708df982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2767"></a>Error C2767 de Error del compilador
administrado o incoherencia de dimensión de WinRTarray: se esperaban N argumentos n - se proporcionaron M  
  
 Una declaración de matriz administrada o de WinRT estaba mal formada. Para obtener más información, vea [Matriz](../../windows/arrays-cpp-component-extensions.md).  
  
 El siguiente ejemplo genera el error C2767 y muestra cómo corregirlo:  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```