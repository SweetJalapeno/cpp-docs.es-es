---
title: Clase COleLinkingDoc | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
dev_langs:
- C++
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe37e1a159fa0138c237b58ffbd622292dcba714
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="colelinkingdoc-class"></a>Clase COleLinkingDoc
La clase base para documentos contenedores de OLE que admiten la vinculación a los elementos incrustados que contienen.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Construye un objeto `COleLinkingDoc`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|Registra el documento con la DLL del sistema OLE.|  
|[COleLinkingDoc::Revoke](#revoke)|Revoca el registro del documento.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Busca el elemento incrustado especificado.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Busca el elemento vinculado especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Una aplicación de contenedor que admite la vinculación a elementos incrustados se denomina un "contenedor de vínculo". El [OCLIENT](../../visual-cpp-samples.md) aplicación de ejemplo es un ejemplo de un contenedor de vínculo.  
  
 Cuando el origen de un elemento vinculado es un elemento incrustado en otro documento, que debe cargarse que contiene el documento en orden para el elemento incrustado que se pueda editar. Por este motivo, un contenedor de vínculo debe ser capaz de iniciar otra aplicación contenedora cuando el usuario desea volver a editar el origen de un elemento vinculado. La aplicación también debe utilizar el [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) clase para que puedan crear documentos cuando se inicia mediante programación.  
  
 Para que el contenedor de un contenedor de vínculo, derive su clase de documento de `COleLinkingDoc` en lugar de [COleDocument](../../mfc/reference/coledocument-class.md). Al igual que con cualquier otro contenedor OLE, debe diseñar una clase para almacenar la aplicación datos nativos, así como elementos incrustados o vinculados. Además, debe diseñar las estructuras de datos para almacenar los datos nativos. Si define un `CDocItem`-clase derivada para la aplicación nativa datos, puede utilizar la interfaz definida por `COleDocument` para almacenar los datos nativos, así como los datos OLE.  
  
 Para permitir que la aplicación que se iniciará mediante programación con otro contenedor, declare un `COleTemplateServer` objeto como un miembro de la aplicación `CWinApp`-clase derivada:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 En el `InitInstance` función miembro de la `CWinApp`-clase derivada, cree una plantilla de documento y especifique su `COleLinkingDoc`-deriva la clase que la clase de documento:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Conectar su `COleTemplateServer` objeto a las plantillas de documento mediante una llamada del objeto `ConnectTemplate` función miembro y registrar clases de todos los objetos con el sistema OLE mediante una llamada a **COleTemplateServer:: RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Para obtener un ejemplo `CWinApp`-derivados de la definición de clase y `InitInstance` función, vea OCLIENT. H y OCLIENT. CPP en el ejemplo MFC [OCLIENT](../../visual-cpp-samples.md).  
  
 Para obtener más información sobre el uso de `COleLinkingDoc`, consulte los artículos [contenedores: implementar un contenedor](../../mfc/containers-implementing-a-container.md) y [contenedores: características avanzadas](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxole.h  
  
##  <a name="colelinkingdoc"></a>  COleLinkingDoc::COleLinkingDoc  
 Construye un `COleLinkingDoc` objeto sin partir las comunicaciones con la archivos DLL del sistema OLE.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a la `Register` función de miembro para informar a OLE que el documento esté abierto.  
  
##  <a name="onfindembeddeditem"></a>  COleLinkingDoc::OnFindEmbeddedItem  
 Lo llama el marco de trabajo para determinar si el documento contiene un elemento OLE incrustado con el nombre especificado.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszItemName`  
 Puntero al nombre del elemento solicitado OLE incrustado.  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero al elemento especificado; **NULL** si no se encuentra el elemento.  
  
### <a name="remarks"></a>Comentarios  
 La implementación predeterminada busca en la lista de elementos incrustados para un elemento con el nombre especificado (la comparación de nombre distingue entre mayúsculas y minúsculas). Reemplace esta función si tiene su propio método de almacenamiento o nomenclatura elementos OLE incrustados.  
  
##  <a name="ongetlinkeditem"></a>  COleLinkingDoc::OnGetLinkedItem  
 Lo llama el marco de trabajo para comprobar si el documento contiene un elemento de servidor vinculado con el nombre especificado.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszItemName`  
 Puntero al nombre de la vinculado OLE elemento solicitado.  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero al elemento especificado; **NULL** si no se encuentra el elemento.  
  
### <a name="remarks"></a>Comentarios  
 El valor predeterminado `COleLinkingDoc` implementación siempre devuelve **NULL**. Esta función es reemplazada en la clase derivada `COleServerDoc` para buscar en la lista de elementos de servidor OLE de un elemento vinculado con el nombre especificado (la comparación de nombre distingue entre mayúsculas y minúsculas). Reemplace esta función si ha implementado su propio método de almacenar o recuperar los elementos del servidor vinculado.  
  
##  <a name="register"></a>  COleLinkingDoc::Register  
 Informa a la DLL del sistema OLE que el documento esté abierto.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parámetros  
 *pFactory*  
 Puntero a un objeto de fábrica OLE (puede ser **NULL**).  
  
 `lpszPathName`  
 Puntero a la ruta de acceso completa del documento contenedor.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se ha registrado correctamente el documento; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Llame a esta función al crear o abrir un archivo con nombre para registrar el documento con la DLL del sistema OLE. No hay ninguna necesidad de llamar a esta función si el documento representa un elemento incrustado.  
  
 Si utilizas `COleTemplateServer` en su aplicación, `Register` es llamado por `COleLinkingDoc`de implementación de `OnNewDocument`, `OnOpenDocument`, y `OnSaveDocument`.  
  
##  <a name="revoke"></a>  COleLinkingDoc::Revoke  
 Informa a la DLL del sistema OLE que el documento ya no está abierto.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Comentarios  
 Llame a esta función para revocar el registro del documento con las DLL del sistema OLE.  
  
 Debería llamar a esta función al cerrar un archivo con nombre, pero normalmente no es necesario llamarlo directamente. `Revoke` es llamado por `COleLinkingDoc`de implementación de `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, y `OnSaveDocument`.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo MFC OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument (clase)](../../mfc/reference/coledocument-class.md)   
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [CDocTemplate (clase)](../../mfc/reference/cdoctemplate-class.md)
