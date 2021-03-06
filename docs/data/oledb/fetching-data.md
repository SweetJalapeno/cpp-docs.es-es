---
title: Capturar datos | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab03da7c303552a715c6766af7829e74025866ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="fetching-data"></a>Obtener datos
Después de abrir el origen de datos, sesión y objetos de conjunto de filas, puede capturar datos. Según el tipo de descriptor de acceso que usa, tendrá que enlazar las columnas.  
  
### <a name="to-fetch-data"></a>Para capturar los datos  
  
1.  Abra el conjunto de filas con la correspondiente **abiertos** comando.  
  
2.  Si utilizas `CManualAccessor`, enlazar las columnas de salida si aún no lo ha hecho. Para enlazar las columnas, llame a `GetColumnInfo`y, a continuación, cree un descriptor de acceso con los enlaces, tal como se muestra en el ejemplo siguiente:  
  
    ```  
    // From the DBViewer Sample CDBTreeView::OnQueryEdit  
    // Get the column information  
    ULONG ulColumns       = 0;  
    DBCOLUMNINFO* pColumnInfo  = NULL;  
    LPOLESTR pStrings      = NULL;  
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)  
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);  
    struct MYBIND* pBind = new MYBIND[ulColumns];  
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);  
    for (ULONG l=0; l<ulColumns; l++)  
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);  
    rs.Bind();  
    ```  
  
3.  Escribir un `while` bucle para recuperar los datos. En el bucle, llame a `MoveNext` para avanzar el cursor y probar el valor devuelto con S_OK, como se muestra en el ejemplo siguiente:  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  En el `while` bucle, puede capturar los datos según el tipo de descriptor de acceso.  
  
    -   Si usas el [CAccessor](../../data/oledb/caccessor-class.md) (clase), debe tener un registro de usuario que contiene miembros de datos. Puede tener acceso a los datos mediante los miembros de datos, como se muestra en el ejemplo siguiente:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   Si usas el `CDynamicAccessor` o `CDynamicParameterAccessor` (clase), se pueden recuperar datos mediante el uso de las funciones de acceso `GetValue` y `GetColumn`, tal y como se muestra en el ejemplo siguiente. Si desea determinar el tipo de datos que usa, use `GetType`.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the dynamic accessor functions to retrieve your data.  
  
            ULONG ulColumns = rs.GetColumnCount();  
            for (ULONG i=0; i<ulColumns; i++)  
            {  
                rs.GetValue(i);  
            }  
        }  
        ```  
  
    -   Si usa `CManualAccessor`, debe especificar sus propios miembros de datos, enlazarlos personalmente y tener acceso a ellos directamente, como se muestra en el ejemplo siguiente:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con plantillas de consumidor OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)