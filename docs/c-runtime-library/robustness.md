---
title: Solidez | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b76235187bad83eb638588cbbd179e93523fdf2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="robustness"></a>Solidez

Use las siguientes funciones de la biblioteca en tiempo de ejecución de C para mejorar la solidez del programa.

## <a name="run-time-robustness-functions"></a>Funciones de solidez en tiempo de ejecución

|Función|Usar|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Transfiere el control al mecanismo de control de errores si el operador **new** no puede asignar memoria.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Controla las excepciones Win32 (excepciones estructuradas de C) como con excepciones con tipo de C++.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Instala su propia función de finalización a la que debe llamar [terminate](../c-runtime-library/reference/terminate-crt.md).|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Instala su propia función de finalización a la que debe llamar [unexpected](../c-runtime-library/reference/unexpected-crt.md).|

## <a name="see-also"></a>Vea también

[Rutinas en tiempo de ejecución Universal C por categoría](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
