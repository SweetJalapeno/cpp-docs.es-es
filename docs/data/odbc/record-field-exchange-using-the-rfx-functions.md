---
title: 'Intercambio de campos de registros: Utilizar las funciones de RFX | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1f834f9f52c8d01dbd7eb3ff54b794afc11630ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Intercambio de campos de registros: Utilizar las funciones de RFX
Este tema explica cómo utilizar las llamadas de función RFX que componen el cuerpo de su `DoFieldExchange` invalidar.  
  
> [!NOTE]
>  En este tema se aplica a las clases derivadas de [CRecordset](../../mfc/reference/crecordset-class.md) qué masiva de filas no se ha implementado la obtención. Si se utiliza la obtención masiva de filas, se implementa el intercambio masivo de campos de registros (RFX masivo). RFX masivo es similar a RFX. Para entender las diferencias, vea [conjunto de registros: obtener registros de forma masiva (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Las funciones globales de RFX intercambian datos entre las columnas de los miembros de datos de origen y el campo de datos en el conjunto de registros. Escribir llamadas de función RFX en el conjunto de registros [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) función miembro. En este tema se describe brevemente las funciones y se muestra los tipos de datos para la cual RFX funciones están disponibles. [La nota técnica 43](../../mfc/tn043-rfx-routines.md) describe cómo escribir sus propias funciones RFX para tipos de datos adicionales.  
  
##  <a name="_core_rfx_function_syntax"></a> Sintaxis de funciones RFX  
 Cada función RFX toma tres parámetros (y algunos toman un cuarto o quinto parámetro opcional):  
  
-   Un puntero a un [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) objeto. Basta con pasar la `pFX` puntero pasado a `DoFieldExchange`.  
  
-   El nombre de la columna tal y como aparece en el origen de datos.  
  
-   El nombre del miembro de datos de campo correspondiente o miembro de datos de parámetro en la clase de conjunto de registros.  
  
-   (Opcional) En algunas de las funciones, la longitud máxima de la cadena o matriz que se va a transferir. El valor predeterminado es 255 bytes, pero puede cambiarlo. El tamaño máximo se basa en el tamaño máximo de un `CString` objeto: **INT_MAX** (2.147.483.647) bytes, pero probablemente encontrará límites en el controlador antes de que el tamaño.  
  
-   (Opcional) En el `RFX_Text` función, a veces se utiliza un quinto parámetro para especificar el tipo de datos de una columna.  
  
 Para obtener más información, vea las funciones RFX en [Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md) en el *Class Library Reference*. Para obtener un ejemplo de cuándo se puede hacer especial de los parámetros, consulte [conjunto de registros: obtener cálculos SUM y otros resultados agregados (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).  
  
##  <a name="_core_rfx_data_types"></a> Tipos de datos RFX  
 La biblioteca de clases proporciona funciones de RFX para transferir muchos tipos de datos diferentes entre el origen de datos y los conjuntos de registros. En la lista siguiente se resume las funciones de RFX por tipo de datos. En los casos en los que debe escribir sus propias llamadas de función RFX, seleccione una de estas funciones por tipo de datos.  
  
|Función|Tipo de datos|  
|--------------|---------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  

 Para obtener más información, consulte la documentación de funciones RFX en [Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md) en el *Class Library Reference*. Para obtener información acerca de cómo se asignan los tipos de datos de C++ a tipos de datos SQL, vea la tabla ANSI SQL datos tipos asignan a tipos de datos de C++ en [SQL: SQL y tipos de datos de C++ (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
## <a name="see-also"></a>Vea también  
 [Intercambio de campos de registros (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Intercambio de campos de registros: Funcionamiento de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Conjunto de registros: Parametrizar un conjunto de registros (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Conjunto de registros: Enlazar dinámicamente columnas de datos (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset (clase)](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange (clase)](../../mfc/reference/cfieldexchange-class.md)