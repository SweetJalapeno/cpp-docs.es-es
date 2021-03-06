---
title: Reemplazar una función Virtual (Visual C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-a-virtual-function-visual-c"></a>Reemplazar una función virtual (Visual C++)
Puede reemplazar las funciones virtuales definidas en una clase base desde Visual Studio [ventana propiedades](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Para reemplazar una función virtual en la ventana Propiedades  
  
1.  En la vista de clases, haga clic en la clase.  
  
2.  En la ventana Propiedades, haga clic en el **invalida** botón.  
  
    > [!NOTE]
    >  El **invalida** botón está disponible cuando se selecciona el nombre de clase en la vista de clases o al hacer clic en la ventana de código fuente.  
  
     La columna izquierda enumera las funciones virtuales. Si el nombre de una función virtual también aparece en la columna derecha, ya se implementó una invalidación.  
  
3.  Si la función no posee ningún reemplazo, a continuación, haga clic en la celda en la columna derecha en la ventana Propiedades para mostrar el nombre sugerido de la función de invalidación como \<Agregar >*FuncName*.  
  
4.  Haga clic en el nombre sugerido para agregar código auxiliar para la función.  
  
5.  Para modificar una función de reemplazo, haga doble clic en el nombre de la función en la vista de clases y modifique el código en la ventana de código fuente.  
  
 Para quitar una invalidación, haga clic en el nombre de la función de reemplazo en la columna derecha y seleccione \<eliminar >*FuncName*. Se hace referencia a código de la función.  
  
## <a name="see-also"></a>Vea también  
 [Agregar funcionalidad con los asistentes para código](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Agregar una clase](../ide/adding-a-class-visual-cpp.md)   
 [Agregar una función miembro](../ide/adding-a-member-function-visual-cpp.md)   
 [Agregar una Variable miembro](../ide/adding-a-member-variable-visual-cpp.md)   
 [Controlador de mensajes MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navegar por la estructura de clases](../ide/navigating-the-class-structure-visual-cpp.md)