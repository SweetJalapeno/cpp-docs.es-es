---
title: Error del compilador C2512 | Documentos de Microsoft
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 286be19ca407039a77d51503a34c7a27da1c3d5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2512"></a>Error del compilador C2512

> '*identificador*': no hay disponible un constructor predeterminado adecuado  

A *constructor predeterminado*, un constructor que no requiere argumentos, no está disponible para la clase especificada, estructura o unión. El compilador proporciona un constructor predeterminado solo si no se proporciona ningún constructor definido por el usuario.

Si proporciona un constructor que toma un parámetro distinto de void y desea permitir que la clase que se creará sin parámetros (por ejemplo, que los elementos de una matriz), también debe proporcionar un constructor predeterminado. El constructor predeterminado puede ser un constructor con valores predeterminados para todos los parámetros.

## <a name="example"></a>Ejemplo

Una causa común de error error C2512 es al definir un constructor de clase o struct que acepta argumentos y, a continuación, intenta declarar una instancia de la clase o struct sin ningún argumento. Por ejemplo, `struct B` a continuación declara un constructor que requiere un `char *` argumento, pero no uno que no toma ningún argumento. En `main`, se declara una instancia de B, pero se proporciona ningún argumento. El compilador genera el error C2512 porque no se puede encontrar un constructor predeterminado para B.

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

Puede solucionar este problema mediante la definición de un constructor predeterminado para la estructura o clase, como `B() {}`, o un constructor donde todos los argumentos tienen valores predeterminados, como `B (char * = nullptr) {}`.
