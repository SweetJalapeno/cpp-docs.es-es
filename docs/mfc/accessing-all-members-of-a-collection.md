---
title: Obtener acceso a todos los miembros de una colección | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, collections
- enumerations [MFC]
- enumerating collections [MFC]
- collections [MFC], accessing
- collection classes [MFC]
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
ms.assetid: 7bbae518-062e-4393-81f9-b22abd2e5f59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec9757a463bce7ef873720f229b70da695deae8d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-all-members-of-a-collection"></a>Acceso a todos los miembros de una colección
Las clases de colección de matriz MFC —tanto basadas en plantillas como no— usan índices para obtener acceso a sus elementos. Las clases de colección de listas y mapas MFC (tanto basadas en plantillas como no) usan un indicador de tipo **POSITION** para describir una posición dada dentro de la colección. Para obtener acceso a uno o más miembros de estas colecciones, primero se inicializa el indicador de posición, después se pasa esa posición repetidamente a la colección y luego se le pide que devuelva el elemento siguiente. La colección no es responsable de mantener la información de estado sobre el progreso de la iteración. Esta información se guarda en el indicador de posición. Pero, en una posición concreta, la colección es responsable de devolver el elemento siguiente.  
  
 Los procedimientos siguientes muestran cómo iterar en los tres tipos principales de colecciones proporcionadas por MFC:  
  
-   [Recorrer en iteración una matriz](#_core_to_iterate_an_array)  
  
-   [Recorrer en iteración una lista](#_core_to_iterate_a_list)  
  
-   [Recorrer en iteración un mapa](#_core_to_iterate_a_map)  
  
### <a name="_core_to_iterate_an_array"></a> Para recorrer en iteración una matriz  
  
1.  Use números de índice secuenciales con la función miembro `GetAt` :  
  
     [!code-cpp[NVC_MFCCollections#12](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_1.cpp)]  
  
     Este ejemplo usa una matriz de puntero con tipo que contiene punteros a objetos `CPerson` . La matriz se deriva de la clase `CObArray`, una de las clases predefinidas no basadas en plantillas. `GetAt` devuelve un puntero a un objeto `CPerson` . Para las clases de colección de puntero con tipo (matrices o listas), el primer parámetro especifica la clase base; el segundo parámetro especifica el tipo para almacenar.  
  
     El `CTypedPtrArray` clase también sobrecargas el **[]** operador para que pueda utilizar la sintaxis habitual de subíndices de matriz para acceder a los elementos de una matriz. Una alternativa a la instrucción del cuerpo del bucle `for` anterior es  
  
     [!code-cpp[NVC_MFCCollections#13](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_2.cpp)]  
  
     Este operador existe en las versiones **const** y no**const** . La versión **const** , que se invoca para las matrices **const** , puede aparecer solo en el lado derecho de una instrucción de asignación.  
  
### <a name="_core_to_iterate_a_list"></a> Para recorrer en iteración una lista  
  
1.  Use las funciones miembro `GetHeadPosition` y `GetNext` para trabajar a su manera a través de la lista:  
  
     [!code-cpp[NVC_MFCCollections#14](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_3.cpp)]  
  
     Este ejemplo usa una lista de puntero con tipo que contiene punteros a objetos `CPerson` . La declaración de la lista es similar a la de la matriz en el procedimiento [Para recorrer en iteración una matriz](#_core_to_iterate_an_array) pero se deriva de la clase `CObList`. `GetNext` devuelve un puntero a un objeto `CPerson` .  
  
### <a name="_core_to_iterate_a_map"></a> Para recorrer en iteración un mapa  
  
1.  Use `GetStartPosition` para llegar al principio del mapa y `GetNextAssoc` para obtener repetidamente la clave y el valor siguiente del mapa, como se muestra en el siguiente ejemplo:  
  
     [!code-cpp[NVC_MFCCollections#15](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_4.cpp)]  
  
     Este ejemplo usa una plantilla de mapa sencilla (en lugar de una colección de puntero con tipo) que usa claves de `CString` y almacena punteros a objetos `CPerson` . Cuando usa las funciones de acceso como `GetNextAssoc`, la clase proporciona punteros a objetos `CPerson` . Si en su lugar usa una de las colecciones de mapa que no está basada en plantillas, debe convertir el puntero `CObject` devuelto en un puntero a un `CPerson`.  
  
    > [!NOTE]
    >  Para los mapas que no están basados en plantillas, el compilador requiere una referencia a un puntero `CObject` en el último parámetro para `GetNextAssoc`. En la entrada, debe convertir los punteros a ese tipo, como se muestra en el siguiente ejemplo.  
  
     La solución de plantilla es más sencilla y ayuda a proporcionar mejor seguridad de tipos. El código que no está basado en plantillas es más complicado, como puede ver aquí:  
  
     [!code-cpp[NVC_MFCCollections#16](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_5.cpp)]  
  
 Para obtener más información, vea [Eliminar todos los objetos de una colección CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md).  
  
## <a name="see-also"></a>Vea también  
 [Colecciones](../mfc/collections.md)

