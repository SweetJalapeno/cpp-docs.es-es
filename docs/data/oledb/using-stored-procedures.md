---
title: Usar procedimientos almacenados | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e5b49daa44fc8c88316134915945ad7ee01bb81a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-stored-procedures"></a>Utilizar procedimientos almacenados
Un procedimiento almacenado es un objeto ejecutable almacenado en una base de datos. Llamar a un procedimiento almacenado es similar a invocar un comando SQL. Usar procedimientos almacenados en el origen de datos (en lugar de ejecutar o preparar una instrucción en la aplicación cliente) puede proporcionar varias ventajas, incluido un mayor rendimiento, tráfico de red reducido y coherencia mejorada y la precisión.  
  
 Un procedimiento almacenado puede tener cualquier número de (incluido cero) entrada o parámetros de salida y puede pasar un valor devuelto. Puede crear los valores de parámetro codificar de forma rígida como valores de datos específicos, o usar un marcador de parámetro (un signo de interrogación '?').  
  
> [!NOTE]
>  CLR de SQL Server los procedimientos almacenados creados con Visual C++ deben compilarse con la **/CLR: safe** opción del compilador.  
  
 El proveedor OLE DB para SQL Server (SQLOLEDB) admite los siguientes mecanismos que usan los procedimientos para devolver los datos almacenan:  
  
-   Cada instrucción SELECT del procedimiento genera un conjunto de resultados.  
  
-   El procedimiento puede devolver datos mediante parámetros output.  
  
-   El procedimiento puede tener un número entero código de retorno.  
  
> [!NOTE]
>  No se puede utilizar procedimientos almacenados con el proveedor OLE DB para Jet porque ese proveedor no admite procedimientos almacenados; sólo se permiten constantes en cadenas de consulta.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con plantillas de consumidor OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)