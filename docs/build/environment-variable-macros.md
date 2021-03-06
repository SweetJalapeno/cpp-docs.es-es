---
title: Macros de variables de entorno | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ebebb6e7d237746f96c7ac7e27c249244ff825b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="environment-variable-macros"></a>Macros de variables de entorno
NMAKE hereda definiciones de macro para variables de entorno que existían antes del inicio de la sesión. Si se establece una variable en el entorno de sistema operativo, está disponible como una macro NMAKE. Los nombres heredados se convierten a mayúsculas. Herencia tiene lugar antes del preprocesamiento. Utilice la opción /E para hacer que las macros heredadas de variables de entorno reemplacen las macros con el mismo nombre en el archivo MAKE.  
  
 Macros de variables de entorno se pueden volver a definir en la sesión y esta acción cambia la variable de entorno correspondiente. También puede cambiar las variables de entorno con el comando SET. Usar el comando SET para cambiar una variable de entorno en una sesión no cambia la macro correspondiente, sin embargo.  
  
 Por ejemplo:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 En este ejemplo, cambiar `PATH` modifica la variable de entorno correspondiente `PATH`; que se anexe `\nonesuch` a la ruta de acceso.  
  
 Si una variable de entorno se define como una cadena que sería sintaxis incorrecta en un archivo MAKE, se crea ninguna macro y no se genera ninguna advertencia. Si el valor de una variable contiene un signo de dólar ($), NMAKE lo interpreta como el principio de una llamada de macro. Con la macro puede provocar un comportamiento inesperado.  
  
## <a name="see-also"></a>Vea también  
 [Macros NMAKE especiales](../build/special-nmake-macros.md)