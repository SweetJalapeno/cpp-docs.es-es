---
title: 2.4.2 sections (construcción) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20b24c5b7d2458294da6280acb2ba7e8be5961fb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="242-sections-construct"></a>2.4.2 sections (Construcción)
El **secciones** directiva identifica una construcción noniterative de uso compartido que especifica un conjunto de construcciones que se va a dividir entre los subprocesos en un equipo. Cada sección se ejecuta una vez con un subproceso en el equipo. La sintaxis de la **secciones** directiva es como sigue:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 La cláusula es uno de los siguientes:  
  
 **private(** *variable-list* **)**  
  
 **firstprivate(** *variable-list* **)**  
  
 **lastprivate(** *variable-list* **)**  
  
 **reducción (** *operador* **:***lista de variables* **)**   
  
 **nowait**  
  
 Cada sección está precedido por un **sección** directiva, aunque la **sección** directiva es opcional para la primera sección. El **sección** directivas deben aparecer dentro de la extensión léxica de la **secciones** directiva. Hay una barrera implícita al final de un **secciones** construir, a menos que un **nowait** se especifica.  
  
 Restricciones a la **secciones** directiva son los siguientes:  
  
-   A **sección** directiva no debe aparecer fuera de la extensión léxica de la **secciones** directiva.  
  
-   Solo una **nowait** cláusula puede aparecer en un **secciones** directiva.  
  
## <a name="cross-references"></a>Referencias cruzadas:  
  
-   **privada**, **firstprivate**, **lastprivate**, y **reducción** cláusulas, vea [sección 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) en página 25.