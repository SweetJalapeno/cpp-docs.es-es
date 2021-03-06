---
title: Directivas de preprocesamiento de archivos MAKE | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs:
- C++
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a84557388f521fb6c70c33ce6814ce33a5f6a1d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="makefile-preprocessing-directives"></a>Directivas de preprocesamiento de archivos MAKE
Las directivas de preprocesamiento no distinguen mayúsculas de minúsculas. El punto inicial de signo de exclamación (!) debe aparecer al principio de la línea. Cero o más espacios o tabulaciones pueden aparecer después del punto de exclamación, para la sangría.  
  
 **! CMDSWITCHES**  
 {**+** &#124; **-**}*opción*... Convierte a cada uno *opción* aparece activado o desactivado. Deben haber espacios ni tabulaciones antes el + o - operador. no pueden estar entre el operador y el [opción letras](../build/nmake-options.md). Letras no distinguen mayúsculas de minúsculas y se especifican sin una barra diagonal (/). Para activar unas opciones y desactivar otras, utilizar especificaciones independientes de **! CMDSWITCHES**.  
  
 Sólo/d, / I, /N y /S se pueden usar en un archivo MAKE. En Tools.ini, se admiten todas las opciones excepto/f, / Help, / nologo, / X, y /?. Cambios especificados en un bloque de descripción no surtirán efecto hasta el siguiente bloque de descripción. Esta directiva actualiza **MAKEFLAGS**; los cambios se heredan durante la recursividad si **MAKEFLAGS** se especifica.  
  
 **! ERROR***texto*   
 Muestra *texto* en error U1050 y después interrumpe NMAKE, aunque se utilicen/k, / I, **. OMITIR**, **! CMDSWITCHES**, o se utiliza el modificador de comando guión (-). Los espacios o tabulaciones antes *texto* se omiten.  
  
 **! MENSAJE***texto*   
 Muestra *texto* a la salida estándar. Los espacios o tabulaciones antes *texto* se omiten.  
  
 **! INCLUIR**[ **\<**] *filename*[ **>**]  
 Lee *filename* como un archivo MAKE, a continuación, continúa con el archivo MAKE actual. NMAKE busca *filename* primero en el directorio actual o especificado, a continuación, recursiva en los directorios de cualquier principal MAKE (archivos), a continuación, si *filename* está incluido entre corchetes angulares (\<>), en los directorios especificados por la **INCLUDE** macro, que inicialmente se establece en la variable de entorno INCLUDE. Es útil para pasar **. SUFIJOS** configuración, **. Muy VALIOSO**y las reglas de inferencia para archivos MAKE recursivos.  
  
 **! IF**  `constantexpression`  
 ¡Procesa instrucciones entre **! IF** y la siguiente instrucción **! ELSE** o `!ENDIF` si `constantexpression` se evalúa como un valor distinto de cero.  
  
 **! IFDEF***Nombredelamacro*   
 ¡Procesa instrucciones entre `!IFDEF` y la siguiente instrucción **! ELSE** o `!ENDIF` si *Nombredelamacro* está definido. Una macro null se considera que está definida.  
  
 **! IFNDEF***Nombredelamacro*   
 ¡Procesa instrucciones entre **! IFNDEF** y la siguiente instrucción **! ELSE** o `!ENDIF` si *Nombredelamacro* no está definido.  
  
 **! ELSE**[**IF** *constantexpression* &#124; **IFDEF** *Nombredelamacro* &#124; **IFNDEF**  *Nombredelamacro*]  
 ¡Procesa instrucciones entre **! ELSE** y el siguiente `!ENDIF` si anterior **! IF**, `!IFDEF`, o **! IFNDEF** instrucción que se evalúa como cero. Las palabras clave opcionales ofrecen un control de preprocesamiento.  
  
 **! ELSEIF**  
 Sinónimo de **! ELSE IF**.  
  
 **! ELSEIFDEF**  
 Sinónimo de **! ELSE IFDEF**.  
  
 **! ELSEIFNDEF**  
 Sinónimo de **! IFNDEF ELSE**.  
  
 `!ENDIF`  
 Marca el final de un **! IF**, `!IFDEF`, o **! IFNDEF** bloque. Cualquier texto situado tras `!ENDIF` se omite en la misma línea.  
  
 **! UNDEF***Nombredelamacro*   
 Anula la definición de *Nombredelamacro*.  
  
## <a name="see-also"></a>Vea también  
 [Preprocesamiento de archivos MAKE](../build/makefile-preprocessing.md)