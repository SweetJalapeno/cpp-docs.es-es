---
title: Declarar una Variable basada en la nueva clase de Control | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 677006d441c940f478b3d23744d1057667307e1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Declarar una variable basada en una clase de control nueva
Una vez haya creado una clase de control MFC, puede declarar una variable basada en él. Para proporcionar un contexto para la nueva variable, debe abrir el editor de cuadro de diálogo y editar el cuadro de diálogo en el que desea utilizar el control reutilizable. Además, el cuadro de diálogo ya debe tener una clase asociada a él. Para obtener información sobre cómo utilizar el editor de cuadro de diálogo, vea [Editor de cuadro de diálogo](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Para declarar una variable basada en una clase reutilizable  
  
1.  Mientras el cuadro de diálogo, arrastre un control del mismo tipo que la clase base del nuevo control desde la barra de herramientas de controles en el cuadro de diálogo.  
  
2.  Coloque el puntero del mouse sobre el control arrastrado.  
  
3.  Mientras se presiona la tecla CTRL, haga doble clic en el control.  
  
     El [agregar variables miembro](../../ide/add-member-variable-wizard.md) aparece el cuadro de diálogo.  
  
4.  En el **acceso** , seleccione el acceso correcto para el control.  
  
5.  Haga clic en el **la variable de Control** casilla de verificación.  
  
6.  En el **nombre de Variable** , escriba un nombre.  
  
7.  En **categoría**, haga clic en **Control**.  
  
8.  En el **Id. de Control** lista, elija el control que agregó. El **tipo de Variable** lista debe mostrar el tipo de variable correcto y el **tipo de Control** cuadro debe mostrar el tipo de control correcto.  
  
9. En el **comentario** , agregue cualquier comentario que desee que aparezca en el código.  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Asignar mensajes a funciones](../../mfc/reference/mapping-messages-to-functions.md)   
 [Agregar funcionalidad con los asistentes para código](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Agregar una clase](../../ide/adding-a-class-visual-cpp.md)   
 [Agregar una función miembro](../../ide/adding-a-member-function-visual-cpp.md)   
 [Agregar una Variable miembro](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Reemplazar una función Virtual](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Controlador de mensajes MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navegar por la estructura de clases](../../ide/navigating-the-class-structure-visual-cpp.md)
