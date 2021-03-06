---
title: Error PRJ0016 al compilar del proyecto | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6184e5bb251a2b74e8500cc195a38f2d814c1b5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0016"></a>Error PRJ0016 al compilar el proyecto
Configuración de seguridad del usuario impide que el proceso que se está creando. Esta configuración es necesaria para la compilación.  
  
 Se registran como un usuario que no tiene permisos para crear procesos mediante un proceso. Debe cambiar los niveles de permiso para esta cuenta de usuario o póngase en contacto con el Administrador de cuentas.  
  
 Este error también puede producirse si se establece la clave del registro siguiente:  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 Para resolver este error, elimine la clave RestrictRun. Si esta clave del registro es necesaria, anexe **vcspawn.exe** a la lista de entradas de la clave.  
  
 Otra causa de este error es que la configuración de directivas no incluye VCSpawn.exe en la clave del Registro HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun como programa de Windows permitido para esta cuenta de usuario.  
  
 Para obtener más información, vea:  
  
-   Artículo de Knowledge Base 324153, que está disponible en [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Cumplir con la configuración de directiva de sistema](http://msdn.microsoft.com/library/aa372139), la sección en "Ejecutar sólo aplicaciones permitidas de Windows".