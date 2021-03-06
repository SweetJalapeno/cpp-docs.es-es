---
title: Utilizar marcadores | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5aa16d5f2a3a02d0e9fd6bb3dd5de71494e81d4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-bookmarks"></a>Utilizar marcadores
Antes de abrir el conjunto de filas, se debe indicar al proveedor que desea usar marcadores. Para ello, establezca la **DBPROP_BOOKMARKS** propiedad **true** en conjunto de sus propiedades. El proveedor recupera los marcadores como columna cero, por lo que debe usar la macro especial `BOOKMARK_ENTRY` y `CBookmark` clase si está utilizando un descriptor de acceso estático. `CBookmark` es una clase de plantilla donde el argumento es la longitud en bytes del búfer del marcador. La longitud del búfer necesario para un marcador depende del proveedor. Si está utilizando el proveedor OLE DB de ODBC, como se muestra en el ejemplo siguiente, el búfer debe ser de 4 bytes.  
  
```  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_BOOKMARKS, true);  
  

CTable<CAccessor<CProducts>> product;  
product.Open(session, "Products", &propset);  
```  
  
 Si usa `CDynamicAccessor`, el búfer se asigna dinámicamente en tiempo de ejecución. En este caso, puede usar una versión especializada de `CBookmark` para el que no se especifica una longitud de búfer. Use la función `GetBookmark` para recuperar el marcador del registro actual, como se muestra en este ejemplo de código:  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
 Para obtener información sobre la compatibilidad con marcadores en proveedores, vea [compatibilidad del proveedor con los marcadores](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>Vea también  
 [Usar descriptores de acceso](../../data/oledb/using-accessors.md)