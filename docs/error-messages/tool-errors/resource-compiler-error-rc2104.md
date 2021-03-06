---
title: Error del compilador de recursos RC2104 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28beaad95cc33d8b014b22035f9ed641f1b6ab6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rc2104"></a>Error del compilador de recursos RC2104
palabra clave o nombre de clave sin definir: clave  
  
 La palabra clave o el nombre de clave especificados no se ha definido.  
  
 A menudo, este error se debe a un error de escritura en la definición del recurso o en el archivo de encabezado incluido. También puede deberse a que falta un archivo de encabezado.  
  
 Para corregir el problema, busque el archivo de encabezado que debe contener la palabra clave o el nombre de clave definidos y compruebe que se han incluido en el archivo de recursos, y que la palabra clave o el nombre de clave están escritos correctamente. Si el proyecto se creó con un encabezado precompilado y posteriormente lo eliminó, asegúrese de que el archivo de recursos sigue incluyendo los encabezados necesarios.  
  
 Para comprobar las palabras clave definidas y nombres de clave en el archivo de recursos, en Visual Studio, abra el **vista de recursos** ventana, en la barra de menús, elija **vista**, **vista de recursos**: y a continuación, abra el menú contextual para el archivo .rc y elija **símbolos de recursos** para ver la lista de símbolos definidos. Para modificar los encabezados incluidos, abra el menú contextual para el archivo .rc y elija **de inclusión de recursos**.  
  
 Si aparece este mensaje:  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 abra \MCL\MFC\Include\AfxRes.h y agregue esta directiva Include:  
  
```  
#include <winresrc.h>  
```