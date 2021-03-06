---
title: CDaoIndexInfo (estructura) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d8c98181a9ec049308d7b85e57c028740927cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo (Estructura)
El `CDaoIndexInfo` estructura contiene información sobre un objeto de índice definido para objetos de acceso a datos (DAO).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
struct CDaoIndexInfo {  
    CDaoIndexInfo();
*// Constructor  
    CString m_strName;  // Primary  
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
    short m_nFields;    // Primary  
    BOOL m_bPrimary;    // Secondary  
    BOOL m_bUnique;     // Secondary  
    BOOL m_bClustered;  // Secondary  
    BOOL m_bIgnoreNulls;                // Secondary  
    BOOL m_bRequired;   // Secondary  
    BOOL m_bForeign;    // Secondary  
    long m_lDistinctCount;              // All  
 *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};   
```  
  
#### <a name="parameters"></a>Parámetros  
 `m_strName`  
 Identifica inequívocamente el objeto de campo. Para obtener más información, vea el tema "Nombre de propiedad" en la Ayuda de DAO.  
  
 `m_pFieldInfos`  
 Un puntero a una matriz de [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) objetos que indica qué campos tabledef o conjunto de registros son campos de clave en un índice. Cada objeto identifica un campo en el índice. El orden de índice predeterminado es el ascendente. Un objeto de índice puede tener uno o varios de los campos que representan las claves de índice para cada registro. Estos pueden ser ascendente, descendente, o una combinación.  
  
 `m_nFields`  
 El número de campos que se almacenan en `m_pFieldInfos`.  
  
 *m_bPrimary*  
 Si la propiedad principal es **TRUE**, el objeto index representa un índice principal. Un índice principal consta de uno o varios campos que identifican de forma única todos los registros de una tabla en un orden predefinido. Dado que el campo de índice debe ser único, también se establece la propiedad Unique del objeto Index en **TRUE** en DAO. Si el índice principal consta de más de un campo, cada campo puede contener valores duplicados, pero cada combinación de valores de todos los campos indizados debe ser única. Un índice principal consta de una clave para la tabla y generalmente contiene los mismos campos que la clave principal.  
  
 Cuando se establece una clave principal para una tabla, la clave principal se define automáticamente como el índice principal de la tabla. Para obtener más información, vea los temas "Propiedad principal" y "Propiedad único" en la Ayuda de DAO.  
  
> [!NOTE]
>  Puede haber, como máximo, un índice principal en una tabla.  
  
 *m_bUnique*  
 Indica si un objeto index representa un índice único para una tabla. Si esta propiedad es **TRUE**, el objeto index representa un índice que es único. Un índice único consta de uno o más campos que organizan de forma lógica todos los registros de una tabla en un orden predefinido único. Si el índice consta de un campo, los valores de ese campo deben ser únicos para toda la tabla. Si el índice está formada por más de un campo, cada campo puede contener valores duplicados, pero cada combinación de valores de todos los campos indizados debe ser única.  
  
 Si se establecen tanto la Unique y Primary propiedades de un objeto de índice **TRUE**, el índice es único y principal: identifica de forma única todos los registros de la tabla en un orden lógico predefinido. Si la propiedad principal se establece en **FALSE**, el índice es un índice secundario. Los índices secundarios (claves y sin clave) organizan de forma lógica los registros en un orden predefinido sin que actúa como un identificador para los registros de la tabla.  
  
 Para obtener más información, vea los temas "Propiedad principal" y "Propiedad único" en la Ayuda de DAO.  
  
 *m_bClustered*  
 Indica si un objeto index representa un índice agrupado para una tabla. Si esta propiedad es **TRUE**, el objeto index representa un índice clúster; en caso contrario, no es así. Un índice clúster está formado por uno o más no son de clave que los campos que, juntas, organizar todos los registros de una tabla en un orden predefinido. Con un índice agrupado, los datos de la tabla se almacenan literalmente en el orden especificado por el índice clúster. Un índice agrupado proporciona un acceso eficiente a registros de una tabla. Para obtener más información, vea el tema "Property en clúster" en la Ayuda de DAO.  
  
> [!NOTE]
>  Se omite la propiedad Clustered para las bases de datos que utilizan el motor de base de datos de Microsoft Jet porque el motor de base de datos de Jet no admiten índices agrupados.  
  
 *m_bIgnoreNulls*  
 Indica si hay entradas de índice para los registros que tienen valores Null en sus campos de índice. Si esta propiedad es **TRUE**, los campos con valores Null no tienen una entrada de índice. Para realizar búsquedas de registros mediante un campo con mayor rapidez, puede definir un índice para el campo. Si permite entradas Null en un campo indizado y espera que muchas de las entradas sean Null, puede establecer la propiedad IgnoreNulls para el objeto index que **TRUE** para reducir la cantidad de espacio de almacenamiento que usa el índice. El valor de la propiedad IgnoreNulls y el valor de propiedad necesario determinan si un registro con un valor de índice Null tiene una entrada de índice, como se muestra en la tabla siguiente.  
  
|IgnoreNulls|Obligatorio|NULL en el campo de índice|  
|-----------------|--------------|-------------------------|  
|True|False|Valor null permitido; no se agregó ninguna entrada de índice.|  
|False|False|Valor null permitido; agregado una entrada de índice.|  
|True o False|True|Valor null que no se permiten; no se agregó ninguna entrada de índice.|  
  
 Para obtener más información, vea el tema "Propiedad IgnoreNulls" en la Ayuda de DAO.  
  
 `m_bRequired`  
 Indica si un objeto de índice DAO requiere un valor distinto de Null. Si esta propiedad es **TRUE**, el objeto de índice no permite un valor Null. Para obtener más información, vea el tema "Propiedad necesaria" en la Ayuda de DAO.  
  
> [!TIP]
>  Cuando se puede establecer esta propiedad para un objeto de índice DAO o de un objeto field (incluidos en un tabledef, el conjunto de registros o el objeto querydef), establece para el objeto de campo. Se comprueba la validez de la configuración de la propiedad para un objeto field antes de un objeto de índice.  
  
 *m_bForeign*  
 Indica si un objeto index representa una clave externa en una tabla. Si esta propiedad es **TRUE**, el índice representa una clave externa en una tabla. Una clave externa se compone de uno o más campos de una tabla externa que identifican de forma única una fila de una tabla principal. El motor de base de datos de Microsoft Jet crea un objeto de índice para la tabla externa y establece la propiedad externa cuando se crea una relación que exige la integridad referencial. Para obtener más información, vea el tema "Propiedad externa" en la Ayuda de DAO.  
  
 *m_lDistinctCount*  
 Indica el número de valores únicos para el objeto index que se incluyen en la tabla asociada. Compruebe la propiedad DistinctCount para determinar el número de valores únicos, o claves, en un índice. Cualquier tecla se cuenten una sola vez, aunque puede haber varias repeticiones de ese valor si el índice permite valores duplicados. Esta información es útil en aplicaciones que intentan optimizar el acceso a datos mediante la evaluación de la información del índice. El número de valores únicos es también conocida como la cardinalidad de un objeto de índice. La propiedad DistinctCount no reflejará siempre el número real de claves en un momento determinado. Por ejemplo, un cambio causado por la reversión de una transacción no se reflejarán inmediatamente en la propiedad DistinctCount. Para obtener más información, vea el tema "DistinctCount (propiedad)" en la Ayuda de DAO.  
  
## <a name="remarks"></a>Comentarios  
 Las referencias a principal, secundaria y todo lo anterior indican cómo se devuelve la información de la `GetIndexInfo` función miembro en clases [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) y [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Objetos de índice no están representados por una clase de MFC. En su lugar, DAO objetos objetos MFC subyacentes de la clase [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) o [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) contienen una colección de objetos de índice, llamado a la colección de índices. Estas clases proporcionan funciones de miembro para tener acceso a elementos individuales de la información de índice, o puede tener acceso a ellos a la vez con un `CDaoIndexInfo` objeto mediante una llamada a la `GetIndexInfo` función de miembro del objeto contenedor.  
  
 `CDaoIndexInfo` tiene un constructor y un destructor con el fin de asignar y cancelar la asignación de la información de campo de índice en correctamente `m_pFieldInfos`.  
  
 La información recuperada por la `GetIndexInfo` función miembro de un objeto de definición de tabla se almacena en un `CDaoIndexInfo` estructura. Llame a la `GetIndexInfo` función de miembro del objeto contenedor tabledef en cuya colección de índices se almacena el objeto de índice. `CDaoIndexInfo` También define un `Dump` compila la función miembro en versiones de depuración. Puede usar `Dump` para volcar el contenido de un `CDaoIndexInfo` objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdao.h  
  
## <a name="see-also"></a>Vea también  
 [Estructuras, estilos, devoluciones de llamada y mapas de mensajes](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)

