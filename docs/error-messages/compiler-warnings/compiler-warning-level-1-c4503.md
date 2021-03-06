---
title: Compilador advertencia (nivel 1) C4503 | Documentos de Microsoft
ms.custom: ''
ms.date: 05/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f60fdb44c5368ccc5c5f089002614332d95a63fe
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-warning-level-1-c4503"></a>Advertencia del compilador (nivel 1) C4503

> '*identificador*': superada, la longitud del nombre representativo nombre se ha truncado

## <a name="remarks"></a>Comentarios

Esta advertencia del compilador está obsoleta y no se genera en Visual Studio de 2017 y compiladores más adelante.

El nombre representativo es mayor que el límite del compilador (4096) y se ha truncado. Para evitar esta advertencia y el truncamiento, reduzca el número de argumentos o la longitud de nombre de identificadores que usa. Nombres de los que ya que el límite del compilador tienen un valor hash que se aplican y no están en riesgo de un conflicto de nombres representativos.

Cuando se usa una versión anterior de Visual Studio, puede generarse esta advertencia cuando el código contiene plantillas especializadas en plantillas repetidamente. Por ejemplo, un mapa de mapas (de la biblioteca estándar de C++). En esta situación, puede que las definiciones de tipos un tipo (un **struct**, por ejemplo) que contiene el mapa.

Sin embargo, podría decidir que no reestructurar el código.  Es posible distribuir una aplicación que genera la advertencia C4503, pero si se producen errores en tiempo de vínculo en un símbolo truncado, puede resultar más difícil determinar el tipo del símbolo en el error. Depurar también puede resultar más difícil; el depurador puede tener dificultades para asignar el nombre del símbolo para el nombre de tipo. La corrección del programa, sin embargo, se ve afectada por el nombre truncado.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C4503 en compiladores antes de 2017 de Visual Studio:

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

Este ejemplo muestra una manera de volver a escribir el código para resolver la advertencia C4503:

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```