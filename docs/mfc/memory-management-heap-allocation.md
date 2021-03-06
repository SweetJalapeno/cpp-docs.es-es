---
title: 'Administración de memoria: Asignación de montones | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99df4a50f021e0981354a5d316606729bb824d94
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="memory-management-heap-allocation"></a>Administración de memoria: Asignación del montón
El montón está reservado para las necesidades de asignación de memoria del programa. Es un área además del código del programa y la pila. Los programas de C Typical utilizan las funciones `malloc` y **libre** para asignar y desasignar memoria del montón. La versión de depuración de MFC proporciona versiones modificadas de los operadores integrados de C++ **nueva** y **eliminar** para asignar y desasignar objetos en la memoria del montón.  
  
 Cuando usas **nueva** y **eliminar** en lugar de `malloc` y **libre**, puede aprovechar las ventajas de las mejoras de depuración de administración de memoria de la biblioteca de clases , que puede ser útil para detectar pérdidas de memoria. Al compilar el programa con la versión de lanzamiento de MFC, las versiones estándares de la **nueva** y **eliminar** operadores proporcionan una manera eficaz de asignar y desasignar memoria (la versión de lanzamiento de MFC no proporciona versiones modificadas de estos operadores).  
  
 Tenga en cuenta que el tamaño total de objetos asignados en el montón está limitado únicamente por la memoria virtual disponible de su sistema.  
  
## <a name="see-also"></a>Vea también  
 [Administración de memoria](../mfc/memory-management.md)

