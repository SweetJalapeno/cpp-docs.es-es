---
title: Tipos de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd26eea35da463211b144e98faa0636f5204f6f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="character-types"></a>Tipos de caracteres
Una constante de caracteres entera no precedida por la letra **L** tiene el tipo `int`. El valor de una constante de caracteres entera que contiene un carácter individual es el valor numérico del carácter interpretado como un entero. Por ejemplo, el valor numérico del carácter `a` es 97 en decimal y 61 en hexadecimal.  
  
 Sintácticamente, una "constante de caracteres anchos" es una constante de caracteres que tienen como prefijo la letra **L**. Una constante de caracteres anchos es de tipo `wchar_t`, un tipo entero definido en el archivo de encabezado STDDEF.H. Por ejemplo:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Las constantes de caracteres anchos tienen 16 bits de ancho y especifican miembros del juego de caracteres de ejecución extendidos. Permiten expresar caracteres en los alfabetos demasiado grandes para representarlos mediante el tipo `char`. Vea [Caracteres multibyte y anchos](../c-language/multibyte-and-wide-characters.md) para obtener más información sobre los caracteres anchos.  
  
## <a name="see-also"></a>Vea también  
 [Constantes de caracteres de C](../c-language/c-character-constants.md)