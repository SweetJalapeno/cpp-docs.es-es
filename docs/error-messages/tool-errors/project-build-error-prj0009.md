---
title: Error PRJ0009 al compilar del proyecto | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0009
dev_langs:
- C++
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5692ec643f5e3fe1adebf68048a6c435ab05d6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0009"></a>Error PRJ0009 al compilar el proyecto
Crear registro no se pudo abrir para escritura.  
  
 **Asegúrese de que el archivo no está abierto en otro proceso y no está protegida contra escritura.**  
  
 Después de establecer el **crear registro** propiedad **Sí** y llevar a cabo una compilación o recompilación, Visual C++ no pudo abrir el registro de compilación en modo exclusivo.  
  
 Inspeccionar el **crear registro** configuración abriendo el **opciones** cuadro de diálogo (en el **herramientas** menú, haga clic en **opciones** comando) y, a continuación, seleccionar **generación de VC ++** en el **proyectos** carpeta. El archivo de compilación se denomina BuildLog.htm y se escribe en el directorio intermedio $(IntDir).  
  
 Posibles razones para este error:  
  
-   Se ejecuta dos procesos de Visual C++ y trate de generar la misma configuración del mismo proyecto en ambos al mismo tiempo.  
  
-   Se abre el archivo de registro de compilación en un proceso que bloquea el archivo.  
  
-   El usuario no tiene permiso para crear un archivo.  
  
-   El usuario actual no tiene acceso de escritura al archivo BuildLog.htm.