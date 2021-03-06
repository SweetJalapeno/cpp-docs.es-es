---
title: Caracteres anchos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf20b58ad9343f1a90f07a7f4c07bccd397a5888
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="wide-characters"></a>Caracteres anchos
**ANSI 3.1.3.4** Valor de una constante de caracteres enteros que contiene más de un carácter o una constante de caracteres anchos que contiene más de un carácter multibyte  
  
 La constante de caracteres normales "ab" tiene el valor entero (int)0x6162. Cuando hay más de un byte, los bytes de lectura anteriores se desplazan a la izquierda según el valor de **CHAR_BIT** y el byte siguiente se compara mediante el operador OR bit a bit con los bits inferiores de **CHAR_BIT**. El número de bytes de la constante de caracteres multibyte no puede superar sizeof(int), que es 4 para el código de 32 bits de destino.  
  
 La constante de caracteres multibyte se lee como se indica arriba y se convierte en una constante de caracteres anchos mediante la función en tiempo de ejecución `mbtowc`. Si el resultado no es una constante de caracteres anchos válida, se produce un error. En cualquier caso, el número de bytes examinados por la función `mbtowc` se limita al valor de `MB_CUR_MAX`.  
  
## <a name="see-also"></a>Vea también  
 [Caracteres](../c-language/characters.md)