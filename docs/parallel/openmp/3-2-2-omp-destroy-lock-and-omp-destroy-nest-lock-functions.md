---
title: 3.2.2 omp_destroy_lock y omp_destroy_nest_lock funciones | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33c21ec9ca07651480748ac705ea6b9e4dcf8e94
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock y omp_destroy_nest_lock (Funciones)
Estas funciones Asegúrese de que el apunta a la variable de bloqueo *bloqueo* no está inicializado. El formato es como se detalla a continuación:  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 No es conforme al llamar a cualquiera de estas rutinas con una variable de bloqueo que no se ha inicializado o desbloqueado.