---
title: Error irrecuperable C1084 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7266a2158c3e6ccd02ea82de22c6f90a8b6363d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1084"></a>Error irrecuperable C1084
No se puede leer el archivo tipodearchivo: 'archivo': mensaje  
  
 Este error suele deberse a un error en una llamada API del sistema interno realizada por el compilador. El mensaje se muestra cuando se produce este error se genera a menudo, ya sea [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) o [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx).  
  
 Con los siguientes pasos, puede que resulte más fácil resolver C1084:  
  
-   Compruebe que el archivo especificado existe.  
  
-   Compruebe que están establecidos los permisos adecuados para acceder al archivo especificado.  
  
-   Garantizar la sintaxis de línea de comandos se ajusta a las reglas que se describen en [sintaxis de línea de comandos del compilador](../../build/reference/compiler-command-line-syntax.md).  
  
-   Asegúrese de que las variables de entorno **TMP** y **TEMP** queden correctamente en conjunto, así como los permisos adecuados para tener acceso a los directorios consulte estas variables de entorno. Asegúrese también de que las unidades de disco al que hace referencia el **TMP** y **TEMP** variables de entorno contienen una cantidad suficiente de espacio libre.  
  
-   Si en el mensaje se indica “número de archivo incorrecto”, puede que el archivo especificado se estuviera cerrando en primer plano mientras se compilaba en segundo plano.  
  
 Después de llevar a cabo los diagnósticos anteriores, realice una compilación limpia.