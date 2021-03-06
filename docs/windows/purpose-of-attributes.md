---
title: Finalidad de los atributos | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ea3b731cc22d144e2e20dc70f14e6b0b76b1479
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="purpose-of-attributes"></a>Objetivo de los atributos
Atributos amplían C++ en direcciones no son actualmente posibles sin romper la estructura clásica del lenguaje. Los atributos permiten a proveedores (DLL independientes) para ampliar la funcionalidad del lenguaje dinámicamente. El objetivo principal de atributos es simplificar la creación de componentes COM, además de aumentar el nivel de productividad del desarrollador del componente. Atributos se pueden aplicar a casi cualquier construcción de C++, como clases, miembros de datos o funciones de miembro. A continuación se muestra un resaltado de beneficios que ofrece esta nueva tecnología:  
  
-   Expone una convención de llamada sencilla y conocida.  
  
-   Utiliza código insertado que, a diferencia de las macros, se reconoce el depurador.  
  
-   Permite derivar clases fácilmente de las clases base sin detalles pesados de la implementación.  
  
-   Reemplaza la gran cantidad de código IDL requerido por un componente COM con unos cuantos atributos concisos.  
  
 Por ejemplo, para implementar un simple receptor de eventos para una clase ATL genérica, podría aplicar la [event_receiver](../windows/event-receiver.md) atributo en una clase específica como `CMyReceiver`. El **event_receiver** , a continuación, se compila el atributo por el compilador de Visual C++, que inserta el código adecuado en el archivo de objeto.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 A continuación, puede configurar la **CMyReceiver** métodos `handler1` y `handler2` para controlar los eventos (mediante la función intrínseca [__hook](../cpp/hook.md)) desde un origen de eventos, que puede crear mediante [event_source](../windows/event-source.md).  
  
## <a name="see-also"></a>Vea también  
 [Conceptos](../windows/attributed-programming-concepts.md)