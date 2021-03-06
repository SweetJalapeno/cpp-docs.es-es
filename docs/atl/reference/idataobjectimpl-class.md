---
title: Clase IDataObjectImpl | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3ffcdd8cc8320b2534d928171fe75619062b300
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="idataobjectimpl-class"></a>Clase IDataObjectImpl
Esta clase proporciona métodos para admitir la transferencia de datos uniforme y administrar las conexiones.  
  
> [!IMPORTANT]
>  Esta clase y sus miembros no se pueden usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 La clase derivada de `IDataObjectImpl`.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Establece una conexión entre el objeto de datos y un receptor con notificación. Esto permite al receptor con notificación recibir notificaciones de cambios en el objeto.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Finaliza una conexión previamente establecida mediante `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Crea un enumerador para recorrer en iteración las conexiones de consulta actuales.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Crea un enumerador para recorrer en iteración la **FORMATETC** estructuras admitidas por el objeto de datos. Devuelve la implementación de ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Envía una notificación de cambio a cada receptor con notificación.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Recupera un lógicamente equivalente **FORMATETC** estructura a uno que sea más compleja. Devuelve la implementación de ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::GetData](#getdata)|Transfiere datos desde el objeto de datos al cliente. Los datos se describen en un **FORMATETC** de la estructura y se transfiere a través de un **STGMEDIUM** estructura.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Similar a `GetData`, excepto en que el cliente debe asignar el **STGMEDIUM** estructura. Devuelve la implementación de ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Determina si el objeto de datos admite una determinada **FORMATETC** estructura de transferencia de datos. Devuelve la implementación de ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::SetData](#setdata)|Transfiere datos desde el cliente para el objeto de datos. Devuelve la implementación de ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Comentarios  
 El [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) interfaz proporciona métodos para admitir la transferencia de datos uniforme. `IDataObject` usa las estructuras de formato estándar [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) y [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) para recuperar y almacenar datos.  
  
 `IDataObject` También administra las conexiones para informar de receptores para controlar las notificaciones de cambio de datos. El cliente puede recibir notificaciones de cambio de datos del objeto de datos, el cliente debe implementar la [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) interfaz en un objeto que llama a un receptor con notificación. Cuando el cliente, a continuación, llama a **IDataObject:: DAdvise**, se establece una conexión entre el objeto de datos y el receptor con notificación.  
  
 Clase `IDataObjectImpl` proporciona una implementación predeterminada de `IDataObject` e implementa **IUnknown** mediante el envío de información para el volcado de memoria compilaciones dispositivo en versiones de depuración.  
  
 **Artículos relacionados** [Tutorial ATL](../../atl/active-template-library-atl-tutorial.md), [crear un proyecto ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlctl.h  
  
##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise  
 Establece una conexión entre el objeto de datos y un receptor con notificación.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Comentarios  
 Esto permite al receptor con notificación recibir notificaciones de cambios en el objeto.  
  
 Para finalizar la conexión, llame a [DUnadvise](#dunadvise).  
  
 Vea [IDataObject:: DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) en el SDK de Windows.  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 Finaliza una conexión previamente establecida mediante [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) en el SDK de Windows.  
  
##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise  
 Crea un enumerador para recorrer en iteración las conexiones de consulta actuales.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) en el SDK de Windows.  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 Crea un enumerador para recorrer en iteración la **FORMATETC** estructuras admitidas por el objeto de datos.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) en el SDK de Windows.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve **E_NOTIMPL**.  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 Envía una notificación de cambio a cada receptor de notificaciones que se está administrando actualmente.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar.  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 Recupera un lógicamente equivalente **FORMATETC** estructura a uno que sea más compleja.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve **E_NOTIMPL**.  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) en el SDK de Windows.  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 Transfiere datos desde el objeto de datos al cliente.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Comentarios  
 El *pformatetcIn* parámetro debe especificar un tipo de medio de almacenamiento de **TYMED_MFPICT**.  
  
 Vea [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) en el SDK de Windows.  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 Similar a `GetData`, excepto en que el cliente debe asignar el **STGMEDIUM** estructura.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve **E_NOTIMPL**.  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) en el SDK de Windows.  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 Determina si el objeto de datos admite una determinada **FORMATETC** estructura de transferencia de datos.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve **E_NOTIMPL**.  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) en el SDK de Windows.  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 Transfiere datos desde el cliente para el objeto de datos.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve **E_NOTIMPL**.  
  
### <a name="remarks"></a>Comentarios  
 Vea [IDataObject:: SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) en el SDK de Windows.  
  
## <a name="see-also"></a>Vea también  
 [Información general de clases](../../atl/atl-class-overview.md)
