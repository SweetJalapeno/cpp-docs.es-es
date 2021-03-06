---
title: Clase CMFCPreviewCtrlImpl | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb1ef84aabed69554ded868bbe9092c3e8b7082f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpreviewctrlimpl-class"></a>Clase CMFCPreviewCtrlImpl
Esta clase implementa una ventana que se coloca en una ventana host proporcionada por el Shell de vista previa avanzada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|Se destruye un objeto de control de vista previa.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Construye un objeto de control de vista previa.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|Sobrecargado. Llama a un controlador de vista previa avanzada para crear la ventana de Windows.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Llama a un controlador de vista previa avanzada cuando es necesario destruir este control.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|Establece el foco a este control de entrada.|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Devuelve un documento conectado a este control de vista previa.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Indica a este control para volver a dibujar.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Llamado por el controlador de vista previa para crear una relación entre la implementación de documento y el control de vista previa.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Establece a un nuevo elemento primario para este control.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Llama a un controlador de vista previa avanzada cuando sea necesario establecer los objetos visuales de vista previa enriquecida contenido.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Establece un nuevo rectángulo delimitador para este control.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Lo llama el marco de trabajo para representar la vista previa.|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Color de fondo de la ventana de vista previa.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Color del texto de la ventana de vista previa.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Fuente utilizada para mostrar texto en la ventana de vista previa.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Un puntero a un documento cuyo contenido se visualizan en el control.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
Construye un objeto de control de vista previa.

### <a name="syntax"></a>Sintaxis
CMFCPreviewCtrlImpl();  

## <a name="create"></a> CMFCPreviewCtrlImpl::Create
Sobrecargado. Llama a un controlador de vista previa avanzada para crear la ventana de Windows.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc  
);  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc,  
   CCreateContext* pContext  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `hWndParent`  
 Un identificador a la ventana host proporcionada por el Shell de vista previa avanzada.  
  
 `prc`  
 Especifica el tamaño inicial y la posición de la ventana.  
  
 `pContext`  
 Un puntero a un contexto de creación.  
  
### <a name="return-value"></a>Valor devuelto  
 `TRUE` Si la creación se realizó correctamente; en caso contrario, `FALSE`.  
  
## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy
Llama a un controlador de vista previa avanzada cuando es necesario destruir este control.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void Destroy();  
```  
  
## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint  
Lo llama el marco de trabajo para representar la vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pDC`  
 Un puntero a un contexto de dispositivo para dibujar.  


## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus  
Establece el foco a este control de entrada.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void Focus();  
```  
## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument
Devuelve un documento conectado a este control de vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a un documento, cuyo contenido se visualizan en el control.

## <a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl::m_clrBackColor  
Color de fondo de la ventana de vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl::m_clrTextColor
Color del texto de la ventana de vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="m_font"></a> Fuente de CMFCPreviewCtrlImpl::m_font utilizada para mostrar texto en la ventana de vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
CFont m_font;  
```  
## <a name="m_pdocument"></a> CMFCPreviewCtrlImpl::m_pDocument  
Un puntero a un documento cuyo contenido se visualizan en el control.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw  
Indica a este control para volver a dibujar.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void Redraw();  
```  
## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument 
Llamado por el controlador de vista previa para crear una relación entre la implementación de documento y el control de vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pDocument`  
 Un puntero a la implementación del documento.  

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost  
Establece a un nuevo elemento primario para este control.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `hWndParent`  
 Un identificador a la nueva ventana primaria.  

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals  
Llama a un controlador de vista previa avanzada cuando sea necesario establecer los objetos visuales de vista previa enriquecida contenido.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `clrBack`  
 Color de fondo de la ventana de vista previa.  
  
 `clrText`  
 Color del texto de la ventana de vista previa.  
  
 `plf`  
 Fuente utilizada para mostrar texto en la ventana de vista previa. 

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect  
Establece un nuevo rectángulo delimitador para este control.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `prc`  
 Especifica el nuevo tamaño y la posición del control de vista previa.  
  
 `bRedraw`  
 Especifica si el control debe volver a dibujar.  
  
### <a name="remarks"></a>Comentarios  
 Normalmente, un nuevo rectángulo delimitador se establece cuando se cambia el tamaño del control host.  

## <a name="dtor"></a> CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
Se destruye un objeto de control de vista previa.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  
