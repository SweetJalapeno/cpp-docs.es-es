---
title: Secuencias de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85cf817a4d50346b9d10a9a9d1bc27abb5904433
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="character-sequences"></a>Secuencias de caracteres
**ANSI 3.8.2** Asignación de secuencias de caracteres del archivo de código fuente  
  
 Las instrucciones de preprocesador utilizan el mismo juego de caracteres que las instrucciones del archivo de código fuente, con la excepción de que no se admiten secuencias de escape.  
  
 Así, para especificar una ruta de acceso para un archivo de inclusión, se usa una sola barra diagonal inversa:  
  
```  
#include "path1\path2\myfile"  
```  
  
 En el código fuente, se requieren dos barras diagonales inversas:  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>Vea también  
 [Preprocesar directivas](../c-language/preprocessing-directives.md)