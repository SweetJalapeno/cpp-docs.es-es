---
title: Clase CInternetException | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6908b72f30b3a2561f7091b912e8144f2b763cc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cinternetexception-class"></a>Clase CInternetException
Representa una condición de excepción relacionada con una operación de Internet.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Construye un objeto `CInternetException`.|  
  
### <a name="public-data-members"></a>Miembros de datos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|El valor de contexto asociado a la operación que produjo la excepción.|  
|[CInternetException::m_dwError](#m_dwerror)|El error que provocó la excepción.|  
  
## <a name="remarks"></a>Comentarios  
 La `CInternetException` clase incluye dos miembros de datos públicos: uno contiene el código de error asociado a la excepción y el otro contiene el identificador de contexto de la aplicación de Internet asociado con el error.  
  
 Para obtener más información acerca de los identificadores de contexto para las aplicaciones de Internet, vea el artículo [programación para Internet con WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxinet.h  
  
##  <a name="cinternetexception"></a>  CInternetException::CInternetException  
 Esta función miembro se llama cuando un `CInternetException` se crea el objeto.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwError`  
 El error que provocó la excepción.  
  
### <a name="remarks"></a>Comentarios  
 Para producir un CInternetException, llame a la función global de MFC [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).  
  
##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext  
 El valor de contexto asociado a la operación de Internet relacionada.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Comentarios  
 El identificador de contexto se especificó originalmente en [CInternetSession](../../mfc/reference/cinternetsession-class.md) y pasa a la biblioteca MFC [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- y [CInternetFile](../../mfc/reference/cinternetfile-class.md)-las clases derivadas. Puede invalidar este comportamiento predeterminado y asignar cualquiera `dwContext` parámetro un valor de su elección. `dwContext` se asocia a cualquier operación del objeto determinado. `dwContext` identifica la información de estado de la operación devuelta por [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>  CInternetException::m_dwError  
 El error que provocó la excepción.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Comentarios  
 Este valor de error puede ser un sistema de código de error, se encuentra en el archivo WINERROR. H, o un valor de error de WININET. H.  
  
 Para obtener una lista de códigos de error de Win32, vea [códigos de Error](http://msdn.microsoft.com/library/windows/desktop/ms681381). Para obtener una lista de mensajes de error de Internet específicos, consulte. Ambos temas se encuentran en el SDK de Windows.  
  
## <a name="see-also"></a>Vea también  
 [CException (clase)](../../mfc/reference/cexception-class.md)   
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [CException (clase)](../../mfc/reference/cexception-class.md)
