---
title: 'TN031: Barras de Control | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.bars
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], styles
- CStatusBar class [MFC], Tech Note 31 usage
- CControlBar class [MFC], Tech Note 31 usage
- CControlBar class [MFC], deriving from
- control bars [MFC], classes [MFC]
- CDialogBar class [MFC], Tech Note 31 usage
- CToolBar class [MFC], Tech Note 31 usage
- TN031
- styles [MFC], control bars
ms.assetid: 8cb895c0-40ea-40ef-90ee-1dd29f34cfd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1d5cc113177a9653e709c14f66682959276e7ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tn031-control-bars"></a>TN031: Barras de control
> [!NOTE]
>  La nota técnica siguiente no se ha actualizado desde que se incluyó por primera vez en la documentación en línea. Como resultado, algunos procedimientos y temas podrían estar obsoletos o ser incorrectos. Para obtener información más reciente, se recomienda buscar el tema de interés en el índice de la documentación en línea.  
  
 Esta nota describe las clases de barras de control en MFC: [CControlBar](#_mfcnotes_ccontrolbar), [CStatusBar](#_mfcnotes_cstatusbar), [CToolBar](#_mfcnotes_ctoolbar), [CDialogBar](#_mfcnotes_cdialogbar)y **CDockBar**.  
  
## <a name="_mfcnotes_ccontrolbar"></a> CControlBar 
  
 Una **ControlBar** es una clase derivada de `CWnd`que:  
  
-   Se alinea a la parte superior o inferior de una ventana marco.  
  
-   Puede contener elementos secundarios que son controles basados en HWND (por ejemplo, `CDialogBar`) o elementos basados en no`HWND` (por ejemplo, `CToolBar`, `CStatusBar`).  
  
 Las barras de control admiten los siguientes estilos adicionales:  
  
- `CBRS_TOP` (Valor predeterminado) Ancla la barra de control a la parte superior.  
  
- `CBRS_BOTTOM` Ancla la barra de control a la parte inferior.  
  
- `CBRS_NOALIGN` No cambia la posición de la barra de control cuando el elemento primario cambia de tamaño.  
  
 Las clases derivadas de `CControlBar` proporcionan implementaciones más interesantes:  
  
- `CStatusBar` Una barra de estado, los elementos son paneles de la barra de estado que contienen texto.  
  
- `CToolBar` Una barra de herramientas, los elementos son botones de mapa de bits alineados en una fila.  
  
- `CDialogBar` Un marco similar a una barra de herramientas que contiene controles de ventana estándar (creados a partir de un recurso de plantilla de cuadro de diálogo).  
  
- **CDockBar** Una zona de acoplamiento generalizada para otros objetos derivados de `CControlBar` . Es probable que las funciones miembro específicas y las variables disponibles en esta clase se modifiquen en versiones futuras.  
  
 Todas las ventanas y objetos de la barra de control serán ventanas secundarias de alguna ventana marco principal. Normalmente se agregan como un elemento relacionado con el área cliente del marco (por ejemplo, un cliente o una vista MDI). El identificador de la ventana secundaria de la barra de control es importante. El diseño predeterminado de la barra de control solo funciona para barras de control con identificadores en el intervalo de **AFX_IDW_CONTROLBAR_FIRST** a **AFX_IDW_CONTROLBAR_LAST**. Tenga en cuenta que aunque exista un intervalo de 256 identificadores de barras de control, los primeros 32 identificadores son especiales ya que la arquitectura de vista previa de impresión los admite directamente.  
  
 La clase `CControlBar` proporciona una implementación estándar para:  
  
-   Alinear la barra de control en la parte superior, inferior o a cualquier lado del marco.  
  
-   Asignar matrices de elementos de control.  
  
-   Admitir la implementación de clases derivadas.  
  
 Los objetos de la barra de control C++ normalmente se insertarán como miembros de una clase derivada `CFrameWnd` , y se borrarán cuando el elemento primario `HWND` y el objeto se destruyan. Si necesita asignar un objeto de barra de control en el montón, simplemente establezca el miembro **m_bAutoDestruct** en **TRUE** para que la barra de control pueda "**eliminar esto**" cuando `HWND` se destruya.  
  
> [!NOTE]
>  Si crea su propia clase derivada de `CControlBar`, en lugar de usar una de las clases derivadas de MFC, como `CStatusBar`, `CToolBar`o `CDialogBar`, necesitará establecer el miembro de datos `m_dwStyle` . Esto puede realizarse en el reemplazo de **Create**:  
  
```  
// CMyControlBar is derived from CControlBar  
BOOL CMyControlBar::Create(CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID)  
{  
    m_dwStyle = dwStyle;  
 
 .  
 .  
 .  
}  
```  
  
 **Algoritmo de diseño de la barra de control**  
  
 El algoritmo de diseño de la barra de control es muy sencillo. La ventana marco envía un mensaje **WM_SIZEPARENT** a todos los elementos secundarios en el intervalo de la barra de control. Junto con este mensaje, se pasa un puntero al rectángulo de cliente del elemento primario. Este mensaje se envía a los elementos secundarios en el orden Z. Los elementos secundarios de la barra de control usan esta información para colocarse y reducir el tamaño del área de cliente del elemento primario. El rectángulo final que queda para el área de cliente normal (menos barras de control) se usa para colocar la ventana de cliente principal (normalmente un cliente, una vista o una ventana divisora MDI).  
  
 Vea `CWnd::RepositionBars` y `CFrameWnd::RecalcLayout` para obtener más información.  
  
 Los mensajes de Windows privados de MFC, incluido **WM_SIZEPARENT**, están documentados en la [Nota técnica 24](../mfc/tn024-mfc-defined-messages-and-resources.md).  
  
## <a name="_mfcnotes_cstatusbar"></a>  CStatusBar  
  
 Una barra de estado es una barra de control que tiene una fila de paneles de salida de texto. Hay dos formas habituales de usar paneles de salida de texto:  
  
-   Como una línea de mensaje  
  
     (por ejemplo, la línea de mensaje de ayuda del menú estándar). Normalmente se accede a ellos mediante un indexado en 0  
  
-   Como indicadores de estado  
  
     (por ejemplo, los indicadores CAP, NUM y BLOQ DESPL). Normalmente se accede a ellos mediante el identificador de comando o cadena.  
  
 La fuente de la barra de estado es MS Sans Serif de 10 puntos (según la Guía de diseño de aplicaciones de interfaz de Windows o la mejor coincidencia de asignadores de fuente de una fuente proporcional Swiss de 10 puntos). En ciertas versiones de Windows, como la edición en japonés, las fuentes seleccionadas son diferentes.  
  
 Los colores usados en la barra de estado también son coherentes con la recomendación de la Guía de diseño de aplicaciones de interfaz de Windows. Estos colores no se codifican de forma rígida y se cambian dinámicamente en respuesta a la personalización del usuario en el Panel de Control.  
  
|Elemento|Valor COLOR de Windows|RGB predeterminado|  
|----------|-------------------------|-----------------|  
|Fondo de la barra de estado|**COLOR_BTNFACE**|RGB (192, 192, 192)|  
|Texto de la barra de estado|**COLOR_BTNTEXT**|RGB (000, 000, 000)|  
|Los bordes superior e izquierdo de la barra de estado|**COLOR_BTNHIGHLIGHT**|RGB (255, 255, 255)|  
|Los bordes inferior y derecho de la barra de estado|**COLOR_BTNSHADOW**|RGB (128, 128, 128)|  
  
 **Compatibilidad de CCmdUI con CStatusBar**  
  
 Los indicadores se actualizan normalmente a través del mecanismo de `ON_UPDATE_COMMAND_UI` . En tiempo de inactividad, la barra de estado llamará al controlador `ON_UPDATE_COMMAND_UI` con el identificador de cadena del panel de indicadores.  
  
 El controlador `ON_UPDATE_COMMAND_UI` puede llamar:  
  
- **Habilitar**: para habilitar o deshabilitar el panel. Un panel deshabilitado es exactamente igual que un panel habilitado pero el texto es invisible (es decir, se desactiva el indicador de texto).  
  
- **SetText**: para cambiar el texto. Tenga cuidado si usa esto porque el panel no cambiará de tamaño automáticamente.  
  
 Consulte la clase [CStatusBar](../mfc/reference/cstatusbar-class.md) en la *Referencia de biblioteca de clases* para obtener más información sobre la creación y personalización de las API de `CStatusBar` . La mayor parte de la personalización de las barras de estado debe realizarse antes de que la barra de estado se haga visible de forma inicial.  
  
 La barra de estado es compatible con un solo panel ajustable, normalmente, el primer panel. El tamaño de dicho panel es realmente un tamaño mínimo. Si la barra de estado es mayor que el tamaño mínimo de todos los paneles, se proporcionará cualquier ancho adicional al panel ajustable. La aplicación predeterminada con una barra de estado tiene indicadores alineados a la derecha para CAP, NUM y BLOQ DESPL, ya que el primer panel es ajustable.  
  
## <a name="_mfcnotes_ctoolbar"></a>  CToolBar  
  
 Una barra de herramientas es una barra de controles con una fila de botones de mapa de bits que pueden incluir separadores. Se admiten dos estilos de botones: pulsadores y botones de casilla. Se puede crear la funcionalidad de grupo de radio con botones de casilla y `ON_UPDATE_COMMAND_UI`.  
  
 Todos los botones de mapa de bits de la barra de herramientas proceden de un mapa de bits. Este mapa de bits debe contener una imagen o un glifo para cada botón. Normalmente, el orden de las imágenes o glifos en el mapa de bits es el mismo orden en que se dibujarán en la pantalla. (Esto se puede cambiar mediante las API de personalización).  
  
 Cada botón debe ser del mismo tamaño. El valor predeterminado es el valor estándar 24 x 22 píxeles. Cada glifo o imagen debe ser del mismo tamaño y debe estar en paralelo en el mapa de bits. El tamaño de la imagen o glifo predeterminado es 16 x 15 píxeles. Por lo tanto, para una barra de herramientas con 10 botones (con tamaños estándar), es necesario un mapa de bits de 160 píxeles de ancho y 15 píxeles de alto.  
  
 Cada botón solo tiene una imagen o glifo. Los diferentes estados y estilos del botón (por ejemplo, presionado, arriba, abajo, deshabilitado, deshabilitado hacia abajo, indeterminado) se generan de forma algorítmica desde una imagen o glifo. En teoría puede usar cualquier mapa de bits de color o DIB. El algoritmo para generar los diferentes estados del botón funciona mejor si la imagen original es de tonalidad gris. Examine los botones de la barra de herramientas estándar y las imágenes prediseñadas del botón de la barra de herramientas proporcionados en el ejemplo general de MFC [CLIPART](../visual-cpp-samples.md) para obtener ejemplos.  
  
 Los colores usados en la barra de herramientas también son coherentes con la recomendación de la Guía de diseño de aplicaciones de interfaz de Windows. Estos colores no se codifican de forma rígida y se cambian dinámicamente en respuesta a la personalización del usuario en el Panel de Control.  
  
|Elemento|Valor COLOR de Windows|RGB predeterminado|  
|----------|-------------------------|-----------------|  
|Fondo de la barra de herramientas|**COLOR_BTNFACE**|RGB (192,192,192)|  
|Bordes superior e izquierdo de los botones de la barra de herramientas|**COLOR_BTNHIGHLIGHT**|RGB (255,255,255)|  
|Bordes inferior y derecho de los botones de la barra de herramientas|**COLOR_BTNSHADOW**|RGB (128,128,128)|  
  
 Además, se han vuelto a colorear los botones de mapa de bits de la barra de herramientas como si se tratara de controles de botón estándar de Windows. Esta recoloración se produce cuando se carga el mapa de bits del recurso y en respuesta a un cambio en los colores del sistema debido a la personalización del usuario en el Panel de Control. Los colores siguientes de un mapa de bits de barra de herramientas se volverán a colorear automáticamente, por lo que se deben usar con precaución. Si no quiere que una parte del mapa de bits se vuelva a colorear, use un color que se asemeje a uno de los valores RGB asignados. La asignación se realiza basándose en los valores RGB exactos.  
  
|Valor RGB|Valor COLOR asignado dinámicamente|  
|---------------|------------------------------------|  
|RGB (000, 000, 000)|COLOR_BTNTEXT|  
|RGB (128, 128, 128)|COLOR_BTNSHADOW|  
|RGB (192, 192, 192)|COLOR_BTNFACE|  
|RGB (255, 255, 255)|COLOR_BTNHIGHLIGHT|  
  
 Consulte la clase [CToolBar](../mfc/reference/ctoolbar-class.md) en la *Referencia de biblioteca de clases* para obtener más información sobre la creación y personalización de las API de `CToolBar` . La mayor parte de la personalización de las barras de herramientas debe realizarse antes de que la barra de herramientas se haga inicialmente visible.  
  
 La personalización de las API pueden usarse para ajustar los identificadores de botón, los estilos, el ancho espaciador y qué glifo o imagen se usa para cada botón. De forma predeterminada no es necesario usar estas API.  
  
## <a name="ccmdui-support-for-ctoolbar"></a>Compatibilidad de CCmdUI con CToolBar  
 Los botones de la barra de herramientas se actualizan siempre a través del mecanismo de `ON_UPDATE_COMMAND_UI` . En tiempo de inactividad, la barra de herramientas llamará al controlador `ON_UPDATE_COMMAND_UI` con el identificador de comando de ese botón. `ON_UPDATE_COMMAND_UI` no se llama para los separadores, pero se llama para los pulsadores y para los botones de casilla.  
  
 El controlador `ON_UPDATE_COMMAND_UI` puede llamar:  
  
- **Habilitar**: para habilitar o deshabilitar el botón. Esto funciona igual para los pulsadores que para los botones de casilla.  
  
- `SetCheck`: para establecer el estado de comprobación de un botón. Al llamar a esto para un botón de barra de herramientas lo convertirá en un botón de casilla. `SetCheck` toma un parámetro que puede ser 0 (no activado), 1 (activado) o 2 (indeterminado)  
  
- `SetRadio`: Una forma abreviada de `SetCheck`.  
  
 Los botones de casilla son botones de casilla "AUTO"; es decir, cuando el usuario los presiona cambiarán inmediatamente su estado. Activado es el estado inactivo o deprimido. No hay ninguna forma en la interfaz de usuario integrada para cambiar un botón al estado "indeterminado"; que debe realizarse a través de código.  
  
 Las API de personalización le permitirán cambiar el estado de un botón de barra de herramientas determinado, preferiblemente debe cambiar estos estados en el controlador `ON_UPDATE_COMMAND_UI` para el comando que representa el botón de barra de herramientas. Recuerde que el procesamiento de inactividad cambiará el estado de los botones de la barra de herramientas con el controlador `ON_UPDATE_COMMAND_UI` , por lo que se pueden perder los cambios realizados en estos estados a través de SetButtonStyle después del próximo tiempo inactivo.  
  
 Los botones de la barra de herramientas enviarán mensajes **WM_COMMAND** como botones normales o elementos de menú y normalmente se controlan mediante un controlador `ON_COMMAND` de la misma clase que proporciona el controlador `ON_UPDATE_COMMAND_UI` .  
  
 Existen cuatro estilos de botón de barra de herramientas (valores TBBS_) que se usan para los estados de visualización:  
  
-   TBBS_CHECKED:   la casilla está actualmente activada (abajo).  
  
-   TBBS_INDETERMINATE:   la casilla es actualmente indeterminada.  
  
-   TBBS_DISABLED:   el botón está actualmente deshabilitado.  
  
-   TBBS_PRESSED:   el botón está actualmente presionado.  
  
 Los seis estilos oficiales de botón de la Guía de diseño de aplicaciones de interfaz de Windows se representan mediante los valores TBBS siguientes:  
  
-   Arriba = 0  
  
-   Mouse hacia abajo = TBBS_PRESSED (&#124; cualquier otro estilo)  
  
-   Deshabilitado = TBBS_DISABLED  
  
-   Abajo = TBBS_CHECKED  
  
-   Abajo deshabilitado = TBBS_CHECKED &#124; TBBS_DISABLED  
  
-   Indeterminado = TBBS_INDETERMINATE  
  
##  <a name="_mfcnotes_cdialogbar"></a> CDialogBar  
 Una barra de cuadro de diálogo es una barra de controles que contiene los controles estándar de Windows. Actúa como un cuadro de diálogo que contiene los controles y admite la tabulación entre ellos. También actúa como un cuadro de diálogo que usa una plantilla de cuadro de diálogo para representar la barra.  
  
 Un `CDialogBar` se usa para la barra de herramientas de vista previa de impresión, que contiene los controles de pulsador estándar.  
  
 Usar un `CDialogBar` es como usar un `CFormView`. Debe definir una plantilla de cuadro de diálogo para la barra de cuadro de diálogo y quitar todos los estilos excepto **WS_CHILD**. Tenga en cuenta que el cuadro de diálogo no debe estar visible.  
  
 Las notificaciones de control para un `CDialogBar` se enviarán al elemento primario de la barra de control (como botones de la barra de herramientas).  
  
## <a name="ccmdui-support-for-cdialogbar"></a>Compatibilidad de CCmdUI con CDialogBar  
 Los botones de la barra de cuadro de diálogo deben actualizarse a través del mecanismo de controlador `ON_UPDATE_COMMAND_UI` . En tiempo de inactividad, la barra de cuadro de diálogo llamará el `ON_UPDATE_COMMAND_UI` controlador con el identificador de comando de todos los botones que tienen un identificador > = 0 x 8000 (es decir, en el intervalo de identificadores de comando).  
  
 El controlador `ON_UPDATE_COMMAND_UI` puede llamar:  
  
-   Habilitar: para habilitar o deshabilitar el botón.  
  
-   SetText: para cambiar el texto del botón.  
  
 La personalización puede realizarse a través de las API de administrador de ventana estándar.  
  
## <a name="see-also"></a>Vea también  
 [Notas técnicas por número](../mfc/technical-notes-by-number.md)   
 [Notas técnicas por categoría](../mfc/technical-notes-by-category.md)

