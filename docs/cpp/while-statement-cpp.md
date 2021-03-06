---
title: while (instrucción) (C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f281007bea3f23bc8e7cebcdd68b9a306b500e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="while-statement-c"></a>while (Instrucción) (C++)
Ejecuta *instrucción* repetidamente hasta que *expresión* se evalúa como cero.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>Comentarios  
 La prueba de *expresión* tiene lugar antes de cada ejecución del bucle; por lo tanto, un `while` el bucle ejecuta cero o más veces. *expresión* debe ser de un tipo entero, un tipo de puntero, o un tipo de clase con una conversión no ambigua a un entero o un tipo de puntero.  
  
 A `while` bucle también puede finalizar cuando un [salto](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), o [devolver](../cpp/return-statement-cpp.md) dentro de la instrucción se ejecuta el cuerpo. Use [continuar](../cpp/continue-statement-cpp.md) para finalizar la iteración actual sin salir del `while` bucle. **continuar** pasa el control a la siguiente iteración de la `while` bucle.  
  
 En el código siguiente se utiliza un bucle `while` para recortar los caracteres de subrayado finales de una cadena:  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 La condición de finalización se evalúa al principio del bucle. Si no hay ningún carácter de subrayado final, el bucle nunca se ejecuta.  
  
## <a name="see-also"></a>Vea también  
 [Iteration Statements](../cpp/iteration-statements-cpp.md)  (Instrucciones de iteración)  
 [Palabras clave](../cpp/keywords-cpp.md)   
 [Instrucción do-while (C++)](../cpp/do-while-statement-cpp.md)   
 [for (Instrucción) (C++)](../cpp/for-statement-cpp.md)   
 [Instrucción for basada en intervalo (C++)](../cpp/range-based-for-statement-cpp.md)