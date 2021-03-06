---
title: Mover y copiar menús y comandos de menú | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, copying on menus
- menu items, moving
- commands, moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0da935ebdce7de61d5ed6b1a816f87b7cef7ce98
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>Mover y copiar menús y comandos de menú
Puede mover o copiar menús y comandos de menú mediante el método de arrastrar y colocar o usando los comandos del menú contextual (menú que se abre al hacer clic con el botón derecho).  
  
### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>Para mover o copiar menús o comandos de menú mediante el método de arrastrar y colocar  
  
1.  Arrastre o copie el elemento que desee mover a:  
  
    -   Una nueva ubicación en el menú actual.  
  
    -   Otro menú. (Puede navegar a otros menús arrastrando el puntero del mouse sobre ellos).  
  
2.  Arrastre el comando de menú cuando la guía de inserción muestre la posición que desee.  
  
### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>Para mover o copiar menús o comandos de menú mediante los comandos de menú contextual  
  
1.  Haga clic con el botón derecho en uno o varios menús o comandos de menú.  
  
2.  En el menú contextual, elija **Cortar** (para mover) o **Copiar**.  
  
3.  Si va a mover los elementos a otro recurso de menú o archivo de script de recursos, [ábralo en otra ventana](/visualstudio/ide/customizing-window-layouts-in-visual-studio).  
  
4.  Seleccione la posición del menú o comando de menú al que desee mover o copiar.  
  
5.  En el menú contextual, elija **Pegar**. El elemento movido o copiado se coloca antes del elemento que seleccione.  
  
    > [!NOTE]
    >  También puede arrastrar, copiar y pegar en otros menús de otras ventanas de menú.  
  
 Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [recursos en aplicaciones de escritorio](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework.* . Para información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, cómo obtener acceso a recursos, cómo mostrar recursos estáticos y cómo asignar cadenas de recursos a propiedades, vea [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Requisitos**  
  
 Win32  
  
## <a name="see-also"></a>Vea también  
 [Editor de menús](../windows/menu-editor.md)