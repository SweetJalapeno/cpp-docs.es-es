---
title: Inicializar tipos escalares | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef7356768a594694e0fcf3415c66ef63568a7cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="initializing-scalar-types"></a>Inicializar tipos escalares
Al inicializar tipos escalares, el valor de *assignment-expression* se asigna a la variable. Se aplican las reglas de conversión de la asignación. (Vea [Conversiones de tipos](../c-language/type-conversions-c.md) para obtener información sobre las reglas de conversión).  
  
## <a name="syntax"></a>Sintaxis  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt **;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list*  **,**  *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* Para la inicialización de valores escalares \*/  
  
 *initializer*:  
 *assignment-expression*  
  
 Puede inicializar variables de cualquier tipo, siempre que observe las reglas siguientes:  
  
-   Las variables declaradas en el nivel de ámbito de archivo se pueden inicializar. Si no inicializa explícitamente una variable en el nivel externo, se inicializa en 0 de forma predeterminada.  
  
-   Una expresión constante se puede utilizar para inicializar una variable global declarada con el especificador **storage-class-specifier** *static*. Las variables declaradas como **static** se inicializan cuando comienza la ejecución del programa. Si no inicializa explícitamente una variable global **static**, se inicializa en 0 de forma predeterminada y se asigna un puntero null a cada miembro que tenga el tipo de puntero.  
  
-   Las variables declaradas con el especificador de clase de almacenamiento **auto** o **register** se inicializan cada vez que el control en tiempo de ejecución pasa al bloque donde se declaran. Si omite un inicializador en la declaración de una variable **auto** o **register**, el valor inicial de la variable es indefinido. Para los valores auto y register, el inicializador no se limita a una constante; puede ser cualquier expresión que contenga valores definidos previamente, incluidas llamadas de función.  
  
-   Los valores iniciales de las declaraciones de variables externas y de todas las variables **static**, tanto sin son externas como internas, deben ser expresiones constantes. (Para obtener más información, vea [Expresiones constantes](../c-language/c-constant-expressions.md)). Como la dirección de cualquier variable definida externamente o variable estática es constante, se puede utilizar para inicializar una variable de puntero **static** declarada internamente. Sin embargo, la dirección de una variable **auto** no puede utilizarse como inicializador estático porque puede ser diferente en cada ejecución del bloque. Puede utilizar valores constantes o variables para inicializar las variables **auto** y **register**.  
  
-   Si la declaración de un identificador tiene ámbito de bloque y el identificador tiene vinculación externa, la declaración no puede tener una inicialización.  
  
## <a name="examples"></a>Ejemplos  
 En los siguientes ejemplos se muestran inicializaciones:  
  
```  
int x = 10;   
```  
  
 La variable de entero `x` se inicializa en la expresión constante `10`.  
  
```  
register int *px = 0;  
```  
  
 El puntero `px` se inicializa en 0, lo que genera un puntero "null".  
  
```  
const int c = (3 * 1024);  
```  
  
 En este ejemplo se utiliza una expresión constante `(3 * 1024)` para inicializar `c` en un valor constante que no se puede modificar debido a la palabra clave **const**.  
  
```  
int *b = &x;  
```  
  
 Esta instrucción inicializa el puntero `b` con la dirección de otra variable, `x`.  
  
```  
int *const a = &z;  
```  
  
 El puntero `a` se inicializa con la dirección de una variable denominada `z`. Sin embargo, como se especifica como una variable **const**, la variable `a` solo puede inicializarse, nunca modificarse. Siempre apunta a la misma ubicación.  
  
```  
int GLOBAL ;  
  
int function( void )  
{  
    int LOCAL ;  
    static int *lp = &LOCAL;   /* Illegal initialization */  
    static int *gp = &GLOBAL;  /* Legal initialization   */  
    register int *rp = &LOCAL; /* Legal initialization   */  
}  
```  
  
 La variable global `GLOBAL` se declara en el nivel externo, por lo que tiene duración global. La variable local `LOCAL` tiene una clase de almacenamiento **auto** y solo tiene una dirección durante la ejecución de la función en la que se declara. Por consiguiente, el intento de inicializar la variable de puntero **static** `lp` con la dirección de `LOCAL` no se permite. La variable de puntero **static** `gp` se puede inicializar en la dirección de `GLOBAL` porque esa dirección siempre es la misma. De igual forma, `*rp` se puede inicializar porque `rp` es una variable local y no puede tener un inicializador que no sea constante. Cada vez que se entra en el bloque, `LOCAL` tiene una nueva dirección, que se asigna a `rp`.  
  
## <a name="see-also"></a>Vea también  
 [Inicialización](../c-language/initialization.md)