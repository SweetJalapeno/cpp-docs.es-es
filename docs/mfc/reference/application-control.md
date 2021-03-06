---
title: Control de la aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76d8ec079a7c3534211118e60c1d9d95a3a8510a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="application-control"></a>Control de la aplicación
OLE requiere un control considerable sobre las aplicaciones y sus objetos. La DLL del sistema OLE deben ser capaz de iniciar automáticamente la versión de las aplicaciones, coordinar su producción y la modificación de objetos y así sucesivamente. Las funciones en este tema cumplen dichos requisitos. Además de llamarse por la DLL del sistema OLE, estas funciones se deben llamar a veces también las aplicaciones. 
  
### <a name="application-control"></a>Control de la aplicación  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Indica si la aplicación puede finalizar.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Recupera el filtro de mensajes de la aplicación actual.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Recupera la marca de control de usuario actual.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Establece o borra la marca de control de usuario.|  
|[AfxOleLockApp](#afxolelockapp)|Incrementa el recuento de global del marco de trabajo del número de objetos activos de una aplicación.|  
|[AfxOleLockControl](#afxolelockcontrol)| Bloquea el generador de clases del control especificado. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Disminuye recuento del marco de trabajo del número de objetos activos de una aplicación.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Desbloquea el generador de clases del control especificado. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Registra un servidor en el registro del sistema OLE.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Implementa la interfaz de usuario para la *typename* objeto de comando.|  

  
##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp  
 Indica si la aplicación puede finalizar.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la aplicación puede cerrarse; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Una aplicación no debe finalizar si hay referencias pendientes a sus objetos. Las funciones globales `AfxOleLockApp` y `AfxOleUnlockApp` incremento y decremento, respectivamente, un contador de referencias a objetos de la aplicación. La aplicación no debería finalizar cuando este contador es distinto de cero. Si el contador es distinto de cero, la ventana principal de la aplicación está oculto (no destruido) cuando el usuario elige cerrar en el menú de sistema o la salida en el menú archivo. El marco de trabajo llama a esta función **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Requisitos  
 **Encabezado**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter  
 Recupera el filtro de mensajes de la aplicación actual.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero para el filtro de mensajes actual.  
  
### <a name="remarks"></a>Comentarios  
 Llame a esta función para obtener acceso a la actual `COleMessageFilter`-derivadas objeto, tal y como se llamaría a `AfxGetApp` para tener acceso al objeto de aplicación actual.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl  
 Recupera la marca de control de usuario actual.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el usuario está en el control de la aplicación; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 El usuario está en el control de la aplicación cuando el usuario tiene abierto explícitamente o se crea un nuevo documento. El usuario es también en el control si la aplicación no se ha iniciado por la DLL del sistema OLE, es decir, si el usuario inicia la aplicación con el shell del sistema.  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl  
 Establece o borra la marca de control de usuario, que se explica en la referencia para `AfxOleGetUserCtrl`.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Parámetros  
 *bUserCtrl*  
 Especifica si la marca de control de usuario se puede establecer ni borrar.  
  
### <a name="remarks"></a>Comentarios  
 El marco de trabajo llama a esta función cuando el usuario crea o carga un documento, pero no cuando se carga o se creó mediante una acción indirecta, como la carga de un objeto incrustado desde una aplicación de contenedor de un documento.  
  
 Llame a esta función si otras acciones en su aplicación deben colocar el usuario en el control de la aplicación.  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp  
 Incrementa el recuento de global del marco de trabajo del número de objetos activos de la aplicación.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Comentarios  
 El marco de trabajo mantiene un recuento del número de objetos activos en una aplicación. El `AfxOleLockApp` y `AfxOleUnlockApp` funciones, respectivamente, aumentar y disminuir este número.  
  
 Cuando el usuario intenta cerrar una aplicación que tiene objetos activos: una aplicación para que el recuento de objetos activos es distinto de cero, el marco de trabajo oculta la aplicación desde la vista del usuario en lugar de apagarlo por completo. El `AfxOleCanExitApp` función indica si la aplicación puede finalizar.  
  
 Llame a `AfxOleLockApp` de cualquier objeto que expone interfaces OLE, si sería deseable para dicho objeto se destruye mientras se siguen en uso en una aplicación cliente. Llamar a `AfxOleUnlockApp` en el destructor de cualquier objeto que llama a `AfxOleLockApp` en el constructor. De forma predeterminada, `COleDocument` (y sus clases derivadas) automáticamente bloquear y desbloquear la aplicación.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  AfxOleUnlockApp  
 Disminuye recuento del marco de trabajo de objetos activos de la aplicación.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Comentarios  
 Consulte `AfxOleLockApp` para obtener más información.  
  
 Cuando el número de objetos activos llega a cero, **AfxOleOnReleaseAllObjects** se llama.  
  
### <a name="example"></a>Ejemplo  
 Vea el ejemplo de [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
Bloquea el generador de clases de control especificado para que los datos creados de forma dinámica asociadas con el control permanecen en memoria.  
   
### <a name="syntax"></a>Sintaxis    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parámetros  
 `clsid`  
 El identificador de clase único del control.  
  
 `lpszProgID`  
 El identificador de programa único del control.  
   
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el generador de clases del control ha bloqueado correctamente; en caso contrario es 0.  
   
### <a name="remarks"></a>Comentarios  
 Esto puede aumentar significativamente la velocidad presentación de los controles. Por ejemplo, una vez al crear un control en un cuadro de diálogo y bloquear el control con `AfxOleLockControl`, no es necesario crear y eliminar de nuevo cada vez que se muestra el cuadro de diálogo o se destruya. Si el usuario abre y cierra un cuadro de diálogo varias veces, los controles de bloqueo puede mejorar significativamente el rendimiento. Cuando esté preparado para destruir el control, llame a `AfxOleUnlockControl`.  
   
### <a name="example"></a>Ejemplo  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>Requisitos  
 **Encabezado:** < afxwin.h >  
   
### <a name="see-also"></a>Vea también  
 [Macros y funciones globales](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass  
 Esta función permite registrar el servidor en el registro del sistema OLE.  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>Parámetros  
 `clsid`  
 Referencia al Id. del servidor OLE  
  
 `lpszClassName`  
 Puntero a una cadena que contiene el nombre de clase de objetos del servidor.  
  
 *lpszShortTypeName*  
 Puntero a una cadena que contiene el nombre corto del tipo de objeto del servidor, como "Gráfico".  
  
 *lpszLongTypeName*  
 Puntero a una cadena que contiene el nombre largo del tipo de objeto del servidor, como "Gráfico de Microsoft Excel 5.0."  
  
 `nAppType`  
 Un valor, tomado de la **OLE_APPTYPE** enumeración, que especifica el tipo de aplicación OLE. Los valores posibles son los siguientes:  
  
- `OAT_INPLACE_SERVER` Servidor tiene interfaz de usuario completa del servidor.  
  
- `OAT_SERVER` El servidor admite solo incrustar.  
  
- `OAT_CONTAINER` Contenedor admite vínculos con incrustaciones.  
  
- `OAT_DISPATCH_OBJECT` `IDispatch`-objeto compatibles con.  
  
 `rglpszRegister`  
 Matriz de punteros a cadenas que representan las claves y los valores que se agregarán al registro del sistema OLE si no se encuentra ningún valor existente para las claves.  
  
 `rglpszOverwrite`  
 Matriz de punteros a cadenas que representan las claves y valores que se agregará al registro del sistema OLE si el registro contiene los valores existentes de las claves especificadas.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la clase de servidor se ha registrado correctamente; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Puede usar la mayoría de las aplicaciones **COleTemplateServer::Register** para registrar tipos de documento de la aplicación. Si el formato de registro del sistema de la aplicación no ajusta el patrón típico, puede usar `AfxOleRegisterServerClass` para tener más control.  
  
 El registro se compone de un conjunto de claves y valores. El `rglpszRegister` y `rglpszOverwrite` argumentos son matrices de punteros a cadenas, que consta de una clave y valor separan por un **NULL** caracteres ( `'\0'`). Cada una de estas cadenas puede tener parámetros reemplazables cuyos lugares están marcados por las secuencias de caracteres `%1` a través de `%5`.  
  
 Los símbolos se rellenan como sigue:  
  
|Símbolo|Valor|  
|------------|-----------|  
|%1|Id. de clase, con formato de cadena|  
|%2|Nombre de la clase|  
|%3|Ruta de acceso al archivo ejecutable|  
|%4|Nombre de tipo corto|  
|%5|Nombre de tipo Long|  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu  
 Implementa la interfaz de usuario para la *typename* objeto de comando.  
  
```   
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Parámetros  
 `pClient`  
 Un puntero al elemento de cliente OLE.  
  
 `pMenu`  
 Un puntero al objeto de menú para actualizarse.  
  
 *iMenuItem*  
 El índice del elemento de menú para actualizarse.  
  
 `nIDVerbMin`  
 El identificador de comando que se corresponde con el verbo principal.  
  
 *nIDVerbMax*  
 El identificador de comando que corresponde a la última verbo.  
  
 *nIDConvert*  
 Identificador para el elemento de menú de Convert.  
  
### <a name="remarks"></a>Comentarios  
 Si el servidor reconoce solo un verbo principal, se convierte en el elemento de menú "verbo *typename* objeto" y el `nIDVerbMin` comando se envía cuando el usuario elige el comando. Si el servidor reconoce varios verbos, a continuación, se convierte en el elemento de menú " *typename* objeto" y un submenú que enumera todos los verbos aparece cuando el usuario elige el comando. Cuando el usuario elige un verbo en el submenú, `nIDVerbMin` se envía si se elige el primer verbo, `nIDVerbMin` + 1 se envía si el segundo verbo es elegido y así sucesivamente. El valor predeterminado `COleDocument` implementación controla automáticamente esta característica.  
  
 Debe tener la siguiente instrucción de script de recursos de aplicación de su cliente (. Archivo RC):  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>Requisitos  
 **Encabezado**: afxole.h 

## <a name="see-also"></a>Vea también  
 [Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl
Desbloquea el generador de clases del control especificado.  
   
### <a name="syntax"></a>Sintaxis  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parámetros  
 `clsid`  
 El identificador de clase único del control.  
  
 `lpszProgID`  
 El identificador de programa único del control.  
   
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el generador de clases del control se ha desbloqueado correctamente; en caso contrario es 0.  
   
### <a name="remarks"></a>Comentarios  
 Un control se bloqueó con `AfxOleLockControl`, de modo que los datos creados de forma dinámica asociadas con el control permanecen en memoria. Esto puede acelerar considerablemente la presentación del control porque el control necesario no se crea y se destruye cada vez que se muestra. Cuando esté preparado para destruir el control, llame a `AfxOleUnlockControl`.  
   
### <a name="example"></a>Ejemplo  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>Requisitos  
 **Encabezado:** < afxwin.h >  
   
### <a name="see-also"></a>Vea también  
 [Macros y funciones globales](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)

