---
title: Las herramientas del vinculador LNK4204 advertencia | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f000fa42357a299c943eda0cd5f8697aee138f4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4204"></a>Advertencia de las herramientas del vinculador LNK4204
'filename' falta información de depuración para hacer referencia al módulo; se vinculará el objeto sin información de depuración  
  
 El archivo .pdb tiene una firma errónea. El vinculador continuará vinculando el objeto sin información de depuración. Puede que desee volver a compilar el archivo de objeto mediante la [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) opción.  
  
 LNK4204 puede producirse si algunos de los objetos de la biblioteca hacen referencia a un archivo que ya no existe. Esto puede ocurrir al volver a generar la solución, por ejemplo; un archivo de objeto se puede eliminar y no vuelve a generar debido a un error de compilación. En este caso, tendrá que compilar con **/Z7**, o **/Fd**para actualizar los objetos para hacer referencia a una único archivo por biblioteca (que no sea el nombre de archivo .pdb predeterminado).  Para obtener más información, consulte [/Fd (Nombre del archivo de base de datos del programa)](../../build/reference/fd-program-database-file-name.md).  Asegúrese de que el archivo .pdb se guarda con la biblioteca cada vez que se actualiza en el sistema de control de código fuente.