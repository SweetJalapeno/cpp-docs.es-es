---
title: Transacciones (acceso a datos MFC) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9dd531aee6ac8014f2ce47ddee7fc5f82e35a63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="transactions--mfc-data-access"></a>Transacciones (acceso a datos MFC)
El concepto de transacción se desarrolló para abordar los casos en que el estado resultante de la base de datos depende del éxito total de una serie de operaciones. Esto podría suceder debido a que las operaciones sucesivas pueden modificar el resultado de las operaciones anteriores. En estos casos, si se produce un error en una operación, el estado resultante puede ser indeterminado.  
  
 Para resolver este problema, las transacciones agrupan una serie de operaciones de tal forma que puede garantizarse la integridad del resultado final. Todas las operaciones deben tener éxito y confirmarse (es decir, escribirse en la base de datos); de lo contrario, se produce un error en toda la transacción. La cancelación de la transacción se denomina reversión. La reversión permite una recuperación de los cambios y devuelve la base de datos al estado previo a la transacción.  
  
 Por ejemplo, en una transacción bancaria automatizada, si transfiere dinero de la cuenta A a la cuenta B, la retirada de A y el depósito en B deben tener éxito para que los fondos se procesen correctamente; de lo contrario, la transacción producirá un error.  
  
 Una transacción debe tener las propiedades ACID, que representan lo siguiente:  
  
-   **Atomicidad** una transacción constituye una unidad atómica de trabajo y se ejecuta exactamente una vez; todo el trabajo se realiza o nada en absoluto.  
  
-   **Coherencia** una transacción mantiene la coherencia de datos, pues transforma un estado coherente de datos en otro estado coherente de datos. Los datos enlazados por una transacción deben conservarse semánticamente.  
  
-   **Aislamiento** una transacción es una unidad de aislamiento y cada una se produce aislada e independientemente de las transacciones simultáneas. Una transacción nunca debe ver las fases intermedias de otra transacción.  
  
-   **Durabilidad** una transacción es una unidad de recuperación. Si una transacción tiene éxito, sus actualizaciones persisten, incluso si el sistema se bloquea o se apaga. Si se produce un error en una transacción, el sistema permanece en el estado anterior a la confirmación de la transacción.  
  
 Puede admitir transacciones en OLE DB (consulte [admitir transacciones en OLE DB](../data/oledb/supporting-transactions-in-ole-db.md)) u ODBC (consulte [transacción (ODBC)](../data/odbc/transaction-odbc.md)).  
  
 Una transacción distribuida es una transacción que actualiza datos distribuidos, es decir, datos en más de un sistema de equipos en red. Si desea admitir transacciones en un sistema distribuido, debe utilizar ADO.NET en lugar de la compatibilidad con transacciones de OLE DB.  
  
## <a name="see-also"></a>Vea también  
 [Acceso a los datos de programación (MFC/ATL)](../data/data-access-programming-mfc-atl.md)