---
title: Funciones globales de notificación de errores y depuración | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb3257b5205587b27a83671ed8e610aad5373eef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="debugging-and-error-reporting-global-functions"></a>Funciones globales de notificación de errores y depuración
Estas funciones proporcionan funciones de seguimiento y depuración útiles.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Devuelve un `GetLastError` código de error en el formato HRESULT.|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Convierte un código de error Win32 en un valor HRESULT.|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Configura **IErrorInfo** para proporcionar detalles del error a un cliente.|  
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Produce una excepción `CAtlException`.|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Llame a esta función para notificar un error en función del resultado de la función de Windows `GetLastError`.|  
  
##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError  
 Devuelve el último valor de código de error del subproceso que realiza la llamada con el formato HRESULT.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Comentarios  
 `AtlHresultFromLastError` llamadas `GetLastError` para obtener el último error y devuelve el error después de convertir en un valor HRESULT con el **HRESULT_FROM_WIN32** macro.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcomcli.h  

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32  
 Convierte un código de error Win32 en un valor HRESULT.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Parámetros  
 *Error*  
 Para convertir el valor de error.  
  
### <a name="remarks"></a>Comentarios  
 Convierte un código de error de Win32 en un valor de HRESULT, mediante la macro **HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  En lugar de usar **HRESULT_FROM_WIN32(GetLastError())**, use la función [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcomcli.h  

##  <a name="atlreporterror"></a>  AtlReportError  
 Configura el `IErrorInfo` interfaz para proporcionar información de error a los clientes del objeto.  
  
```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>Parámetros  
 `clsid`  
 [in] Identificador CLSID del objeto que notifica el error.  
  
 `lpszDesc`  
 [in] La cadena que describe el error. Especifican las versiones de Unicode que `lpszDesc` es de tipo **LPCOLESTR**; la versión ANSI especifica un tipo de `LPCSTR`.  
  
 `iid`  
 [in] El IID de la interfaz que define el error o `GUID_NULL` si el error se ha definido por el sistema operativo.  
  
 `hRes`  
 [in] El `HRESULT` desea devolver al llamador.  
  
 `nID`  
 [in] El identificador de recurso donde se almacena la cadena de descripción del error. Este valor debe estar comprendida entre 0 x 0200 y 0xFFFF, ambos inclusive. En las compilaciones de depuración, un **ASSERT** se producirá si `nID` no indiza una cadena válida. En versiones de lanzamiento, la cadena de descripción del error se establecerá en "Error desconocido".  
  
 `dwHelpID`  
 [in] El identificador de contexto de ayuda para el error.  
  
 `lpszHelpFile`  
 [in] La ruta de acceso y el nombre del archivo de ayuda que describe el error.  
  
 `hInst`  
 [in] El identificador del recurso. De forma predeterminada, este parámetro es **__AtlBaseModuleModule::GetResourceInstance**, donde **__AtlBaseModuleModule** es la instancia global de [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) o una clase derivan de él.  
  
### <a name="return-value"></a>Valor devuelto  
 Si el `hRes` parámetro es distinto de cero, se devuelve el valor de `hRes`. Si `hRes` es cero, entonces las cuatro primeras versiones de `AtlReportError` devolver `DISP_E_EXCEPTION`. Las dos últimas versiones devuelven el resultado de la macro **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Comentarios  
 La cadena *lpszDesc* se utiliza como la descripción de texto del error. Cuando el cliente recibe la `hRes` volver del `AtlReportError`, el cliente puede tener acceso a la **IErrorInfo** estructura para obtener más información sobre el error.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  No utilice `AtlReportError` en C++ controladores catch. Algunas invalidaciones de estas funciones usan las macros de conversión de cadena ATL internamente, que a su vez utilizan el `_alloca` función internamente. Usar `AtlReportError` en un bloque catch de C++ controlador puede producir excepciones en los controladores catch de C++.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlcom.h  
    
##  <a name="atlthrow"></a>  AtlThrow  
 Llame a esta función para notificar un error en función de un código de estado `HRESULT`.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Parámetros  
 `hr`  
 Valor HRESULT estándar.  
  
### <a name="remarks"></a>Comentarios  
 Esta función se utiliza por código de MFC y ATL si se produce una condición de error. También puede llamarlo desde su propio código. La implementación predeterminada de esta función depende de la definición del símbolo **_ATL_NO_EXCEPTIONS** y el tipo de proyecto, MFC o ATL.  
  
 En todos los casos, esta función realiza un seguimiento el HRESULT al depurador.  
  
 En Visual Studio 2015 Update 3 y versiones posteriores, esta función es con atributos __declspec (noreturn) para evitar advertencias de SAL falsas.  
  
 Si **_ATL_NO_EXCEPTIONS** no está definido en un proyecto MFC, esta función genera un [CMemoryException](../../mfc/reference/cmemoryexception-class.md) o un [COleException](../../mfc/reference/coleexception-class.md) según el valor de HRESULT.  
  
 Si **_ATL_NO_EXCEPTIONS** no está definido en un proyecto ATL, la función inicia genera un [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Si **_ATL_NO_EXCEPTIONS** está definido, la función genera un error de aserción en lugar de producir una excepción.  
  
 Para los proyectos ATL, es posible proporcionar su propia implementación de esta función que va a usar ATL si se produce un error. Para ello, defina su propia función con la misma firma que `AtlThrow` y #define `AtlThrow` para que sea el nombre de la función. Esto debe hacerse antes de incluir atlexcept.h (lo que significa que se debe hacer antes de incluir encabezados ATL porque atlbase.h incluye atlexcept.h). Atributo de la función `__declspec(noreturn)` para evitar advertencias de SAL falsas.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldef.h  

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32  
 Llame a esta función para notificar un error en función del resultado de la función de Windows `GetLastError`.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Comentarios  
 Esta función realiza el seguimiento de los resultados de `GetLastError` al depurador.  
  
 Si **_ATL_NO_EXCEPTIONS** no está definido en un proyecto MFC, esta función genera un [CMemoryException](../../mfc/reference/cmemoryexception-class.md) o un [COleException](../../mfc/reference/coleexception-class.md) en función del valor devuelto por `GetLastError`.  
  
 Si **_ATL_NO_EXCEPTIONS** no está definido en un proyecto ATL, la función inicia genera un [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Si **_ATL_NO_EXCEPTIONS** está definido, la función genera un error de aserción en lugar de producir una excepción.  

## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldef.h  
   
     
## <a name="see-also"></a>Vea también  
 [Funciones](../../atl/reference/atl-functions.md)   
 [Macros de depuración e informe de errores](../../atl/reference/debugging-and-error-reporting-macros.md)









