---
title: Clase CSplitButton | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac4241bb19c6abc0fbbf489bf4efb43f56ede72e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="csplitbutton-class"></a>Clase CSplitButton
La `CSplitButton` clase representa un control de botón de división. El control de botón de expansión realiza un comportamiento predeterminado cuando un usuario hace clic en la parte principal del botón y muestra un menú desplegable cuando un usuario hace clic en la flecha de lista desplegable del botón.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Construye un objeto `CSplitButton`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Crea un control de botón de división con estilos especificados y lo adjunta a la corriente `CSplitButton` objeto.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Establece el menú desplegable que se muestra cuando un usuario hace clic en la flecha de lista desplegable del control de botón de división actual.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Controla el `BCN_DROPDOWN` notificación de que el sistema envía cuando un usuario hace clic en la flecha de lista desplegable del control de botón de división actual.|  
  
## <a name="remarks"></a>Comentarios  
 El `CSplitButton` clase se deriva de la [CButton](../../mfc/reference/cbutton-class.md) clase. El control de botón de expansión es un control de botón cuyo estilo es `BS_SPLITBUTTON`. Muestra un menú personalizado cuando un usuario hace clic en la flecha de lista desplegable. Para obtener más información, consulte el `BS_SPLITBUTTON` y `BS_DEFSPLITBUTTON` estilos en [estilos de botón](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 En la siguiente ilustración muestra un cuadro de diálogo que contiene un control de paginación y un control de botón de división (1). Ya se ha hecho clic en la flecha de lista desplegable (2) y se muestra el submenú (3).  
  
 ![Cuadro de diálogo con un botón de división y control de paginación. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxcmn.h  
  
 Esta clase es compatible con [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] y versiones posteriores.  
  
 Requisitos adicionales para esta clase se describen en [crear requisitos para Windows Vista controles comunes](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>  CSplitButton::Create  
 Crea un control de botón de división con estilos especificados y lo adjunta a la corriente `CSplitButton` objeto.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[in] `dwStyle`|Una combinación bit a bit (OR) de estilos para aplicarse al control. Para obtener más información, consulte [estilos de botón](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
|[in] `rect`|Una referencia a un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) estructura que contiene la posición y el tamaño del control.|  
|[in] `pParentWnd`|Un puntero no nulo para un [CWnd](../../mfc/reference/cwnd-class.md) objeto que es la ventana primaria del control.|  
|[in] `nID`|El identificador del control.|  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si este método se realiza correctamente; en caso contrario, `false`.  
  
##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton  
 Construye un objeto `CSplitButton`. Los parámetros del constructor especifican un submenú que se muestra cuando un usuario hace clic en la flecha de lista desplegable del control de botón de división.  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[in] `nMenuId`|El identificador de recurso de la barra de menús.|  
|[in] `nSubMenuId`|El identificador de recurso de un submenú.|  
|[in] `pMenu`|Un puntero a un [CMenu](../../mfc/reference/cmenu-class.md) objeto que especifica un submenú. El `CSplitButton` objeto eliminaciones el `CMenu` objeto y su identificador `HMENU` cuando la `CSplitButton` objeto queda fuera del ámbito.|  
  
### <a name="remarks"></a>Comentarios  
 Use la [CSplitButton::Create](#create) método para crear un control de botón de división y adjuntarla a la `CSplitButton` objeto.  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 Controla el `BCN_DROPDOWN` notificación de que el sistema envía cuando un usuario hace clic en la flecha de lista desplegable del control de botón de división actual.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[in] `pNMHDR`|Puntero a un [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) estructura que contiene información sobre la [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) notificación.|  
|[out] `pResult`|(No se usa; se devuelve ningún valor). Valor devuelto de la [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) notificación.|  
  
### <a name="remarks"></a>Comentarios  
 Cuando el usuario hace clic en la flecha de lista desplegable en un control de botón de división, el sistema envía una `BCN_DROPDOWN` notificación de mensaje que el `OnDropDown` método controla. Sin embargo, el `CSplitButton` objeto no reenvía el `BCN_DROPDOWN` notificación para el control que contiene el control de botón de expansión. Por lo tanto, el control contenedor no admite una acción personalizada en respuesta a la notificación.  
  
 Para implementar una acción personalizada que admite el control contenedor, use un [CButton](../../mfc/reference/cbutton-class.md) objeto con un estilo de `BS_SPLITBUTTON` en lugar de un `CSplitButton` objeto. A continuación, implemente un controlador para el `BCN_DROPDOWN` notificación en el `CButton` objeto. Para obtener más información, consulte [estilos de botón](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 Para implementar una acción personalizada que el botón de expansión propio control admite, use [reflexión de mensajes](../../mfc/tn062-message-reflection-for-windows-controls.md). Derive su propia clase de la `CSplitButton` clase y asígnele el nombre, por ejemplo, CMySplitButton. A continuación, agregue el siguiente mapa de mensajes a la aplicación para controlar la `BCN_DROPDOWN` notificación:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu  
 Establece el menú desplegable que se muestra cuando un usuario hace clic en la flecha de lista desplegable del control de botón de división actual.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|[in] `nMenuId`|El identificador de recurso de la barra de menús.|  
|[in] `nSubMenuId`|El identificador de recurso de un submenú.|  
|[in] `pMenu`|Puntero a un [CMenu](../../mfc/reference/cmenu-class.md) objeto que especifica un submenú. El `CSplitButton` objeto eliminaciones el `CMenu` objeto y su identificador `HMENU` cuando la `CSplitButton` objeto queda fuera del ámbito.|  
  
### <a name="remarks"></a>Comentarios  
 El `nMenuId` parámetro identifica una barra de menús, que es una lista de elementos de la barra de menús horizontal. El `nSubMenuId` parámetro es un número de índice de base cero que identifica un submenú, que es la lista desplegable de elementos de menú asociados con cada elemento de la barra de menú. Por ejemplo, una aplicación típica tiene un menú que contiene los elementos de barra de menú "Archivo", "Editar" y "Ayuda". El elemento de barra de menú "Archivo" tiene un submenú que contiene los elementos de menú "Abrir", "Cerrar" y "Exit". Cuando se hace clic en la flecha de lista desplegable del control de botón de expansión, el control muestra el submenú especificado, no en la barra de menús.  
  
 En la siguiente ilustración muestra un cuadro de diálogo que contiene un control de paginación y un control de botón de división (1). Ya se ha hecho clic en la flecha de lista desplegable (2) y se muestra el submenú (3).  
  
 ![Cuadro de diálogo con un botón de división y control de paginación. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>Ejemplo  
 La primera instrucción en el ejemplo de código siguiente se muestra la [CSplitButton::SetDropDownMenu](#setdropdownmenu) método. Hemos creado el menú con Visual Studio editor de recursos, que se denomina automáticamente el identificador de la barra de menús, `IDR_MENU1`. El `nSubMenuId` parámetro, que es cero, se refiere al submenú solo de la barra de menús.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [Clase CSplitButton](../../mfc/reference/csplitbutton-class.md)   
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [CButton (clase)](../../mfc/reference/cbutton-class.md)
