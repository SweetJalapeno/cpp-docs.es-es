---
title: ¡Con IDispEventImpl (ATL) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 520d1129234a26ff6eb4c402154969ad7e166211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="using-idispeventimpl"></a>¡Con IDispEventImpl
Cuando se usa `IDispEventImpl` para controlar los eventos, deberá:  
  
-   Derive la clase de [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Agregue un mapa de receptores de eventos a la clase.  
  
-   Agregar entradas en el mapa de receptor de eventos mediante el [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) o [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) macro.  
  
-   Implemente los métodos que está interesado en el control.  
  
-   Aconsejar y desaconsejar el origen del evento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente muestra cómo controlar la **DocumentChange** eventos desencadenados por de Word **aplicación** objeto. Este evento se define como un método en el **ApplicationEvents** dispinterface.  
  
 El ejemplo está tomado del [ejemplo ATLEventHandling](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 El ejemplo se utiliza `#import` para generar los archivos de encabezado necesarios desde la biblioteca de tipos de Word. Si desea utilizar este ejemplo con otras versiones de Word, debe especificar el archivo mso dll correcto. Por ejemplo, Office 2000 proporciona mso9.dll y OfficeXP proporciona mso.dll. Este código se ha simplificado de stdafx.h:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 Aparece el siguiente código en NotSoSimple.h. El código relevante se anota mediante comentarios:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>Vea también  
 [Control de eventos](../atl/event-handling-and-atl.md)   
 [Ejemplo ATLEventHandling](../visual-cpp-samples.md)

