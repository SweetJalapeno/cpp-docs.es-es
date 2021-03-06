---
title: 'Función CAtlServiceModuleT:: Run | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a07ad6b09fa10a81b500625531226dc18fc6281a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemoduletrun-function"></a>Función CAtlServiceModuleT:: Run
**Ejecutar** contiene las llamadas a `PreMessageLoop`, `RunMessageLoop`, y `PostMessageLoop`. Después de que se llama, `PreMessageLoop` almacena primero el identificador de subproceso. del servicio El servicio utilizará este identificador para cerrarse a sí mismo mediante el envío de un **WM_QUIT** mensaje cuando se utiliza la función API de Win32, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` a continuación, llama `InitializeSecurity`. De forma predeterminada, `InitializeSecurity` llamadas [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) con el descriptor de seguridad establecido en NULL, lo que significa que cualquier usuario tenga acceso al objeto.  
  
 Si no desea que el servicio para especificar su propia seguridad, reemplace `PreMessageLoop` y no llame a `InitializeSecurity`, y COM, a continuación, determinar la configuración de seguridad del registro. Es una manera cómoda de configuración del registro con el [DCOMCNFG](../atl/dcomcnfg.md) utilidad que se describe más adelante en esta sección.  
  
 Una vez especificada la seguridad, el objeto está registrado con COM para que los nuevos clientes puedan conectarse al programa. Por último, el programa indica al administrador de control de servicios (SCM) que se está ejecutando y el programa entra en un bucle de mensajes. El programa sigue ejecutándose hasta que envía un mensaje quit tras el cierre del servicio.  
  
## <a name="see-also"></a>Vea también  
 [Servicios de](../atl/atl-services.md)   
 [Clase de CSecurityDesc](../atl/reference/csecuritydesc-class.md)   
 [CSid (clase)](../atl/reference/csid-class.md)   
 [Clase CDacl](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT:: Run](../atl/reference/catlservicemodulet-class.md#run)

