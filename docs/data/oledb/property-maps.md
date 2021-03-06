---
title: Mapas de propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d7664562ff31f1f5871fab4ce74c1652370a540d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="property-maps"></a>Mapas de propiedades
Además de la sesión, el conjunto de filas y el objeto de comando opcional, cada proveedor admite una o varias propiedades. Estas propiedades se definen en asignaciones de propiedad que contiene los archivos de encabezado creados por el Asistente para proveedores OLE DB. Cada archivo de encabezado contiene un mapa para las propiedades en el grupo de propiedades de OLE DB definido para el objeto u objetos definidos en ese archivo. El archivo de encabezado que contiene el objeto de origen de datos también contiene la asignación de propiedad para el [propiedades de origen de datos](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx). Session.h contiene la asignación de propiedad para el [propiedades de la sesión](https://msdn.microsoft.com/en-us/library/ms714221.aspx). Los objetos rowset y command residen en un archivo de encabezado único, denominado *projectname*RS.h. Estas propiedades son miembros de la [propiedades de conjunto de filas](https://msdn.microsoft.com/en-us/library/ms711252.aspx) grupo.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de plantillas de proveedores OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)