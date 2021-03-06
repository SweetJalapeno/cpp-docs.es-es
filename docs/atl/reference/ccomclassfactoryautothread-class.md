---
title: Clase CComClassFactoryAutoThread | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 601f67d4a753dd617b9d7a3d5856ca64588a66c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ccomclassfactoryautothread-class"></a>Clase CComClassFactoryAutoThread
Esta clase implementa la [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) de interfaz y permite a los objetos que se creen en varios contenedores.  
  
> [!IMPORTANT]
>  Esta clase y sus miembros no se pueden usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Crea un objeto del CLSID especificado.|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Bloquea el generador de clases en la memoria.|  
  
## <a name="remarks"></a>Comentarios  
 `CComClassFactoryAutoThread` es similar a [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), pero permite que los objetos que se creen en varios contenedores. Para sacar partido de esta compatibilidad, derive su módulo EXE de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Objetos ATL normalmente adquieren un generador de clases derivando de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Esta clase incluye la macro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), que declara [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) como el generador de clases de forma predeterminada. Usar `CComClassFactoryAutoThread`, especifique el [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) macro en la definición de clase del objeto. Por ejemplo:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance  
 Crea un objeto del CLSID especificado y recupera un puntero de interfaz a este objeto.  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Parámetros  
 `pUnkOuter`  
 [in] Si el objeto se crea como parte de un agregado, a continuación, `pUnkOuter` debe ser el desconocido externo. En caso contrario, `pUnkOuter` debe ser **NULL**.  
  
 `riid`  
 [in] El IID de la interfaz solicitada. Si `pUnkOuter` no es **NULL**, `riid` debe ser **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Un puntero al puntero de interfaz identificado por `riid`. Si el objeto no admite esta interfaz, `ppvObj` está establecido en **NULL**.  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar.  
  
### <a name="remarks"></a>Comentarios  
 Si el módulo se deriva de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` primero selecciona un subproceso para crear el objeto en el contenedor asociado.  
  
##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer  
 Aumenta y disminuye el módulo recuento de bloqueos mediante una llamada a **_Module::Lock** y **_Module::Unlock**, respectivamente.  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>Parámetros  
 `fLock`  
 [in] Si **TRUE**, el recuento de bloqueos se incrementó; en caso contrario, disminuye el recuento de bloqueos.  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se usa `CComClassFactoryAutoThread`, **_Module** suele hacer referencia a la instancia global de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Al llamar a `LockServer` permite a un cliente almacenar en un generador de clases para que se pueden crear rápidamente varios objetos.  
  
## <a name="see-also"></a>Vea también  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [Clase CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)   
 [Clase CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx (clase)](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Información general de clases](../../atl/atl-class-overview.md)
