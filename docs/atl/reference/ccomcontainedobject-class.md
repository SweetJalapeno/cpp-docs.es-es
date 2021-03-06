---
title: Clase CComContainedObject | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0d4b0a6491aaeb27e4a1d986db01c03d1c5314d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcontainedobject-class"></a>Clase CComContainedObject
Esta clase implementa [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) mediante la delegación para el objeto propietario **IUnknown**.  
  
> [!IMPORTANT]
>  Esta clase y sus miembros no se pueden usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>Parámetros  
 `Base`  
 La clase derivada de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) o [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|El constructor. Inicializa el puntero de miembro para el objeto propietario `IUnknown`.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Destructor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|Incrementa el recuento de referencias en el objeto propietario.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Recupera el objeto propietario `IUnknown`.|  
|[CComContainedObject::QueryInterface](#queryinterface)|Recupera un puntero a la interfaz solicitada en el objeto propietario.|  
|[CComContainedObject::Release](#release)|Disminuye el recuento de referencias en el objeto propietario.|  
  
## <a name="remarks"></a>Comentarios  
 ATL usa `CComContainedObject` en clases [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), y [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject` implementa [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) mediante la delegación para el objeto propietario **IUnknown**. (El propietario es el objeto externo de una agregación o el objeto para el que se está creando una interfaz desplazable). `CComContainedObject` llamadas `CComObjectRootEx`del `OuterQueryInterface`, `OuterAddRef`, y `OuterRelease`, todas las heredadas a través de `Base`.  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcom.h  
  
##  <a name="addref"></a>  CComContainedObject::AddRef  
 Incrementa el recuento de referencias en el objeto propietario.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor que puede ser útil para el diagnóstico o pruebas.  
  
##  <a name="ccomcontainedobject"></a>  CComContainedObject::CComContainedObject  
 El constructor.  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>Parámetros  
 `pv`  
 [in] El objeto propietario **IUnknown**.  
  
### <a name="remarks"></a>Comentarios  
 Conjuntos de la `m_pOuterUnknown` puntero de miembro (heredan a través de la `Base` clase) a `pv`.  
  
##  <a name="dtor"></a>  CComContainedObject:: ~ CComContainedObject  
 Destructor.  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>Comentarios  
 Libera todos los recursos asignados.  
  
##  <a name="getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown  
 Devuelve el `m_pOuterUnknown` puntero de miembro (heredan a través de la *Base* clase) que contiene el objeto propietario **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>Valor devuelto  
 El objeto propietario **IUnknown**.  
  
### <a name="remarks"></a>Comentarios  
 Este método puede ser virtual si `Base` ha sido declarado por el [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) macro.  
  
##  <a name="queryinterface"></a>  CComContainedObject::QueryInterface  
 Recupera un puntero a la interfaz solicitada en el objeto propietario.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El identificador de la interfaz que se solicita.  
  
 `ppvObject`  
 [out] Un puntero al puntero de interfaz identificado por `iid`. Si el objeto no admite esta interfaz, `ppvObject` está establecido en **NULL**.  
  
 `pp`  
 [out] Un puntero al puntero de interfaz identificado por tipo `Q`. Si el objeto no admite esta interfaz, `pp` está establecido en **NULL**.  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar.  
  
##  <a name="release"></a>  CComContainedObject::Release  
 Disminuye el recuento de referencias en el objeto propietario.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valor devuelto  
 En las compilaciones de depuración, **versión** devuelve un valor que puede ser útil para el diagnóstico o pruebas. En las compilaciones de depuración no, **versión** siempre devuelve 0.  
  
## <a name="see-also"></a>Vea también  
 [Información general de clases](../../atl/atl-class-overview.md)
