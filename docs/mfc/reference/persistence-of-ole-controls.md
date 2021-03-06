---
title: Persistencia de los controles OLE | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e84e26bae83bd131b53d10e4561ddb60854a8a5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="persistence-of-ole-controls"></a>Persistencia de los controles OLE
Capacidad de uno de los controles OLE es persistencia de propiedad (o serialización), que permite que el control OLE leer o escribir valores de propiedad a y desde un archivo o secuencia. Una aplicación de contenedor puede utilizar la serialización para almacenar valores de propiedad de un control incluso después de que la aplicación ha destruido el control. Los valores de propiedad del control OLE, a continuación, se pueden leer desde el archivo o secuencia cuando una nueva instancia del control se crea en un momento posterior.  
  
### <a name="persistence-of-ole-controls"></a>Persistencia de los controles OLE  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|Intercambia una propiedad de control que almacena los datos de objeto binario grande (BLOB).|  
|[PX_Bool](#px_bool)|Intercambia una propiedad de control de tipo **BOOL**.|  
|[PX_Color](#px_color)|Intercambia una propiedad de color de un control.|  
|[PX_Currency](#px_currency)|Intercambia una propiedad de control de tipo **CY**.|  
|[PX_DataPath](#px_datapath)|Intercambia una propiedad de control de tipo `CDataPathProperty`.|  
|[PX_Double](#px_double)|Intercambia una propiedad de control de tipo **doble**.|  
|[PX_Font](#px_font)|Intercambia una propiedad de fuente de un control.|  
|[PX_Float](#px_float)|Intercambia una propiedad de control de tipo **float**.|  
|[PX_IUnknown](#px_iunknown)|Intercambia una propiedad de control de un tipo no definido.|  
|[PX_Long](#px_long)|Intercambia una propiedad de control de tipo **largo**.|  
|[PX_Picture](#px_picture)|Intercambia una propiedad de imagen de un control.|  
|[PX_Short](#px_short)|Intercambia una propiedad de control de tipo **corto**.|  
|[PX_ULong](#px_ulong)|Intercambia una propiedad de control de tipo **ULONG**.|  
|[PX_UShort](#px_ushort)|Intercambia una propiedad de control de tipo **USHORT**.|  
|[PXstring](#px_string)|Intercambia una propiedad de control de la cadena de caracteres.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|Intercambia VBX relacionadas con la fuente propiedades de un control en una propiedad de fuente del control OLE.|  
  
 Además, el `AfxOleTypeMatchGuid` se proporciona una función global para buscar una coincidencia entre un `TYPEDESC` y un GUID determinado.  
  
##  <a name="px_blob"></a>  PX_Blob  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad que almacena los datos de objeto binario grande (BLOB).  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `hBlob`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `hBlobDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad se ser de lectura o escritura a la variable al que hace referencia `hBlob`, según corresponda. Esta variable se debe inicializar para **NULL** antes de llamar inicialmente a `PX_Blob` por primera vez (por lo general, esto puede hacerse en el constructor del control). Si `hBlobDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por cualquier motivo, no se puede proceso de inicialización o la serialización del control.  
  
 Los identificadores de `hBlob` y `hBlobDefault` hacen referencia a un bloque de memoria que contiene lo siguiente:  
  
-   Un `DWORD` que contiene la longitud, en bytes, de los datos binarios que sigue, seguido inmediatamente por  
  
-   Un bloque de memoria que contiene los datos binarios reales.  
  
 Tenga en cuenta que `PX_Blob` asignará memoria, con las ventanas de [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) API, al cargar las propiedades de tipo BLOB. Usted es responsable de liberar esta memoria. Por consiguiente, debe llamar al destructor del control de [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) en cualquier propiedad de tipo BLOB identificadores para liberar una copia de seguridad cualquier memoria asignada al control.  
  
##  <a name="px_bool"></a>  PX_Bool  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **BOOL**.  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `bValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `bDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad se ser de lectura o escritura a la variable al que hace referencia `bValue`, según corresponda. Si `bDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_color"></a>  PX_Color  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **OLE_COLOR**.  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `clrValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `clrDefault`  
 Valor predeterminado para la propiedad, tal como se define por el desarrollador del control.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad se ser de lectura o escritura a la variable al que hace referencia `clrValue`, según corresponda. Si `clrDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_currency"></a>  PX_Currency  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **moneda**.  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `cyValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `cyDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad se ser de lectura o escritura a la variable al que hace referencia `cyValue`, según corresponda. Si `cyDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_datapath"></a>  PX_DataPath  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de ruta de acceso de datos de tipo [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `dataPathProperty`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Propiedades de ruta de acceso de datos implementan propiedades de control asincrónico. Valor de la propiedad se ser de lectura o escritura a la variable al que hace referencia `dataPathProperty`, según corresponda.  
  
##  <a name="px_double"></a>  PX_Double  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **doble**.  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `doubleValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `doubleDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `doubleValue`, según corresponda. Si `doubleDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_font"></a>  PX_Font  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de fuente de tipo.  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `font`  
 Una referencia a un `CFontHolder` objeto que contiene la propiedad font.  
  
 `pFontDesc`  
 Un puntero a un **FONTDESC** estructura que contiene los valores que se usarán al inicializar el estado predeterminado de la propiedad de fuente, en el caso donde `pFontDispAmbient` es **NULL**.  
  
 `pFontDispAmbient`  
 Un puntero a la **IFontDisp** interfaz de una fuente que se va a utilizar al inicializar el estado predeterminado de la propiedad font.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escrito a `font`, un `CFontHolder` de referencia, cuando sea necesario. Si `pFontDesc` y `pFontDispAmbient` se especifica, se utilizan para inicializar el valor de propiedad predeterminado, cuando sea necesario. Estos valores se usan si, por cualquier motivo, no se puede proceso de serialización del control. Por lo general, pasar **NULL** para `pFontDesc` y el valor ambiente devuelto por `COleControl::AmbientFont` para `pFontDispAmbient`. Tenga en cuenta que el objeto de fuente devuelto por `COleControl::AmbientFont` debe liberarse mediante una llamada a la **IFontDisp::Release** función miembro.  
  
##  <a name="px_float"></a>  PX_Float  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **float**.  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `floatValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `floatDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `floatValue`, según corresponda. Si `floatDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_iunknown"></a>  PX_IUnknown  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad representada por un objeto con un **IUnknown**-interfaz derivada.  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 *pUnk*  
 Referencia a una variable que contiene la interfaz del objeto que representa el valor de la propiedad.  
  
 `iid`  
 Un identificador de interfaz que indica qué interfaz del objeto de propiedad se utiliza el control.  
  
 `pUnkDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia *pUnk*, según corresponda. Si `pUnkDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_long"></a>  PX_Long  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **largo**.  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `lValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `lDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `lValue`, según corresponda. Si `lDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_picture"></a>  PX_Picture  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de imagen del control.  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `pict`  
 Referencia a un [CPictureHolder](../../mfc/reference/cpictureholder-class.md) donde se almacena la propiedad de objeto (normalmente una variable de miembro de la clase).  
  
 `pictDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `pict`, según corresponda. Si `pictDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_short"></a>  PX_Short  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **corto**.  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `sValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `sDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `sValue`, según corresponda. Si `sDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_ulong"></a>  PX_ULong  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo **ULONG**.  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 Nombre de la propiedad que se va a intercambiar.  
  
 `ulValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `ulDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `ulValue`, según corresponda. Si `ulDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_ushort"></a>  PX_UShort  
 Llame a esta función en el control `DoPropExchange` función de miembro para serializar o inicializar una propiedad de tipo `unsigned` **corto**.  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 Nombre de la propiedad que se va a intercambiar.  
  
 *usValue*  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 *usDefault*  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia *usValue*, según corresponda. Si *usDefault* se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_string"></a>  PXstring  
 Llame a esta función en el control **DoPropExchange** función de miembro para serializar o inicializar una propiedad de cadena de caracteres.  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `pszPropName`  
 El nombre de la propiedad que se va a intercambiar.  
  
 `strValue`  
 Referencia a la variable donde se almacena la propiedad (normalmente una variable de miembro de la clase).  
  
 `strDefault`  
 Valor predeterminado para la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Valor de la propiedad es de lectura o escritura a la variable al que hace referencia `strValue`, según corresponda. Si `strDefault` se especifica, se usará como valor predeterminado de la propiedad. Este valor se utiliza si, por alguna razón, falla el proceso de serialización del control.  
  
##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert  
 Llame a esta función en el control `DoPropExchange` función de miembro para inicializar una propiedad de fuente mediante la conversión de propiedades de relacionadas con la fuente de un control VBX.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pPX`  
 Puntero a la [CPropExchange](../../mfc/reference/cpropexchange-class.md) objeto (normalmente se pasa como un parámetro para `DoPropExchange`).  
  
 `font`  
 La propiedad font del control OLE que contiene las propiedades relacionadas con la fuente VBX convertidas.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el intercambio se realizó correctamente; 0 si no lo consigue.  
  
### <a name="remarks"></a>Comentarios  
 Esta función debe usarse únicamente por un control OLE que se ha diseñado como un reemplazo para un control VBX directa. Cuando el entorno de desarrollo de Visual Basic convierte un formulario que contenga un control VBX para usar el control OLE de reemplazo correspondiente, llamará el control **IDataObject:: SetData** estableció pasando una propiedad de la función, que contiene los datos de propiedad del control VBX. Esta operación, a su vez, hace que el control `DoPropExchange` función va a invocar. `DoPropExchange` puede llamar a `PX_VBXFontConvert` para convertir las VBX propiedades del control relacionadas con la fuente (por ejemplo, "FontName," "FontSize", y así sucesivamente) en los componentes correspondientes de la propiedad font del control OLE.  
  
 `PX_VBXFontConvert` solo debe llamarse cuando el control realmente se está convirtiendo desde una aplicación de formulario VBX. Por ejemplo:  
  
 [!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md)
