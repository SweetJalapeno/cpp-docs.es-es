---
title: Compilador advertencia (nivel 1) C4274 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b941fc0cb32e268e33d3b0e1ae66079e8decaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4274"></a>Compilador advertencia (nivel 1) C4274
\#Ident omitida; Consulte la documentación de #pragma comment (exestr, 'string')  
  
 La `#ident` directiva, que inserta una cadena especificada por el usuario en el objeto o archivo ejecutable, ha quedado desusada. Por lo tanto, el compilador omite la directiva.  
  
> [!CAUTION]
>  Advertencia C4274 le aconsejará que use la [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md) directiva. Sin embargo, estos consejos está en desuso y se revisarán en una versión futura del compilador. Si usas el `#pragma` directiva, la herramienta del vinculador (LINK.exe) pasa por alto el registro de comentario producido por la directiva y emite la advertencia [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). En lugar de la `#ident` directiva, se recomienda que utilice una cadena de recurso de versión de archivo en la aplicación.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quitar el `#ident "` *cadena* `"` directiva.  
  
## <a name="see-also"></a>Vea también  
 [comentario) (C/C ++)](../../preprocessor/comment-c-cpp.md)   
 [Herramientas del vinculador LNK4229 de advertencia](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Trabajo con archivos de recursos](../../windows/working-with-resource-files.md)