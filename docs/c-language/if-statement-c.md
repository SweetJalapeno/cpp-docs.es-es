---
title: if (Instrucción) (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else
- if
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f307860ce71e8c9fc74b2ab97e88ced02e08332f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="if-statement-c"></a>if (Instrucción) (C)
La instrucción **if** controla la bifurcación condicional. El cuerpo de una instrucción **if** se ejecuta si el valor de la expresión es distinto de cero. La sintaxis de la instrucción **if** tiene dos formas.  
  
## <a name="syntax"></a>Sintaxis  
 *selection-statement*:  
 **if (**  *expression*  **)**  *statement*  
  
 **if (**  *expression*  **)**  *statement*  **else**  *statement*  
  
 En ambos formatos de la instrucción **if** se evalúan las expresiones, que pueden tener cualquier valor excepto una estructura, incluidos todos los efectos secundarios.  
  
 En la primera forma de sintaxis, si *expression* es true (distinta de cero), se ejecuta *statement*. Si *expression* es false, *statement* se ignora. En la segunda forma de sintaxis, que utiliza **else**, se ejecuta la segunda instancia de *statement* si *expression* es false. Con ambas formas, el control pasa entonces de la instrucción **if** a la siguiente instrucción del programa a menos que una de las instrucciones contenga **break**, **continue** o `goto`.  
  
 A continuación se muestran ejemplos de la instrucción **if**:  
  
```  
if ( i > 0 )  
    y = x / i;  
else   
{  
    x = i;  
    y = f( x );  
}  
```  
  
 En este ejemplo, la instrucción `y = x/i;` se ejecuta si `i` es mayor que 0. Si `i` es menor o igual que 0, `i` se asigna a `x` y `f( x )` se asigna a `y`. Observe que la instrucción que forma la cláusula **if** finaliza con un punto y coma.  
  
 Al anidar instrucciones **if** y cláusulas **else**, use llaves para agrupar las instrucciones y las cláusulas en instrucciones compuestas que clarifiquen su intención. Si no hay llaves presentes, el compilador resuelve las ambigüedades asociando cada cláusula **else** a la instrucción **if** más próxima que no tenga **else**.  
  
```  
if ( i > 0 )           /* Without braces */  
    if ( j > i )  
        x = j;  
    else  
        x = i;  
```  
  
 En este ejemplo, la cláusula **else** está asociada a la instrucción **if** interna. Si `i` es menor o igual que 0, no se asigna ningún valor a `x`.  
  
```  
if ( i > 0 )   
{                      /* With braces */  
    if ( j > i )  
        x = j;  
}  
else  
    x = i;  
```  
  
 Las llaves que rodean la instrucción **if** interna en este ejemplo componen la parte de la cláusula **else** de la instrucción **if** externa. Si `i` es menor o igual que 0, `i` se asigna a `x`.  
  
## <a name="see-also"></a>Vea también  
 [if-else (Instrucción) (C++)](../cpp/if-else-statement-cpp.md)