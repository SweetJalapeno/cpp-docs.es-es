---
title: Error del compilador C3510 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abb58d8d4fb9008b07579ef7fbc0066d00bcea57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3510"></a>Error del compilador C3510
no se puede localizar el tipo dependiente 'biblioteca de tipos'  
  
 [no_registry](../../preprocessor/no-registry.md) y [auto_search](../../preprocessor/auto-search.md) se pasaron a `#import` , pero el compilador no pudo encontrar una biblioteca de tipos que se hace referencia.  
  
 Para resolver este error, asegúrese de que todas las bibliotecas de tipos y las bibliotecas de tipos que se hace referencia están disponibles para el compilador.  
  
 El ejemplo siguiente genera C3510:  
  
 Suponga que se crearon las siguientes dos bibliotecas de tipos, y que se eliminó C3510a.tlb o no en la ruta de acceso.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Y, a continuación, el código fuente para la segunda biblioteca de tipos:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Y, a continuación, el código de cliente:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```