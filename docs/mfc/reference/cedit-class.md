---
title: Clase CEdit | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
dev_langs:
- C++
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72bf4ffb56ad34926b3a47d86d7609aae5dff4f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cedit-class"></a>CEdit Class
Proporciona la funcionalidad de un control de edición de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|Construye un `CEdit` objeto de control.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|Determina si se puede deshacer una operación de control de edición.|  
|[CEdit::CharFromPos](#charfrompos)|Recupera los índices de línea y el carácter para el carácter más cercano a una posición especificada.|  
|[CEdit::Clear](#clear)|Controlar la selección actual (si existe) de la edición de eliminaciones (borra).|  
|[CEdit::Copy](#copy)|Copia la selección actual (si existe) en el control de edición en el Portapapeles en **CF_TEXT** formato.|  
|[CEdit::Create](#create)|Crea el control de edición de Windows y lo adjunta a la `CEdit` objeto.|  
|[CEdit::Cut](#cut)|Control de la selección actual (si existe) de la edición de eliminaciones (cortes) y copia el texto eliminado en el Portapapeles en **CF_TEXT** formato.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Restablece el control (borra) la marca de deshacer de una operación de edición.|  
|[CEdit::FmtLines](#fmtlines)|Establece la inclusión de caracteres de salto de línea suave o desactivar dentro de un control de edición de varias líneas.|  
|[CEdit::GetCueBanner](#getcuebanner)|Recupera el texto que se muestra como la indicación de texto, o sugerencia, en un control de edición cuando el control está vacío y no tiene el foco.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Determina la línea superior visible en un control de edición.|  
|[CEdit::GetHandle](#gethandle)|Recupera un identificador a la memoria que está asignado actualmente para un control de edición de varias líneas.|  
|[CEdit::GetHighlight](#gethighlight)|Obtiene los índices de iniciales y finales de caracteres en un intervalo de texto que se resalta en el control de edición actual.|  
|[CEdit::GetLimitText](#getlimittext)|Obtiene la cantidad máxima de texto este `CEdit` puede contener.|  
|[CEdit::GetLine](#getline)|Recupera una línea de texto de un control de edición.|  
|[CEdit::GetLineCount](#getlinecount)|Recupera el número de líneas en un control de edición de varias líneas.|  
|[CEdit::GetMargins](#getmargins)|Obtiene los márgenes izquierdos y derecho para `CEdit`.|  
|[CEdit::GetModify](#getmodify)|Determina si se ha modificado el contenido de un control de edición.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|Recupera el carácter de contraseña que se muestran en un control de edición cuando el usuario escriba texto.|  
|[CEdit::GetRect](#getrect)|Obtiene el rectángulo de formato de un control de edición.|  
|[CEdit::GetSel](#getsel)|Obtiene las posiciones de caracteres primero y último de la selección actual en un control de edición.|  
|[CEdit::HideBalloonTip](#hideballoontip)|Oculta un globo de sugerencias asociado al control de edición actual.|  
|[CEdit::LimitText](#limittext)|Limita la longitud del texto que el usuario puede escribir en un control de edición.|  
|[CEdit::LineFromChar](#linefromchar)|Recupera el número de línea de la línea que contiene el índice de carácter especificado.|  
|[CEdit::LineIndex](#lineindex)|Recupera el índice de carácter de una línea dentro de un control de edición de varias líneas.|  
|[CEdit::LineLength](#linelength)|Recupera la longitud de una línea en un control de edición.|  
|[CEdit::LineScroll](#linescroll)|Desplaza el texto de un control de edición de varias líneas.|  
|[CEdit::Paste](#paste)|Inserta los datos del Portapapeles en el control de edición en la posición actual del cursor. Se insertan datos solo si el Portapapeles contiene datos en **CF_TEXT** formato.|  
|[CEdit::PosFromChar](#posfromchar)|Recupera las coordenadas de la esquina superior izquierda de un índice de carácter especificado.|  
|[CEdit::ReplaceSel](#replacesel)|Reemplaza la selección actual en un control de edición con el texto especificado.|  
|[CEdit::SetCueBanner](#setcuebanner)|Establece el texto que se muestra como la indicación de texto, o sugerencia, en un control de edición cuando el control está vacío y no tiene el foco.|  
|[CEdit::SetHandle](#sethandle)|Establece el identificador en la memoria local que se usará en un control de edición de varias líneas.|  
|[CEdit::SetHighlight](#sethighlight)|Resalta un intervalo de texto que se muestra en este control de edición.|  
|[CEdit::SetLimitText](#setlimittext)|Establece la cantidad máxima de texto esto `CEdit` puede contener.|  
|[CEdit::SetMargins](#setmargins)|Establece los márgenes izquierdos y derecho de este `CEdit`.|  
|[CEdit::SetModify](#setmodify)|Establece o borra la marca de modificación de un control de edición.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|Establece o quita un carácter de contraseña que se muestra en un control de edición cuando el usuario escribe texto.|  
|[CEdit::SetReadOnly](#setreadonly)|Establece el estado de solo lectura de un control de edición.|  
|[CEdit::SetRect](#setrect)|Establece el rectángulo de formato de un control de edición de varias líneas y actualiza el control.|  
|[CEdit::SetRectNP](#setrectnp)|Establece el rectángulo de formato de un control de edición de varias líneas sin volver a dibujar la ventana de control.|  
|[CEdit::SetSel](#setsel)|Selecciona un intervalo de caracteres en un control de edición.|  
|[CEdit::SetTabStops](#settabstops)|Control de edición de conjuntos de las tabulaciones en varias líneas.|  
|[CEdit::ShowBalloonTip](#showballoontip)|Muestra un globo de sugerencias asociado al control de edición actual.|  
|[CEdit::Undo](#undo)|Invierte la última operación de control de edición.|  
  
## <a name="remarks"></a>Comentarios  
 Un control de edición es una ventana rectangular secundarios en el que el usuario puede escribir texto.  
  
 Puede crear un control de edición de una plantilla de cuadro de diálogo o directamente en el código. En ambos casos, llame primero al constructor de `CEdit` para construir el `CEdit` de objeto y después llamar a la [crear](#create) función de miembro para crear las ventanas de control de edición y adjuntarla a la `CEdit` objeto.  
  
 Construcción puede ser un proceso de un paso en una clase derivada de `CEdit`. Escribir un constructor para la clase derivada y llamar a **crear** desde dentro del constructor.  
  
 `CEdit` hereda de una funcionalidad significativa de `CWnd`. Para establecer y recuperar el texto de un `CEdit` objeto, utilice la `CWnd` funciones miembro [SetWindowText](cwnd-class.md#setwindowtext) y [GetWindowText](cwnd-class.md#getwindowtext), qué set o get controlar todo el contenido de una operación de edición, incluso si se es un control de varias líneas. Las líneas de texto en un control de varias líneas se separan mediante secuencias de caracteres '\r\n'. Además, si un control de edición es multilínea, obtener y establecer parte del texto del control mediante una llamada a la `CEdit` funciones miembro [GetLine](#getline), [función miembro SetSel](#setsel), [función miembro GetSel](#getsel)y [ ReplaceSel](#replacesel).  
  
 Si desea controlar los mensajes de notificación de Windows enviados por un control de edición a su elemento primario (normalmente una clase derivada de `CDialog`), agregar una función de miembro de entrada y el controlador de mensajes de mapa de mensajes para la clase primaria para cada mensaje.  
  
 Cada entrada de mapa de mensajes tiene el formato siguiente:  
  
 **ON_** notificación **(** *memberFxn ***, Id.)**  
  
 donde `id` especifica el identificador de ventana secundaria de envío de notificaciones, el control de edición y `memberFxn` es el nombre de la función de miembro primario haya terminado de escribir para controlar la notificación.  
  
 Prototipo de función del elemento primario es el siguiente:  
  
 **afx_msg** memberFxn void **();**  
  
 Aquí te mostramos una lista de posibles entradas de mapa de mensajes y una descripción de los casos en que se enviarían al elemento primario:  
  
- **ON_EN_CHANGE** el usuario ha realizado una acción que puede haber modificado el texto en un control de edición. A diferencia de la **EN_UPDATE** mensaje de notificación, este mensaje de notificación se envía después de la presentación de las actualizaciones de Windows.  
  
- **ON_EN_ERRSPACE** el control de edición no puede asignar memoria suficiente para satisfacer una solicitud concreta.  
  
- **ON_EN_HSCROLL** el usuario hace clic en la barra de desplazamiento horizontal de un control de edición. La ventana primaria es una notificación antes de actualiza la pantalla.  
  
- **ON_EN_KILLFOCUS** el control de edición pierde el foco de entrada.  
  
- **ON_EN_MAXTEXT** la inserción actual ha superado el número especificado de caracteres para el control de edición y se ha truncado. También se envía cuando un control de edición no tiene la **ES_AUTOHSCROLL** estilo y el número de caracteres que deben insertarse superaría el ancho del control de edición. También se envía cuando un control de edición no tiene la **ES_AUTOVSCROLL** estilo y el número total de líneas resultantes de una inserción de texto, superan el alto del control de edición.  
  
- **ON_EN_SETFOCUS** se envía cuando un control de edición recibe el foco de entrada.  
  
- **ON_EN_UPDATE** el control de edición está a punto de mostrar el texto modificado. Envía después de que el control ha dado formato al texto, pero antes de que filtra el texto para que se puede modificar el tamaño de la ventana, si es necesario.  
  
- **ON_EN_VSCROLL** el usuario hace clic en la barra de desplazamiento vertical de un control de edición. La ventana primaria es una notificación antes de actualiza la pantalla.  
  
 Si crea un `CEdit` objeto dentro de un cuadro de diálogo, la `CEdit` objeto se destruye automáticamente cuando el usuario cierra el cuadro de diálogo.  
  
 Si crea un `CEdit` objeto desde un recurso de cuadro de diálogo con el editor de cuadro de diálogo, la `CEdit` objeto se destruye automáticamente cuando el usuario cierra el cuadro de diálogo.  
  
 Si crea un `CEdit` de objeto dentro de una ventana, puede que también necesite destruirlo. Si crea el `CEdit` del objeto en la pila, se destruye automáticamente. Si crea el `CEdit` objeto en el montón mediante el uso de la **nueva** función, se debe llamar a **eliminar** en el objeto para destruirla cuando el usuario finalice las ventanas de control de edición. Si asigna memoria en el `CEdit` objeto, invalide el `CEdit` destructor para deshacerse de las asignaciones.  
  
 Para modificar determinados estilos en un control de edición (como **ES_READONLY**) debe enviar mensajes específicos para el control en lugar de usar [ModifyStyle](cwnd-class.md#modifystyle). Vea [estilos de Control de edición](http://msdn.microsoft.com/library/windows/desktop/bb775464) en el SDK de Windows.  
  
 Para obtener más información sobre `CEdit`, vea:  
  
- [Controles](../../mfc/controls-mfc.md)  
  
-   El artículo de Knowledge Base Q259949: INFO: SetCaretPos() es no es apropiado con CEdit o controles CRichEditCtrl  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxwin.h  
  
##  <a name="canundo"></a>  CEdit::CanUndo  
 Llame a esta función para determinar si se puede deshacer la última operación de edición.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la última operación de edición se puedan deshacer mediante una llamada a la **deshacer** función miembro; 0 si no se puede deshacer.  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::Undo](#undo).  
  
##  <a name="cedit"></a>  CEdit::CEdit  
 Construye un objeto `CEdit`.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Comentarios  
 Use [crear](#create) para construir las ventanas de control de edición.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>  CEdit::CharFromPos  
 Llame a esta función para recuperar la línea de base cero y los índices de carácter del carácter más cercano al punto especificado en este `CEdit` control  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `pt`  
 Las coordenadas de un punto en el área cliente de este `CEdit` objeto.  
  
### <a name="return-value"></a>Valor devuelto  
 El índice de carácter en el orden inferior **WORD**y el índice de línea en el orden de alta **WORD**.  
  
### <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta función miembro está disponible a partir de Windows 95 y Windows NT 4.0.  
  
 Para obtener más información, consulte [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>  CEdit::Clear  
 Llame a esta función para eliminar (borrar) la selección actual (si existe) en el control de edición.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Comentarios  
 La eliminación realizada por **desactive** puedan deshacer mediante una llamada a la [deshacer](#undo) función miembro.  
  
 Para eliminar la selección actual y coloca el contenido eliminado en el Portapapeles, llame a la [cortar](#cut) función miembro.  
  
 Para obtener más información, consulte [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>  CEdit::Copy  
 Llame a esta función para copiar la selección actual (si existe) en el control de edición en el Portapapeles en **CF_TEXT** formato.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>  CEdit::Create  
 Crea el control de edición de Windows y lo adjunta a la `CEdit` objeto.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwStyle`  
 Especifica el estilo del control de edición. Aplicar cualquier combinación de [estilos de edición](styles-used-by-mfc.md#edit-styles) al control.  
  
 `rect`  
 Especifica el tamaño y la posición del control de edición. Puede ser un `CRect` objeto o `RECT` estructura.  
  
 `pParentWnd`  
 Especifica la ventana primaria del control de edición (normalmente un `CDialog`). No debe ser **NULL**.  
  
 `nID`  
 Especifica el identificador. del control de edición  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la inicialización se realiza correctamente; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Crear un `CEdit` objeto en dos pasos. En primer lugar, llame a la `CEdit` constructor y, después, llame **crear**, que crea el control de edición de Windows y lo adjunta a la `CEdit` objeto.  
  
 Cuando **crear** se ejecuta, Windows envía la [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), y [WM_ GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) mensajes para el control de edición.  
  
 Estos mensajes se controlan de manera predeterminada el [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), y [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) funciones miembro en la `CWnd` clase base. Para extender el control de mensajes de forma predeterminada, derive una clase de `CEdit`, agregue un mapa de mensajes a la nueva clase y reemplazan las funciones de miembro anterior de controlador de mensajes. Invalidar `OnCreate`, por ejemplo, para realizar la inicialización necesaria para la nueva clase.  
  
 Aplique el siguiente [estilos de ventana](styles-used-by-mfc.md#window-styles) a un control de edición.  
  
- **WS_CHILD** siempre  
  
- **WS_VISIBLE** normalmente  
  
- **WS_DISABLED** rara vez  
  
- **WS_GROUP** a controles de grupo  
  
- **WS_TABSTOP** debe incluir el control de edición en el orden de tabulación  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>  CEdit::Cut  
 Llame a esta función para eliminar (Cortar) la selección actual (si existe) en el control de edición y copiar el texto eliminado en el Portapapeles en **CF_TEXT** formato.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Comentarios  
 La eliminación realizada por **cortar** puedan deshacer mediante una llamada a la [deshacer](#undo) función miembro.  
  
 Para eliminar la selección actual sin colocar el texto eliminado en el Portapapeles, llame a la [desactive](#clear) función miembro.  
  
 Para obtener más información, consulte [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer  
 Llame a esta función para restablecer (borrar) el indicador de deshacer de un control de edición.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Comentarios  
 El control de edición ahora podrá deshacer la última operación. La marca de deshacer se establece cada vez que se puede deshacer una operación en el control de edición.  
  
 El indicador de deshacer automáticamente está desactivada cada vez que la [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) o [SetHandle](#sethandle) `CWnd` se denominan funciones miembro.  
  
 Para obtener más información, consulte [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>  CEdit::FmtLines  
 Llame a esta función para establecer la inclusión de caracteres de salto de línea suave o desactivar dentro de un control de edición de varias líneas.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>Parámetros  
 *bAddEOL*  
 Especifica si se pueden insertar caracteres de salto de línea suave. Un valor de **TRUE** inserta los caracteres; un valor de **FALSE** quita de ellos.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si cualquier formato que se produzca; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Un salto de línea suave está formada por dos retornos de carro y avance de línea insertado al final de una línea que se interrumpe debido a ajuste de líneas. Un salto de línea de duro está formada por un retorno de carro y avance de línea. Las líneas que terminan con un salto de línea de duro no se ven afectadas por `FmtLines`.  
  
 Windows responderá sólo si la `CEdit` objeto es un control de edición de varias líneas.  
  
 `FmtLines` sólo afecta al búfer devuelto [GetHandle](#gethandle) y el texto devuelto por [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627). No tiene efecto en la presentación del texto en el control de edición.  
  
 Para obtener más información, consulte [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>  CEdit::GetCueBanner  
 Recupera el texto que se muestra como la indicación de texto, o sugerencia, en un control de edición cuando el control está vacío.  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>Parámetros  
 [out] `lpszText`  
 Un puntero a una cadena que contiene el texto de indicación.  
  
 [in] `cchText`  
 El número de caracteres que se pueden recibir. Este número incluye el carácter final `NULL` caracteres.  
  
### <a name="return-value"></a>Valor devuelto  
 Para la primera sobrecarga, `true` si el método es correcto; en caso contrario `false`.  
  
 Para la segunda sobrecarga, un [CString](../../atl-mfc-shared/using-cstring.md) que contiene el texto de indicación de si el método es correcto; en caso contrario, la cadena vacía ("").  
  
### <a name="remarks"></a>Comentarios  
 Este método envía el [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) mensaje, que se describe en el SDK de Windows. Para obtener más información, consulte el [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) macro.  
  
##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine  
 Llame a esta función para determinar la línea de nivel superior visible en un control de edición.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Índice de base cero de la línea visible superior. Para los controles de edición de línea única, el valor devuelto es 0.  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>  CEdit::GetHandle  
 Llame a esta función para recuperar un identificador de la memoria asignada actualmente a un control de edición de varias líneas.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un identificador de memoria local que identifica el búfer que contiene el contenido del control de edición. Si se produce un error, como enviar el mensaje a un control de edición de línea única, el valor devuelto es 0.  
  
### <a name="remarks"></a>Comentarios  
 El identificador es un identificador de memoria local y se puede usar con cualquiera de los **Local** las funciones de memoria de Windows que toman una memoria local se tratan como un parámetro.  
  
 **GetHandle** se procesa solo por los controles de edición de varias líneas.  
  
 Llame a **GetHandle** para un control de edición de varias líneas en un cuadro de diálogo solo si el cuadro de diálogo se creó con la **DS_LOCALEDIT** aplicar estilo a la marca establecida. Si el **DS_LOCALEDIT** estilo no está establecido, se seguirán enviando un valor devuelto distinto de cero, pero no podrá usar el valor devuelto.  
  
> [!NOTE]
> **GetHandle** no funcionará con Windows 95 ó 98. Si se llama a **GetHandle** en Windows 95 y Windows 98, devolverá **NULL**. **GetHandle** funcionará como se documenta en Windows NT, las versiones 3.51 y posteriores.  
  
 Para obtener más información, consulte [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>  CEdit::GetHighlight  
 Obtiene los índices de los caracteres primeros y últimos de un intervalo de texto que se resalta en el control de edición actual.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[out] `pichStart`|Índice de base cero del primer carácter en el intervalo de texto que aparece resaltado.|  
|[out] `pichEnd`|Índice de base cero del último carácter en el intervalo de texto que aparece resaltado.|  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si este método se realiza correctamente; en caso contrario, `false`.  
  
### <a name="remarks"></a>Comentarios  
 Este método envía el [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) mensaje, que se describe en el SDK de Windows.  
  
##  <a name="getlimittext"></a>  CEdit::GetLimitText  
 Llame a esta función miembro para obtener el límite de texto para este `CEdit` objeto.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El límite texto actual, en bytes, de este `CEdit` objeto.  
  
### <a name="remarks"></a>Comentarios  
 El límite de texto es la cantidad máxima de texto, en bytes, que puede aceptar el control de edición.  
  
> [!NOTE]
>  Esta función miembro está disponible a partir de Windows 95 y Windows NT 4.0.  
  
 Para obtener más información, consulte [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>  CEdit::GetLine  
 Llame a esta función para recuperar una línea de texto de un control de edición y lo coloca en `lpszBuffer`.  
  
```  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Especifica el número de línea para recuperar de varias líneas de control de edición. Números de línea están basadas en cero; un valor de 0 especifica la primera línea. Este parámetro se ignora por un control de edición de línea única.  
  
 `lpszBuffer`  
 Señala al búfer que recibe una copia de la línea. La primera palabra del búfer debe especificar el número máximo de caracteres que se pueden copiar en el búfer.  
  
 `nMaxLength`  
 Especifica el número máximo de bytes que se pueden copiar en el búfer. `GetLine` coloca este valor en la primera palabra de `lpszBuffer` antes de realizar la llamada a Windows.  
  
### <a name="return-value"></a>Valor devuelto  
 El número de bytes copiados realmente. El valor devuelto es 0 si el número de línea especificado por `nIndex` es mayor que el número de líneas en el control de edición.  
  
### <a name="remarks"></a>Comentarios  
 La línea copiada no contiene un carácter de terminación null.  
  
 Para obtener más información, consulte [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CEdit::GetLineCount  
 Llame a esta función para recuperar el número de líneas en un control de edición de varias líneas.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Control de edición de un entero que contiene el número de líneas en varias líneas. Si no se ha especificado ningún texto en el control de edición, el valor devuelto es 1.  
  
### <a name="remarks"></a>Comentarios  
 `GetLineCount` solo se procesa mediante controles de edición de varias líneas.  
  
 Para obtener más información, consulte [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>  CEdit::GetMargins  
 Llame a esta función miembro para recuperar los márgenes izquierdos y derecho del control de edición.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El ancho del margen izquierdo en el orden inferior **WORD** y el ancho del margen derecho en el orden de alta **WORD**.  
  
### <a name="remarks"></a>Comentarios  
 Los márgenes se miden en píxeles.  
  
> [!NOTE]
>  Esta función miembro está disponible a partir de Windows 95 y Windows NT 4.0.  
  
 Para obtener más información, consulte [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="getmodify"></a>  CEdit::GetModify  
 Llame a esta función para determinar si se ha modificado el contenido de un control de edición.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se ha modificado el contenido del control de edición; 0 si permanecen sin cambios.  
  
### <a name="remarks"></a>Comentarios  
 Windows mantiene un marcador interno que indica si se ha cambiado el contenido del control de edición. Esta marca se borra cuando el control de edición se crea por primera vez y también se pueden borrar mediante una llamada a la [SetModify](#setmodify) función miembro.  
  
 Para obtener más información, consulte [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar  
 Llame a esta función para recuperar el carácter de contraseña que se muestra en un control de edición cuando el usuario escribe texto.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Especifica el carácter que se mostrará en lugar del carácter escrito por el usuario. El valor devuelto es `NULL` si no existe ningún carácter de contraseña.  
  
### <a name="remarks"></a>Comentarios  
 Si crea el control de edición con la **ES_PASSWORD** estilo, el archivo DLL que admite el control determina el carácter de contraseña predeterminado. El manifiesto o [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) método determina qué archivo DLL es compatible con el control de edición. Si el archivo user32.dll admite el control de edición, el carácter de contraseña predeterminado es asterisco ('* ', 002A U +). Si la versión de comctl32.dll 6 es compatible con el control de edición, el carácter predeterminado es negro círculo ('●', U + 25CF). Para obtener más información acerca de los archivos DLL y la versión que soporta los controles comunes, vea [Shell y versiones de los controles comunes](http://msdn.microsoft.com/library/windows/desktop/bb776779).  
  
 Este método envía el [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) mensaje, que se describe en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>  CEdit::GetRect  
 Llame a esta función para obtener el rectángulo de formato de un control de edición.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `lpRect`  
 Apunta a la `RECT` estructura que recibe el rectángulo de formato.  
  
### <a name="remarks"></a>Comentarios  
 El rectángulo de formato es el rectángulo limitador del texto, que es independiente del tamaño de la ventana de control de edición.  
  
 El rectángulo de formato de un control de edición de varias líneas se puede modificar mediante la [SetRect](#setrect) y [SetRectNP](#setrectnp) funciones miembro.  
  
 Para obtener más información, consulte [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::LimitText](#limittext).  
  
##  <a name="getsel"></a>  CEdit::GetSel  
 Llame a esta función para obtener iniciales y finales de posiciones de caracteres de la selección actual (si existe) en un control de edición, con el valor devuelto o los parámetros.  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nStartChar`  
 Referencia a un entero que recibirá la posición del primer carácter de la selección actual.  
  
 `nEndChar`  
 Referencia a un entero que recibirá la posición del primer carácter más allá del final de la selección actual.  
  
### <a name="return-value"></a>Valor devuelto  
 La versión que devuelve un `DWORD` devuelve un valor que contiene la posición inicial de la palabra de orden inferior y la posición del primer carácter después del final de la selección de la palabra de orden superior.  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip  
 Oculta un globo de sugerencias asociado al control de edición actual.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si este método se realiza correctamente; en caso contrario, `false`.  
  
### <a name="remarks"></a>Comentarios  
 Esta función envía el [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) mensaje, que se describe en el SDK de Windows.  
  
##  <a name="limittext"></a>  CEdit::LimitText  
 Llame a esta función para limitar la longitud del texto que el usuario puede escribir en un control de edición.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>Parámetros  
 `nChars`  
 Especifica la longitud (en bytes) del texto que el usuario puede escribir. Si este parámetro es 0, la longitud del texto se establece en **UINT_MAX** bytes. Éste es el comportamiento predeterminado.  
  
### <a name="remarks"></a>Comentarios  
 Cambiar el límite del texto restringe sólo el texto que el usuario puede escribir. No tiene ningún efecto en cualquier texto ya en el control de edición, ni afecta a la longitud del texto que se copian en el control de edición por la [SetWindowText](cwnd-class.md#setwindowtext) función miembro en `CWnd`. Si una aplicación usa el `SetWindowText` función colocar más texto en un control de edición que se especifica en la llamada a `LimitText`, el usuario puede eliminar alguna parte del texto en el control de edición. Sin embargo, el límite de texto impedirá que el usuario reemplazando el texto existente con texto nuevo, a menos que eliminar la selección actual hace que el texto quede por debajo del límite de texto.  
  
> [!NOTE]
>  En Win32 (Windows NT y Windows 95 ó 98), [SetLimitText](#setlimittext) reemplaza esta función.  
  
 Para obtener más información, consulte [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>  CEdit::LineFromChar  
 Llame a esta función para recuperar el número de línea de la línea que contiene el índice de carácter especificado.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Contiene el valor de índice de base cero para el carácter que desee en el texto del control de edición, o -1. Si `nIndex` es -1, especifica la línea actual, es decir, la línea que contiene el símbolo de intercalación.  
  
### <a name="return-value"></a>Valor devuelto  
 El número de línea de base cero de la línea que contiene el índice de carácter especificado por `nIndex`. Si `nIndex` es -1, se devuelve el número de la línea que contiene el primer carácter de la selección. Si no hay ninguna selección, se devuelve el número de línea actual.  
  
### <a name="remarks"></a>Comentarios  
 Un índice de carácter es el número de caracteres desde el principio del control de edición.  
  
 Esta función miembro solo se usa controles de edición de varias líneas.  
  
 Para obtener más información, consulte [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>  CEdit::LineIndex  
 Llame a esta función para recuperar el índice de carácter de una línea dentro de un control de edición de varias líneas.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nLine`  
 Contiene el valor de índice de la línea deseada en el texto del control de edición, o -1. Si `nLine` es -1, especifica la línea actual, es decir, la línea que contiene el símbolo de intercalación.  
  
### <a name="return-value"></a>Valor devuelto  
 El índice de carácter de la línea especificada en `nLine` o -1 si el número de línea especificado es mayor que el número de líneas en el control de edición.  
  
### <a name="remarks"></a>Comentarios  
 El índice de carácter es el número de caracteres desde el principio del control de edición a la línea especificada.  
  
 Esta función miembro solo se procesa en controles de edición de varias líneas.  
  
 Para obtener más información, consulte [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>  CEdit::LineLength  
 Recupera la longitud de una línea en un control de edición.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nLine`  
 Índice de base cero de un carácter en la línea cuya longitud se va a recuperar. El valor predeterminado es -1.  
  
### <a name="return-value"></a>Valor devuelto  
 Para los controles de edición de línea única, el valor devuelto es la longitud, en `TCHAR`s, del texto en el control de edición.  
  
 Para los controles de edición multilínea, el valor devuelto es la longitud, en `TCHAR`s, de la línea especificada por el `nLine` parámetro. Para [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] la longitud es el número de bytes en la línea de texto, para texto Unicode, la longitud es el número de caracteres de la línea. La longitud no incluye el carácter de retorno de carro al final de la línea.  
  
 Si el `nLine` parámetro es mayor que el número de caracteres en el control, el valor devuelto es cero.  
  
 Si el `nLine` parámetro es -1, el valor devuelto es el número de caracteres no seleccionados en las líneas que contienen los caracteres seleccionados. Por ejemplo, si la selección se extiende desde el cuarto carácter de una línea al octavo carácter desde el final de la línea siguiente, el valor devuelto es 10. Es decir, los tres caracteres en la primera línea y siete en la siguiente.  
  
 Para obtener más información sobre la `TCHAR` los tipos, vea la `TCHAR` fila en la tabla de [tipos de datos de Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Comentarios  
 Este método es compatible con la [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) mensaje, que se describe en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>  CEdit::LineScroll  
 Llame a esta función para desplazarse por el texto de un control de edición de varias líneas.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Parámetros  
 `nLines`  
 Especifica el número de líneas de desplazamiento vertical.  
  
 `nChars`  
 Especifica el número de posiciones de caracteres a desplazarse horizontalmente. Este valor se omite si el control de edición tiene el **ES_RIGHT** o **ES_CENTER** estilo.  
  
### <a name="remarks"></a>Comentarios  
 Esta función miembro se procesa solo por los controles de edición de varias líneas.  
  
 El control de edición no se desplaza verticalmente más allá de la última línea de texto en el control de edición. Si la línea actual más el número de líneas especificado por `nLines` supera el número total de líneas en el control de edición, el valor se ajusta para que la última línea del control de edición se desplaza a la parte superior de la ventana de control de edición.  
  
 `LineScroll` puede utilizarse para desplazarse horizontalmente más allá del último carácter de cualquiera de las líneas.  
  
 Para obtener más información, consulte [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>  CEdit::Paste  
 Llame a esta función para insertar los datos desde el Portapapeles en el `CEdit` en el punto de inserción.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Comentarios  
 Se insertan datos solo si el Portapapeles contiene datos en **CF_TEXT** formato.  
  
 Para obtener más información, consulte [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>  CEdit::PosFromChar  
 Llame a esta función para obtener la posición (esquina superior izquierda) de un carácter determinado dentro de este `CEdit` objeto.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nChar`  
 Índice de base cero del carácter especificado.  
  
### <a name="return-value"></a>Valor devuelto  
 Las coordenadas de la esquina superior izquierda del carácter especificado por `nChar`.  
  
### <a name="remarks"></a>Comentarios  
 Se especifica el carácter dando a su valor de índice de base cero. Si `nChar` es mayor que el índice del último carácter en esta `CEdit` de objeto, el valor devuelto especifica las coordenadas de la posición de carácter inmediatamente después del último carácter en esta `CEdit` objeto.  
  
> [!NOTE]
>  Esta función miembro está disponible a partir de Windows 95 y Windows NT 4.0.  
  
 Para obtener más información, consulte [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::LineFromChar](#linefromchar).  
  
##  <a name="replacesel"></a>  CEdit::ReplaceSel  
 Llame a esta función para reemplazar la selección actual en un control de edición con el texto especificado por `lpszNewText`.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszNewText`  
 Apunta a una cadena terminada en null que contiene el texto de reemplazo.  
  
 `bCanUndo`  
 Para especificar que se puede deshacer esta función, establezca el valor de este parámetro para **TRUE** . El valor predeterminado es **FALSE**.  
  
### <a name="remarks"></a>Comentarios  
 Reemplaza solo una parte del texto de un control de edición. Si desea reemplazar todo el texto, use la [CWnd::SetWindowText](cwnd-class.md#setwindowtext) función miembro.  
  
 Si no hay ninguna selección actual, se inserta el texto de reemplazo en la ubicación actual del cursor.  
  
 Para obtener más información, consulte [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::LineIndex](#lineindex).  
  
##  <a name="setcuebanner"></a>  CEdit::SetCueBanner  
 Establece el texto que se muestra como la pila de texto, o sugerencia, en una edición de control cuando el control está vacío.  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `lpszText`  
 Puntero a una cadena que contiene la pila para mostrar en el control de edición.  
  
 [in] `fDrawWhenFocused`  
 Si `false`, no se dibuja el titular de indicación cuando el usuario hace clic en el control de edición y el foco proporciona al control.  
  
 Si `true`, se dibuja el titular de indicación incluso cuando el control tiene el foco. El titular de indicación desaparece cuando el usuario empieza a escribir en el control.  
  
 El valor predeterminado es `false`.  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si el método es correcto; en caso contrario, `false`.  
  
### <a name="remarks"></a>Comentarios  
 Este método envía el [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) mensaje, que se describe en el SDK de Windows. Para obtener más información, consulte el [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) macro.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la [CEdit::SetCueBanner](#setcuebanner) método.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>  CEdit::SetHandle  
 Llame a esta función para establecer el identificador de la memoria local que se usará en un control de edición de varias líneas.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>Parámetros  
 *hBuffer*  
 Contiene un identificador de la memoria local. Este identificador se debe haber creado por una llamada anterior a la [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) función de Windows mediante el **LMEM_MOVEABLE** marca. La memoria se supone que contienen una cadena terminada en null. Si esto no es el caso, el primer byte de la memoria asignada debe establecerse en 0.  
  
### <a name="remarks"></a>Comentarios  
 El control de edición, a continuación, usará este búfer para almacenar el texto mostrado actualmente en lugar de asignar su propio búfer.  
  
 Esta función miembro se procesa solo por los controles de edición de varias líneas.  
  
 Antes de que una aplicación establezca un nuevo identificador de memoria, debe usar el [GetHandle](#gethandle) función de miembro para obtener el identificador para el búfer de memoria actual y liberar esa memoria con el **LocalFree** la función de Windows.  
  
 `SetHandle` Borra el búfer de deshacer (el [CanUndo](#canundo) función miembro, a continuación, devuelve 0) y la marca de modificación interna (la [GetModify](#getmodify) función miembro, a continuación, devuelve 0). La ventana de control de edición se vuelve a dibujar.  
  
 Puede usar esta función miembro en un control de edición de varias líneas en un cuadro de diálogo solo si ha creado el cuadro de diálogo con el **DS_LOCALEDIT** aplicar estilo a la marca establecida.  
  
> [!NOTE]
> **GetHandle** no funcionará con Windows 95 ó 98. Si se llama a **GetHandle** en Windows 95 y Windows 98, devolverá **NULL**. **GetHandle** funcionará como se documenta en Windows NT, las versiones 3.51 y posteriores.  
  
 Para obtener más información, consulte [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), y [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) del SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>  CEdit::SetHighlight  
 Resalta un intervalo de texto que se muestra en este control de edición.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[in] `ichStart`|Índice de base cero del primer carácter en el intervalo de texto para resaltar.|  
|[in] `ichEnd`|Índice de base cero del último carácter en el intervalo de texto para resaltar.|  
  
### <a name="remarks"></a>Comentarios  
 Este método envía el [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) mensaje, que se describe en el SDK de Windows.  
  
##  <a name="setlimittext"></a>  CEdit::SetLimitText  
 Llame a esta función miembro para establecer el límite de texto para este `CEdit` objeto.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>Parámetros  
 `nMax`  
 El nuevo límite de texto, en caracteres.  
  
### <a name="remarks"></a>Comentarios  
 El límite de texto es la cantidad máxima de texto, en caracteres, que puede aceptar el control de edición.  
  
 Cambiar el límite del texto restringe sólo el texto que el usuario puede escribir. No tiene ningún efecto en cualquier texto ya en el control de edición, ni afecta a la longitud del texto que se copian en el control de edición por la [SetWindowText](cwnd-class.md#setwindowtext) función miembro en `CWnd`. Si una aplicación usa el `SetWindowText` función colocar más texto en un control de edición que se especifica en la llamada a `LimitText`, el usuario puede eliminar alguna parte del texto en el control de edición. Sin embargo, el límite de texto impedirá que el usuario reemplazando el texto existente con texto nuevo, a menos que eliminar la selección actual hace que el texto quede por debajo del límite de texto.  
  
 Esta función reemplaza [LimitText](#limittext) en Win32.  
  
 Para obtener más información, consulte [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmargins"></a>  CEdit::SetMargins  
 Llame a este método para establecer los márgenes izquierdos y derecho del control de edición.  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>Parámetros  
 *nLeft*  
 El ancho del margen izquierdo nuevo, en píxeles.  
  
 *nRight*  
 El ancho del margen derecho nuevo, en píxeles.  
  
### <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta función miembro está disponible a partir de Windows 95 y Windows NT 4.0.  
  
 Para obtener más información, consulte [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmodify"></a>  CEdit::SetModify  
 Llame a esta función para establecer o borrar el indicador modificado para un control de edición.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parámetros  
 `bModified`  
 Un valor de **TRUE** indica que se ha modificado el texto y un valor de **FALSE** indica no se modifica. De forma predeterminada, se establece la marca modificada.  
  
### <a name="remarks"></a>Comentarios  
 La marca modificada se indica como si no se ha modificado el texto en el control de edición. Se establece automáticamente cuando el usuario cambia el texto. Su valor se puede recuperar con el [GetModify](#getmodify) función miembro.  
  
 Para obtener más información, consulte [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::GetModify](#getmodify).  
  
##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar  
 Llame a esta función para establecer o quitar un carácter de contraseña que se muestran en un control de edición cuando el usuario escribe texto.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>Parámetros  
 *CH*  
 Especifica el carácter que se mostrará en lugar del carácter escrito por el usuario. Si *ch* es 0, se muestran los caracteres reales escritos por el usuario.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se establece un carácter de contraseña, dicho carácter se muestra para cada carácter de los tipos de usuario.  
  
 Esta función miembro no tiene ningún efecto en varias líneas control de edición.  
  
 Cuando el `SetPasswordChar` se llama la función miembro, `CEdit` se volverá a dibujar todos los caracteres visibles mediante el carácter especificado por *ch*.  
  
 Si el control de edición se crea con el [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) estilo, el carácter de contraseña predeterminado se establece en un asterisco ( **\***). Este estilo se quitará si `SetPasswordChar` se llama con *ch* establecido en 0.  
  
 Para obtener más información, consulte [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>  CEdit::SetReadOnly  
 Llama a esta función para establecer el estado de solo lectura de un control de edición.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Parámetros  
 `bReadOnly`  
 Especifica si se debe establecer o quitar el estado de solo lectura del control de edición. Un valor de **TRUE** establece el estado como de solo lectura; un valor de **FALSE** establece el estado de lectura/escritura.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la operación es correcta, o 0 si un error se produce.  
  
### <a name="remarks"></a>Comentarios  
 La configuración actual se puede encontrar mediante la comprobación de la [ES_READONLY](styles-used-by-mfc.md#edit-styles) marca en el valor devuelto de [CWnd::GetStyle](cwnd-class.md#getstyle).  
  
 Para obtener más información, consulte [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>  CEdit::SetRect  
 Llame a esta función para establecer las dimensiones de un rectángulo con las coordenadas especificadas.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpRect`  
 Apunta a la `RECT` estructura o `CRect` objeto que especifica las nuevas dimensiones del rectángulo de formato.  
  
### <a name="remarks"></a>Comentarios  
 Este miembro se procesa solo por los controles de edición de varias líneas.  
  
 Use `SetRect` para establecer el formato de control de edición rectángulo de varias líneas. El rectángulo de formato es el rectángulo limitador del texto, que es independiente del tamaño de la ventana de control de edición. Cuando el control de edición se crea por primera vez, el rectángulo de formato es el mismo que el área de cliente de la ventana de control de edición. Mediante el uso de la `SetRect` función miembro, una aplicación puede establecer el formato rectángulo mayor o menor que la ventana de control de edición.  
  
 Si el control de edición no tiene ninguna barra de desplazamiento, texto se recortará, no se ajusta, si es mayor que la ventana del rectángulo de formato. Si el control de edición contiene un borde, el rectángulo de formato se reduce por el tamaño del borde. Si está ajustando el rectángulo devuelto por la `GetRect` función miembro, debe quitar el tamaño del borde antes de pasar el rectángulo para `SetRect`.  
  
 Cuando `SetRect` se llama, el control de edición del texto también ha cambiado y se vuelve a mostrar.  
  
 Para obtener más información, consulte [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>  CEdit::SetRectNP  
 Llame a esta función para establecer el rectángulo de formato de un control de edición de varias líneas.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpRect`  
 Apunta a un `RECT` estructura o `CRect` objeto que especifica las nuevas dimensiones del rectángulo.  
  
### <a name="remarks"></a>Comentarios  
 El rectángulo de formato es el rectángulo limitador del texto, que es independiente del tamaño de la ventana de control de edición.  
  
 `SetRectNP` es idéntica a la `SetRect` función miembro, salvo que la ventana de control de edición no vuelve a dibujarse.  
  
 Cuando el control de edición se crea por primera vez, el rectángulo de formato es el mismo que el área de cliente de la ventana de control de edición. Mediante una llamada a la `SetRectNP` función miembro, una aplicación puede establecer el formato rectángulo mayor o menor que la ventana de control de edición.  
  
 Si el control de edición no tiene ninguna barra de desplazamiento, texto se recortará, no se ajusta, si es mayor que la ventana del rectángulo de formato.  
  
 Este miembro se procesa solo por los controles de edición de varias líneas.  
  
 Para obtener más información, consulte [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::SetRect](#setrect).  
  
##  <a name="setsel"></a>  CEdit::SetSel  
 Llame a esta función para seleccionar un intervalo de caracteres en un control de edición.  
  
```  
void SetSel(
    DWORD dwSelection,  
    BOOL bNoScroll = FALSE);

 
void SetSel(
    int nStartChar,  
    int nEndChar,  
    BOOL bNoScroll = FALSE);
```  
  
### <a name="parameters"></a>Parámetros  
 *dwSelection*  
 Especifica la posición inicial de la palabra de orden inferior y la posición final de la palabra de orden superior. Si la palabra de orden inferior es 0 y la palabra de orden superior es -1, se selecciona todo el texto en el control de edición. Si la palabra de orden inferior es -1, se quitará cualquier selección actual.  
  
 *bNoScroll*  
 Indica si se debe desplazar el símbolo de intercalación en la vista. Si **FALSE**, se desplaza el símbolo de intercalación en la vista. Si **TRUE**, el símbolo de intercalación no se desplaza en la vista.  
  
 `nStartChar`  
 Especifica la posición inicial. Si `nStartChar` es 0 y `nEndChar` es -1, todo el texto en el control de edición está seleccionado. Si `nStartChar` es -1, se quita cualquier selección actual.  
  
 `nEndChar`  
 Especifica la posición final.  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEdit::GetSel](#getsel).  
  
##  <a name="settabstops"></a>  CEdit::SetTabStops  
 Llame a esta función para establecer las posiciones de tabulación en un control de edición de varias líneas.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parámetros  
 `cxEachStop`  
 Especifica que se puede establecer en posiciones de tabulación cada `cxEachStop` unidades de cuadro de diálogo.  
  
 `nTabStops`  
 Especifica el número de posiciones de tabulación contenidos en `rgTabStops`. Este número debe ser mayor que 1.  
  
 `rgTabStops`  
 Apunta a una matriz de enteros sin signo que especifica la ficha se detiene en unidades de cuadro de diálogo. Una unidad de cuadro de diálogo es una distancia horizontal o vertical. Una unidad de cuadro de diálogo horizontal equivale a una cuarta parte de la unidad de base de ancho del cuadro de diálogo actual y 1 unidad de cuadro de diálogo vertical equivale a una octava parte de la unidad de alto de la base de cuadro de diálogo actual. Las unidades de base del cuadro de diálogo se calculan basándose en el alto y ancho de la fuente del sistema actual. El **GetDialogBaseUnits** la función de Windows devuelve el cuadro de diálogo actual unidades base en píxeles.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se han establecido las pestañas; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Cuando el texto se copia en un control de edición de varias líneas, cualquier carácter de tabulación en el texto hará que el espacio que se genere hasta la siguiente posición de tabulación.  
  
 Para establecer las posiciones de tabulación en el tamaño predeterminado de 32 unidades de cuadro de diálogo, llame a la versión de esta función miembro sin parámetros. Para establecer las posiciones de tabulación en un tamaño distinto de 32, llame a la versión con el `cxEachStop` parámetro. Para establecer las posiciones de tabulación en una matriz de tamaños, utilice la versión con dos parámetros.  
  
 Esta función miembro solo se procesa en controles de edición de varias líneas.  
  
 `SetTabStops` no se actualiza automáticamente la ventana de edición. Si cambia las tabulaciones para el texto ya está en el control de edición, llame a [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) para volver a dibujar la ventana de edición.  
  
 Para obtener más información, consulte [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) y [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CEditView::SetTabStops](ceditview-class.md#settabstops).  
  
##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip  
 Muestra un globo de sugerencias asociado al control de edición actual.  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[in] `pEditBalloonTip`|Puntero a un [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) estructura que describe el globo de sugerencias.|  
|[in] `lpszTitle`|Puntero a una cadena Unicode que contiene el título del globo de sugerencias.|  
|[in] `lpszText`|Puntero a una cadena Unicode que contiene el texto de sugerencia de globo.|  
|[in] `ttiIcon`|Un `INT` que especifica el tipo de icono que se va a asociar con el globo de sugerencias. El valor predeterminado es `TTI_NONE`. Para obtener más información, consulte el `ttiIcon` miembro de la [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) estructura.|  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si este método se realiza correctamente; en caso contrario, `false`.  
  
### <a name="remarks"></a>Comentarios  
 Esta función envía el [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) mensaje, que se describe en el SDK de Windows. Para obtener más información, consulte el [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) macro.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define una variable, `m_cedit`, que se usa para tener acceso al control de edición actual. Esta variable se utiliza en el siguiente ejemplo.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra un globo de sugerencias para un control de edición. El [CEdit::ShowBalloonTip](#showballoontip) método especifica un texto de sugerencia de título y el globo.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>  CEdit::Undo  
 Llame a esta función para deshacer la última operación de control de edición.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Para un control de edición de línea única, el valor devuelto siempre es distinto de cero. Para un control de edición de varias líneas, el valor devuelto es distinto de cero si la operación de deshacer se realiza correctamente, o 0 si se produce un error en la operación de deshacer.  
  
### <a name="remarks"></a>Comentarios  
 También se puede deshacer una operación de deshacer. Por ejemplo, puede restaurar el texto eliminado con la primera llamada a **deshacer**. Como no hay ninguna operación de edición que intervengan, puede quitar el texto nuevo con una segunda llamada a **deshacer**.  
  
 Para obtener más información, consulte [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) en el SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo CALCDRIV de MFC](../../visual-cpp-samples.md)   
 [CMNCTRL2 de ejemplo MFC](../../visual-cpp-samples.md)   
 [CWnd (clase)](../../mfc/reference/cwnd-class.md)   
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [CWnd (clase)](cwnd-class.md)   
 [Clase CButton](cbutton-class.md)   
 [CComboBox (clase)](ccombobox-class.md)   
 [CListBox (clase)](clistbox-class.md)   
 [Clase CScrollBar](cscrollbar-class.md)   
 [Clase CStatic](cstatic-class.md)   
 [CDialog (clase)](cdialog-class.md)
