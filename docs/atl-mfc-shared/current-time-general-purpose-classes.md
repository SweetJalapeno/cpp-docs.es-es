---
title: 'Hora actual: Clases de propósito General | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec71cf76f859457aa76e69b57b58db3940e974da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="current-time-general-purpose-classes"></a>Hora actual: Clases de propósito General
El siguiente procedimiento muestra cómo crear un `CTime` objeto e inicializarlo con la hora actual.  
  
#### <a name="to-get-the-current-time"></a>Para obtener la hora actual  
  
1.  Asignar un `CTime` objeto, como se indica a continuación:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Sin inicializar `CTime` objetos no se inicializan con una hora válida.  
  
2.  Llame a la `CTime::GetCurrentTime` función para obtener la hora actual del sistema operativo. Esta función devuelve un `CTime` objeto que puede utilizarse para establecer el valor de `CTime`, como se indica a continuación:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     Puesto que `GetCurrentTime` es una función miembro estática desde la `CTime` (clase), debe calificar su nombre con el nombre de la clase y el operador de resolución de ámbito (`::`), `CTime::GetCurrentTime()`.  
  
 Por supuesto, los dos pasos descritos anteriormente se pueden combinar en una única instrucción del programa como sigue:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [Fecha y hora: Clases de propósito general](../atl-mfc-shared/date-and-time-general-purpose-classes.md)



