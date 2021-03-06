---
title: Clase IPerPropertyBrowsingImpl | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d9fffd6151405eaf53e99f770281139d7664b01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="iperpropertybrowsingimpl-class"></a>Clase IPerPropertyBrowsingImpl
Esta clase implementa **IUnknown** y permite que un cliente tener acceso a la información de páginas de propiedades de un objeto.  
  
> [!IMPORTANT]
>  Esta clase y sus miembros no se pueden usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 La clase derivada de `IPerPropertyBrowsingImpl`.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Recupera una cadena que describe una propiedad determinada.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Recupera una matriz de cadenas que corresponde a los valores que puede aceptar una propiedad determinada.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Recupera un **VARIANT** que contiene el valor de una propiedad identificada por un DISPID determinado. El identificador de envío está asociado con el nombre de cadena recuperado desde `GetPredefinedStrings`. Devuelve la implementación de ATL **E_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Recupera el CLSID de la página de propiedades asociada a una propiedad determinada.|  
  
## <a name="remarks"></a>Comentarios  
 El [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) interfaz permite que un cliente tener acceso a la información de páginas de propiedades de un objeto. Clase `IPerPropertyBrowsingImpl` proporciona una implementación predeterminada de esta interfaz e implementa **IUnknown** mediante el envío de información para el volcado de memoria compilaciones dispositivo en versiones de depuración.  
  
> [!NOTE]
>  Si usas Microsoft Access como la aplicación contenedora, debe derivar la clase de `IPerPropertyBrowsingImpl`. En caso contrario, el acceso no cargará el control.  
  
 **Artículos relacionados** [Tutorial ATL](../../atl/active-template-library-atl-tutorial.md), [crear un proyecto ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlctl.h  
  
##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString  
 Recupera una cadena que describe una propiedad determinada.  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>Comentarios  
 Vea [IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) en el SDK de Windows.  
  
##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings  
 Llena cada matriz con cero elementos.  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Implementación de ATL de [GetPredefinedValue](#getpredefinedvalue) devuelve **E_NOTIMPL**.  
  
### <a name="remarks"></a>Comentarios  
 Vea [IPerPropertyBrowsing::](http://msdn.microsoft.com/library/windows/desktop/ms679724) en el SDK de Windows.  
  
##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue  
 Recupera un **VARIANT** que contiene el valor de una propiedad identificada por un DISPID determinado. El identificador de envío está asociado con el nombre de cadena recuperado desde `GetPredefinedStrings`.  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve **E_NOTIMPL**.  
  
### <a name="remarks"></a>Comentarios  
 Implementación de ATL de [GetPredefinedStrings](#getpredefinedstrings) no recupera ninguna cadena correspondiente.  
  
 Vea [IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) en el SDK de Windows.  
  
##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage  
 Recupera el CLSID de la página de propiedades asociada a la propiedad especificada.  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>Comentarios  
 ATL usa asignación de propiedad del objeto para obtener esta información.  
  
 Vea [IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) en el SDK de Windows.  
  
## <a name="see-also"></a>Vea también  
 [IPropertyPageImpl (clase)](../../atl/reference/ipropertypageimpl-class.md)   
 [Clase de ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Información general de clases](../../atl/atl-class-overview.md)
