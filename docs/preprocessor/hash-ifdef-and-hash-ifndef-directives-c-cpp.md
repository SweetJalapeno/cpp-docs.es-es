---
title: '#Directivas ifdef e #ifndef (C/C ++) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a5ecfc9cc63fc4028e1f93d8f30e8d5cb9f9357
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef e #ifndef (Directivas) (C/C++)
El **#ifdef** y **#ifndef** directivas realizan la misma tarea que el `#if` directiva cuando se usa con **definido**( *identificador* ).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el **#ifdef** y **#ifndef** directivas en cualquier lugar `#if` puede utilizarse. El **#ifdef** *identificador* instrucción es equivalente a `#if 1` cuando *identificador* se ha definido, y es equivalente a `#if 0` cuando *identificador* no se ha definido o no se ha definido con el `#undef` directiva. Estas directivas solo comprueban la presencia o ausencia de identificadores definidos con `#define`, no comprueban los identificadores declarados en el código fuente de C o C++.  
  
 Estas directivas se proporcionan únicamente por compatibilidad con las versiones anteriores del lenguaje. El **definido (** *identificador* **)** expresión constante que se utiliza con el `#if` se prefiere la directiva.  
  
 El **#ifndef** directiva comprueba lo contrario de la condición que comprueba **#ifdef**. Si el identificador no se ha definido (o su definición se ha quitado con `#undef`), la condición es true (distinto de cero). De lo contrario, la condición es false (0).  
  
 **Específicos de Microsoft**  
  
 El *identificador* se puede pasar desde la línea de comandos con la opción/d. Se pueden especificar hasta 30 macros con /D.  
  
 Es útil para comprobar si existe una definición, porque una definición se puede pasar desde la línea de comandos. Por ejemplo:  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [Directivas de preprocesador](../preprocessor/preprocessor-directives.md)