---
title: NULL (Instrucción) (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72e120fa412481a8313809bd5cdaf748de498bde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="null-statement-c"></a>NULL (Instrucción) (C)
Una "instrucción null" es una instrucción que solo contiene un punto y coma; puede aparecer en cualquier lugar donde se espere una instrucción. No ocurre nada cuando se ejecuta una instrucción null. La manera correcta de escribir una instrucción null es:  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
;  
  
```  
  
## <a name="remarks"></a>Comentarios  
 Las instrucciones como **do**, **for**, **if** y `while` requieren que aparezca una instrucción ejecutable como cuerpo de la instrucción. La instrucción null cumple el requisito sintáctico en los casos en que no se necesita un cuerpo de instrucción sustancial.  
  
 Como con cualquier otra instrucción de C, puede incluir una etiqueta delante de una instrucción null. Para etiquetar un elemento que no es una instrucción, como la llave de cierre de una instrucción compuesta, puede etiquetar una instrucción null e insertarla inmediatamente delante del elemento para obtener el mismo efecto.  
  
 En este ejemplo se ilustra la instrucción null:  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 En este ejemplo, la expresión de bucle de la instrucción **for** `line[i++] = 0` inicializa los 10 primeros elementos de `line` en 0. El cuerpo de la instrucción es una instrucción null, ya que no se requieren más instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones](../c-language/statements-c.md)