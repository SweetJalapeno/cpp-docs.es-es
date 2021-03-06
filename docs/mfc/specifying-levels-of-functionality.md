---
title: Especificar los niveles de funcionalidad | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f32b9502d2e8bd1c1483d817b759ca204f5c9c1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-levels-of-functionality"></a>Especificar los niveles de funcionalidad
Este artículo describe cómo agregar los siguientes niveles de funcionalidad a su [CObject](../mfc/reference/cobject-class.md)-clase derivada:  
  
-   [Información de clase en tiempo de ejecución](#_core_to_add_run.2d.time_class_information)  
  
-   [Compatibilidad con la creación dinámica](#_core_to_add_dynamic_creation_support)  
  
-   [Compatibilidad con la serialización](#_core_to_add_serialization_support)  
  
 Para obtener una descripción general de `CObject` funcionalidad, vea el artículo [derivar una clase de CObject](../mfc/deriving-a-class-from-cobject.md).  
  
-   [Información de clase en tiempo de ejecución](#_core_to_add_run.2d.time_class_information)  
#### <a name="_core_to_add_run.2d.time_class_information"></a> Para agregar información de clase en tiempo de ejecución  
  
1.  Derive la clase de `CObject`, tal y como se describe en el [derivar una clase de CObject](../mfc/deriving-a-class-from-cobject.md) artículo.  
  
2.  Use la `DECLARE_DYNAMIC` macro en la declaración de clase, como se muestra aquí:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]  
  
3.  Use la `IMPLEMENT_DYNAMIC` macro en el archivo de implementación (. CPP) de la clase. Esta macro toma como argumentos el nombre de la clase y su clase base, como se indica a continuación:  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  Colocar siempre `IMPLEMENT_DYNAMIC` en el archivo de implementación (. CPP) para la clase. El `IMPLEMENT_DYNAMIC` macro debe evaluarse una sola vez durante una compilación y, por tanto, no debe usarse en un archivo de interfaz (. (H) que podría potencialmente incluirse en más de un archivo.  
  
#### <a name="_core_to_add_dynamic_creation_support"></a> Para agregar compatibilidad con la creación dinámica  
  
1.  Derive la clase de `CObject`.  
  
2.  Use la `DECLARE_DYNCREATE` macro en la declaración de clase.  
  
3.  Defina un constructor sin argumentos (un constructor predeterminado).  
  
4.  Use la `IMPLEMENT_DYNCREATE` macro en el archivo de implementación de clase.  
  
#### <a name="_core_to_add_serialization_support"></a> Para agregar compatibilidad con la serialización  
  
1.  Derive la clase de `CObject`.  
  
2.  Invalidar el `Serialize` función miembro.  
  
    > [!NOTE]
    >  Si se llama a `Serialize` directamente, es decir, no desea serializar el objeto a través de un puntero polimórfico, omita los pasos 3 a 5.  
  
3.  Use la `DECLARE_SERIAL` macro en la declaración de clase.  
  
4.  Defina un constructor sin argumentos (un constructor predeterminado).  
  
5.  Use la `IMPLEMENT_SERIAL` macro en el archivo de implementación de clase.  
  
> [!NOTE]
>  Un "puntero polimórfico" apunta a un objeto de una clase (llama A) o a un objeto de cualquier clase derivada de una (por ejemplo, B). Para serializar a través de un puntero polimórfico, el marco de trabajo debe determinar la clase en tiempo de ejecución del objeto que se está serializando (B), puesto que puede ser un objeto de cualquier clase derivada de alguna clase base (A).  
  
 Para obtener más información acerca de cómo habilitar la serialización al derivar la clase de `CObject`, consulte los artículos [archivos en MFC](../mfc/files-in-mfc.md) y [serialización](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Vea también  
 [Derivación de una clase de CObject](../mfc/deriving-a-class-from-cobject.md)
