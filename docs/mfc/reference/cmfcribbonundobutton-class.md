---
title: Clase CMFCRibbonUndoButton | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 233f37fc0ab31afcd8ba112677af8cd144d01c2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonundobutton-class"></a>Clase CMFCRibbonUndoButton
La `CMFCRibbonUndoButton` clase implementa un botón de lista desplegable que contiene los comandos de usuario más reciente. Los usuarios pueden seleccionar uno o varios de los comandos más recientes de la lista desplegable para rehacer o deshacer.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Construye un nuevo `CMFCRibbonUndoButton` objeto utilizando el identificador de comando que especifique, etiqueta de texto e imágenes de la lista de imágenes del objeto primario.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Agrega una nueva acción a la lista de acciones.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Borra la lista de acciones, que es la lista desplegable.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Determina el número de elementos que el usuario seleccionado en la lista desplegable.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Indica si el objeto contiene un menú.|  
  
## <a name="remarks"></a>Comentarios  
 La `CMFCRibbonUndoButton` clase utiliza una pila para representar la lista desplegable.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo construir un objeto de la `CMFCRibbonUndoButton` clase y agregue una nueva acción a la lista de acciones. Este fragmento de código forma parte de la [ejemplo de Gadgets de cinta de opciones](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction  
 Agrega una nueva acción a la lista de acciones.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `lpszLabel`  
 La etiqueta de acción que se mostrará en la lista desplegable.  
  
##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList  
 Borra la lista de acciones, que es la lista desplegable.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 Construye un nuevo `CMFCRibbonUndoButton` objeto utilizando el identificador de comando que especifique, etiqueta de texto e imágenes de la lista de imágenes del objeto primario.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `nID`  
 Especifica el identificador de comando.  
  
 [in] `lpszText`  
 Especifica la etiqueta de texto del botón.  
  
 [in] `nSmallImageIndex`  
 Índice de base cero en la lista de imágenes del objeto primario para la imagen del botón pequeño.  
  
 [in] `nLargeImageIndex`  
 Índice de base cero en la lista de imágenes del objeto primario para el de imagen grande del botón.  
  
 [in] `hIcon`  
 Un identificador a un icono que puede usar como imagen del botón.  
  
##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber  
 Determina el número de elementos que el usuario seleccionado en la lista desplegable.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El número de elementos que el usuario seleccionado.  
  
##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu  
 Indica si el objeto contiene un menú.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Siempre devuelve `TRUE`.  
  
### <a name="remarks"></a>Comentarios  
  
## <a name="see-also"></a>Vea también  
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [Clases](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery (clase)](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton (clase)](../../mfc/reference/cmfcribbonbutton-class.md)
