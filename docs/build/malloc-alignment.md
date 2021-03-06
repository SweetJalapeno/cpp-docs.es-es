---
title: Alineación de malloc | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d503d0dd891c651a405cb79bb5ce50996f46cff6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="malloc-alignment"></a>Alineación de malloc
[malloc](../c-runtime-library/reference/malloc.md) se garantiza que devuelven memoria que es como correctamente alineado para almacenar cualquier objeto que tiene una alineación fundamental y que puede caber en la cantidad de memoria que se asigna. A *alineación fundamental* es una opción de alineación que es menor o igual que la alineación mayor que es compatible con la implementación sin una especificación de alineación. (En Visual C++, se trata de la alineación que se requiere para una `double`, u 8 bytes. En el código destinado a las plataformas de 64 bits, son 16 bytes). Por ejemplo, una asignación de cuatro bytes se alinearían en un límite que es compatible con cualquier objeto de cuatro bytes o más pequeño.  
  
 Visual C++ permite tipos que tienen *extendidos alineación*, que son también se denomina *exceso alineado* tipos. Por ejemplo, los tipos de SSE [__m128](../cpp/m128.md) y `__m256`y los tipos que se declaran mediante `__declspec(align( n ))` donde `n` es superior a 8, ha ampliado la alineación. No se garantiza la alineación de memoria en un límite que es adecuado para un objeto que requiere una alineación extendida por `malloc`. Para asignar memoria para los tipos de exceso alineados, utilice [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) y funciones relacionadas.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la pila](../build/stack-usage.md)   
 [Alinear](../cpp/align-cpp.md)   
 [__declspec](../cpp/declspec.md)