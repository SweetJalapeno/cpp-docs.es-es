---
title: C2036 de Error del compilador | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2036
dev_langs:
- C++
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 244d99635585b21efc6218402277947eb265761e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2036"></a>C2036 de Error del compilador
'identificador': tamaño desconocido  
  
 Una operación en `identifier` requiere que el tamaño del objeto de datos, que no se puede determinar.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera C2036.  
  
```  
// C2036.c  
// a C program  
struct A* pA;  
struct B { int i; } *pB;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*)pA)++;   // OK  
  
   pB++;   // OK  
}  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera C2036.  
  
```  
// C2036_2.cpp  
// a C++ program  
struct A* pA;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)  
}  
```