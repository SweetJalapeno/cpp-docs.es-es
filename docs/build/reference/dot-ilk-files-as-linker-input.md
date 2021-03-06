---
title: . ILK (archivos) como entrada del vinculador | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01fea585b86114373017b6d73948cb1438b7185e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ilk-files-as-linker-input"></a>Archivos .Ilk como entrada del vinculador
Al vincular de forma incremental, LINK actualiza el archivo de estado .ilk que creó durante la primera vinculación incremental. Este archivo tiene el mismo nombre base que el archivo .exe o .dll, y tiene la extensión .ilk. Durante posteriores vínculos incrementales, LINK actualiza el archivo .ilk. Si falta el archivo .ilk, LINK realizará un vínculo completo y crea un archivo .ilk nuevo. Si el archivo .ilk está inutilizable, LINK realizará un vínculo no incremental. Para obtener más información sobre la vinculación incremental, vea la [vínculo incremental (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) opción.  
  
## <a name="see-also"></a>Vea también  
 [Archivos de entrada de vínculo](../../build/reference/link-input-files.md)   
 [Opciones del vinculador](../../build/reference/linker-options.md)