---
title: Mapas de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 313e465698da5799a107bc3bdbeb6d2cbbe47303
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dispatch-maps"></a>Mapas de envío
Automatización OLE proporciona métodos para llamar a métodos y tener acceso a propiedades en todas las aplicaciones. El mecanismo proporcionado por la biblioteca Microsoft Foundation Class para enviar estas solicitudes es el "mapa de envíos", que designa los nombres internos y externos de funciones de objetos y propiedades, así como los tipos de datos de las propiedades en Sí y de argumentos de función.  
  
### <a name="dispatch-maps"></a>Mapas de envío  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Declara que se utilizará un mapa de envíos para exponer métodos y propiedades (debe usarse en la declaración de clase) de una clase.|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Inicia la definición de un mapa de envíos.|  
|[END_DISPATCH_MAP](#end_dispatch_map)|Termina la definición de un mapa de envíos.|  
|[DISP_FUNCTION](#disp_function)|Se utiliza en un mapa de envíos para definir una función de automatización OLE.|  
|[DISP_PROPERTY](#disp_property)|Define una propiedad de automatización OLE.|  
|[DISP_PROPERTY_EX](#disp_property_ex)|Define una propiedad de automatización OLE y nombres de las funciones Get y Set.|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Define una propiedad de automatización OLE con notificación.|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Define una propiedad de automatización OLE que toma parámetros y nombres de las funciones Get y Set.|  
|[DISP_DEFVALUE](#disp_defvalue)|Convierte el valor predeterminado de un objeto de una propiedad existente.|  
  
##  <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP  
 Si un `CCmdTarget`-clase derivada en el programa es compatible con la automatización OLE, que la clase debe proporcionar un mapa de envíos para exponer sus métodos y propiedades.  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Comentarios  
 Use la `DECLARE_DISPATCH_MAP` macro al final de la declaración de clase. A continuación, en el. Las funciones de los archivos CPP que define el miembro de la clase, use la `BEGIN_DISPATCH_MAP` macro. A continuación, incluir entradas de macro para cada una de la clase del expone métodos y propiedades ( `DISP_FUNCTION`, `DISP_PROPERTY`, y así sucesivamente). Por último, utilice la `END_DISPATCH_MAP` macro.  
  
> [!NOTE]
>  Si declara los miembros después `DECLARE_DISPATCH_MAP`, debe especificar un nuevo tipo de acceso ( **público**, `private`, o `protected`) para ellos.  
  
 Los asistentes de Asistente para aplicaciones y código ayudar en la creación de clases de automatización así como en el mantenimiento de mapas de envío. Para obtener más información sobre los mapas de envío, consulte [servidores de automatización](../../mfc/automation-servers.md).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxwin.h  

##  <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP  
 Declara la definición de su mapa de envíos.  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Especifica el nombre de la clase a la que pertenece este mapa de envíos.  
  
 `baseClass`  
 Especifica el nombre de clase base `theClass`.  
  
### <a name="remarks"></a>Comentarios  
 En el archivo de implementación (.cpp) que define las funciones de miembro para la clase, inicie el mapa de envíos con la `BEGIN_DISPATCH_MAP` macro, agregue entradas de macro para cada una de las propiedades y funciones de envío y completar el mapa de envíos con la `END_DISPATCH_MAP` macro.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h  

##  <a name="end_dispatch_map"></a>  END_DISPATCH_MAP  
 Termina la definición de su mapa de envíos.  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Comentarios  
 Se debe usar junto con `BEGIN_DISPATCH_MAP`.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h  

##  <a name="disp_function"></a>  DISP_FUNCTION  
 Define una función de automatización OLE en un mapa de envíos.  
  
```   
DISP_FUNCTION(
  theClass, 
  pszName, 
  pfnMember, 
  vtRetVal, 
  vtsParams)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Nombre de la clase.  
  
 `pszName`  
 Nombre externo de la función.  
  
 `pfnMember`  
 Nombre de la función miembro.  
  
 `vtRetVal`  
 Valor que especifica el tipo de valor devuelto de la función.  
  
 `vtsParams`  
 Una lista separada por espacios de una o varias constantes que especifica la lista de parámetros de la función.  
  
### <a name="remarks"></a>Comentarios  
 El `vtRetVal` argumento es del tipo **VARTYPE**. Los siguientes valores posibles para este argumento se toman de la `VARENUM` enumeración:  
  
|Símbolo|Tipo devuelto|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 El `vtsParams` argumento es una lista separada por espacios de valores de la **VTS_** constantes. Uno o varios de estos valores separados por espacios (no por comas) especifican la lista de parámetros de la función. Por ejemplo, 
  
 [!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 Especifica una lista que contiene un entero corto seguido por un puntero a un entero corto.  
  
 El **VTS_** constantes y sus significados son los siguientes:  
  
|Símbolo|Tipo de parámetro|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**Float**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**CY const** o **CY\***|  
|**VTS_DATE**|**DATE**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**VARIANTE const\***  o **VARIANT &**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**Corto\***|  
|**VTS_PI4**|**Long\***|  
|**VTS_PR4**|**Float\***|  
|**VTS_PR8**|**Doble\***|  
|**VTS_PCY**|**CY\***|  
|**VTS_PDATE**|**FECHA\***|  
|**VTS_PBSTR**|**BSTR\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\***|  
|**VTS_PSCODE**|**SCODE\***|  
|**VTS_PBOOL**|**BOOL\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\***|  
|**VTS_NONE**|Sin parámetros|  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h 

##  <a name="disp_property"></a>  DISP_PROPERTY  
 Define una propiedad de automatización OLE en un mapa de envíos.  
  
```   
DISP_PROPERTY(
  theClass, 
  pszName, 
  memberName, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Nombre de la clase.  
  
 `pszName`  
 Nombre externo de la propiedad.  
  
 `memberName`  
 Nombre de la variable de miembro en el que se almacena la propiedad.  
  
 `vtPropType`  
 Valor que especifica el tipo de propiedad.  
  
### <a name="remarks"></a>Comentarios  
 El `vtPropType` argumento es del tipo **VARTYPE**. Los valores posibles para este argumento se toman de la `VARENUM` enumeración:  
  
|Símbolo|**Tipo de propiedad**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Cuando un cliente externo cambia la propiedad, el valor de la variable de miembro especificado por `memberName` cambia; no hay ninguna notificación del cambio.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h 

##  <a name="disp_property_ex"></a>  DISP_PROPERTY_EX  
 Define una propiedad de automatización OLE y el nombre de las funciones utilizadas para obtener y establecer el valor de propiedad en un mapa de envíos.  
  
```   
DISP_PROPERTY_EX(
  theClass, 
  pszName, 
  memberGet, 
  memberSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Nombre de la clase.  
  
 `pszName`  
 Nombre externo de la propiedad.  
  
 `memberGet`  
 Nombre de la función de miembro que se utiliza para obtener la propiedad.  
  
 `memberSet`  
 Nombre de la función de miembro que se usa para establecer la propiedad.  
  
 `vtPropType`  
 Valor que especifica el tipo de propiedad.  
  
### <a name="remarks"></a>Comentarios  
 El `memberGet` y `memberSet` funciones tengan firmas determinadas por la `vtPropType` argumento. El `memberGet` función no toma ningún argumento y devuelve un valor del tipo especificado por `vtPropType`. El `memberSet` función toma un argumento del tipo especificado por `vtPropType` y no devuelve nada.  
  
 El `vtPropType` argumento es del tipo **VARTYPE**. Los valores posibles para este argumento se toman de la `VARENUM` enumeración. Para obtener una lista de estos valores, vea la sección Comentarios para el `vtRetVal` parámetro en [DISP_FUNCTION](#disp_function). Tenga en cuenta que `VT_EMPTY`, enumerado en el `DISP_FUNCTION` comentarios, no se permite como un tipo de datos de propiedad.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h 

##  <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY  
 Define una propiedad de automatización OLE con notificación en un mapa de envíos.  
  
```   
DISP_PROPERTY_NOTIFY(
  theClass, 
  szExternalName, 
  memberName, 
  pfnAfterSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Nombre de la clase.  
  
 `szExternalName`  
 Nombre externo de la propiedad.  
  
 `memberName`  
 Nombre de la variable de miembro en el que se almacena la propiedad.  
  
 `pfnAfterSet`  
 Nombre de la función de notificación para `szExternalName`.  
  
 `vtPropType`  
 Valor que especifica el tipo de propiedad.  
  
### <a name="remarks"></a>Comentarios  
 A diferencia de propiedades definidas con `DISP_PROPERTY`, definida con una propiedad `DISP_PROPERTY_NOTIFY` llaman automáticamente a la función especificada por `pfnAfterSet` cuando se cambia la propiedad.  
  
 El `vtPropType` argumento es del tipo **VARTYPE**. Los valores posibles para este argumento se toman de la `VARENUM` enumeración:  
  
|Símbolo|**Tipo de propiedad**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h 

##  <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM  
 Define una propiedad que se obtiene acceso con independiente **obtener** y `Set` funciones miembro.  
  
```   
DISP_PROPERTY_PARAM(
  theClass, 
  pszExternalName, 
  pfnGet, 
  pfnSet, 
  vtPropType,
  vtsParams)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Nombre de la clase.  
  
 *pszExternalName*  
 Nombre externo de la propiedad.  
  
 `pfnGet`  
 Nombre de la función de miembro que se utiliza para obtener la propiedad.  
  
 `pfnSet`  
 Nombre de la función de miembro que se usa para establecer la propiedad.  
  
 `vtPropType`  
 Valor que especifica el tipo de propiedad.  
  
 `vtsParams`  
 Una cadena separada por espacios **VTS_** tipos de parámetro variant, uno para cada parámetro.  
  
### <a name="remarks"></a>Comentarios  
 A diferencia de la `DISP_PROPERTY_EX` (macro), esta macro le permite especificar una lista de parámetros para la propiedad. Esto es útil para implementar propiedades indizadas o con parámetros.  
  
### <a name="example"></a>Ejemplo  
 Considere la siguiente declaración de get y miembro del grupo de funciones que permiten al usuario a solicitar una fila y columna específicas al obtener acceso a la propiedad:  
  
 [!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 Estos valores se corresponden al siguiente `DISP_PROPERTY_PARAM` macro en el mapa de envíos del control:  
  
 [!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 Como otro ejemplo, considere la posibilidad de get siguiente y miembro del grupo de funciones:  
  
 [!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 Estos valores se corresponden al siguiente `DISP_PROPERTY_PARAM` macro en el mapa de envíos del control:  
  
 [!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h 

##  <a name="disp_defvalue"></a>  DISP_DEFVALUE  
 Convierte el valor predeterminado de un objeto de una propiedad existente.  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>Parámetros  
 `theClass`  
 Nombre de la clase.  
  
 `pszName`  
 Nombre externo de la propiedad que representa el "valor" del objeto.  
  
### <a name="remarks"></a>Comentarios  
 Con un valor predeterminado, puede realizar el proceso de programar el objeto de automatización más sencillo para aplicaciones de Visual Basic.  
  
 El "valor predeterminado" del objeto es la propiedad que se recuperan o se establecen cuando una referencia a un objeto no especifica una propiedad o función miembro.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** afxdisp.h 

## <a name="see-also"></a>Vea también  
 [Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md)
