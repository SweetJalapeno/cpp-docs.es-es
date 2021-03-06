---
title: Operadores de C | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f90f25d52a2555eb92938dd29ebb7e5bfc6e96a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="c-operators"></a>Operadores de C
Los operadores de C son un subconjunto de los [operadores integrados de C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md).  
  
 Hay tres tipos de operadores. Una expresión unaria consta de un operador unario antepuesto a un operando, o la palabra clave `sizeof` seguida de una expresión. La expresión puede ser el nombre de una variable o una expresión de conversión. Si la expresión es una expresión de conversión, se debe incluir entre paréntesis. Una expresión binaria consta de dos operandos unidos por un operador binario. Una expresión ternaria consta de tres operandos unidos por el operador de expresión condicional.  
  
 C incluye los operadores unarios siguientes:  
  
|Símbolo|nombre|  
|------------|----------|  
|**- ~ !**|Operadores de negación y complemento|  
|**\* &**|Operadores de direccionamiento indirecto y address-of|  
|`sizeof`|Operador de tamaño|  
|**+**|Operador unario más|  
|**++ --**|Operadores unarios de incremento y decremento|  
  
 Los operadores binarios se asocian de izquierda a derecha. C proporciona los operadores binarios siguientes:  
  
|Símbolo|nombre|  
|------------|----------|  
|**\* / %**|Operadores de multiplicación|  
|**+ -**|Operadores aditivos|  
|**<\< >>**|Operadores de desplazamiento|  
|**\<   >   \<=   >=   ==   !=**|Operadores relacionales|  
|**&   &#124; ^**|Operadores bit a bit|  
|**&&   &#124;&#124;**|Operadores lógicos|  
|**,**|Operador de evaluación secuencial|  
  
 El operador base(**:>**), compatible con las versiones anteriores del compilador de C de 16 bits de Microsoft, se describe en [Resumen de la sintaxis de lenguaje C](../c-language/c-language-syntax-summary.md).  
  
 El operador de expresión condicional tiene menos prioridad que las expresiones binarias y se diferencia de ellas en que es asociativo a la derecha.  
  
 Las expresiones con operadores también incluyen expresiones de asignación, que usan operadores de asignación unarios o binarios. Los operadores de asignación unarios son los operadores de incremento (`++`) y decremento (**--**); los operadores de asignación binarios son el operador de asignación simple (**=**) y los operadores de asignación compuesta. Cada operador de asignación compuesta es una combinación de otro operador binario con el operador de asignación simple.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones y asignaciones](../c-language/expressions-and-assignments.md)