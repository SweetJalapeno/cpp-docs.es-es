---
title: Macros de entrada de la interfaz COM | Documentos de Microsoft
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c3ba41a05813c4112c1e5dd51bfe447d2c8debf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="cominterfaceentry-macros"></a>Macros COM_INTERFACE_ENTRY  
 Estas macros especificar interfaces de un objeto en su mapa de COM para que resulten accesibles por `QueryInterface`. El orden de las entradas del mapa COM es las interfaces de orden que se va a comprobar para hallar una coincidencia **IID** durante `QueryInterface`.  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|En el mapa de interfaz COM se especifican interfaces.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Use esta macro para eliminar la ambigüedad de dos bifurcaciones de herencia.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Utilice esta macro para entrar en la interfaz en el mapa de COM y especificar su IID.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Igual que [COM_INTERFACE_ENTRY2](#com_interface_entry2), excepto en que puede especificar un IID diferentes.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Cuando la interfaz identificada por `iid` se consulta, `COM_INTERFACE_ENTRY_AGGREGATE` reenvía a `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Igual que [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), salvo que consultar los IID da como resultado la consulta de reenvío `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Igual que [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), excepto si `punk` es **NULL**, crea automáticamente el agregado descrito por el `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Igual que [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), salvo que consultar los IID da como resultado la consulta de reenvío `punk`y si `punk` es **NULL**, creando automáticamente el agregado descrito por el `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Hace que el programa llamar a [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) cuando se consulta la interfaz especificada.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Guarda los datos específicos de la interfaz para cada instancia.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Expone las interfaces divisibles.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Procesa el mapa COM de la clase base cuando el procesamiento alcanza esta entrada en el mapa COM.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Un mecanismo general para enlazar con de ATL `QueryInterface` lógica.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Igual que [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), salvo que consultar los IID da como resultado una llamada a `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Devuelve **E_NOINTERFACE** y finaliza el procesamiento de asignación COM cuando se consulta la interfaz especificada para.|  

## <a name="requirements"></a>Requisitos
**Encabezado:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY
En el mapa de interfaz COM se especifican interfaces.

### <a name="syntax"></a>Sintaxis

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>Parámetros

x [in] el nombre de una interfaz de su objeto de clase se deriva directamente.

### <a name="remarks"></a>Comentarios
Normalmente, esto es el tipo de entrada que se utiliza con más frecuencia.

### <a name="example"></a>Ejemplo
```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```
### <a name="requirements"></a>Requisitos
**Encabezado:** atlcom.h
  
##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2  
 Use esta macro para eliminar la ambigüedad de dos bifurcaciones de herencia.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Parámetros  
 *x*  
 [in] El nombre de una interfaz que desea exponer desde el objeto.  
  
 `x2`  
 [in] El nombre de la rama de herencia desde el que *x* se expone.  
  
### <a name="remarks"></a>Comentarios  
 Por ejemplo, si se deriva el objeto de clase de dos interfaces duales, exponer `IDispatch` con `COM_INTERFACE_ENTRY2` desde `IDispatch` puede obtenerse de cualquiera de las interfaces.  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID  
 Utilice esta macro para entrar en la interfaz en el mapa de COM y especificar su IID.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID de la interfaz expuesta.  
  
 *x*  
 [in] El nombre de la clase cuyo vtable se expondrá como la interfaz identificada por `iid`.  
  
 
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID  
 Igual que [COM_INTERFACE_ENTRY2](#com_interface_entry2), excepto en que puede especificar un IID diferentes.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID que se va a especificar para la interfaz.  
  
 *x*  
 [in] El nombre de una interfaz que el objeto de clase se deriva directamente.  
  
 `x2`  
 [in] El nombre de una segunda interfaz que el objeto de clase se deriva directamente.  
  
##  <a name="com_interface_entry_aggregate"></a>  COM_INTERFACE_ENTRY_AGGREGATE  
 Cuando la interfaz identificada por `iid` se consulta, `COM_INTERFACE_ENTRY_AGGREGATE` reenvía a `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID de la interfaz de consulta.  
  
 `punk`  
 [in] El nombre de un **IUnknown** puntero.  
  
### <a name="remarks"></a>Comentarios  
 El `punk` se supone que el parámetro para que apunte a la desconocido interno de un agregado o a **NULL**, en cuyo caso se omite la entrada. Por lo general, debería **CoCreate** el agregado en `FinalConstruct`.  
  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 Igual que [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), salvo que consultar los IID da como resultado la consulta de reenvío `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Parámetros  
 `punk`  
 [in] El nombre de un **IUnknown** puntero.  
  
### <a name="remarks"></a>Comentarios  
 Si se produce un error en la consulta de la interfaz, el procesamiento de la asignación COM continúa.  
  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Igual que [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), excepto si `punk` es **NULL**, crea automáticamente el agregado descrito por el `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID de la interfaz de consulta.  
  
 `punk`  
 [in] El nombre de un **IUnknown** puntero. Debe ser un miembro de la clase que contiene la asignación COM.  
  
 `clsid`  
 [in] El identificador de la función de agregado que se creará si `punk` es **NULL**.  
  
### <a name="remarks"></a>Comentarios  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 Igual que [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), salvo que consultar los IID da como resultado la consulta de reenvío `punk`y si `punk` es **NULL**, creando automáticamente el agregado descrito por el `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Parámetros  
 `punk`  
 [in] El nombre de un **IUnknown** puntero. Debe ser un miembro de la clase que contiene la asignación COM.  
  
 `clsid`  
 [in] El identificador de la función de agregado que se creará si `punk` es **NULL**.  
  
### <a name="remarks"></a>Comentarios  
 Si se produce un error en la consulta de la interfaz, el procesamiento de la asignación COM continúa.  
  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK  
 Hace que el programa llamar a [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) cuando se consulta la interfaz especificada.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Parámetros  
 *x*  
 [in] Texto utilizado para construir el identificador de interfaz.  
  
### <a name="remarks"></a>Comentarios  
 La interfaz se construirá IID anexando *x* a `IID_`. Por ejemplo, si *x* es `IPersistStorage`, será el IID `IID_IPersistStorage`.  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Guarda los datos específicos de la interfaz para cada instancia.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID de la interfaz desplazable.  
  
 *x*  
 [in] El nombre de la clase que implementa la interfaz.  
  
 `punk`  
 [in] El nombre de un **IUnknown** puntero. Debe ser un miembro de la clase que contiene la asignación COM. Se debe inicializar para **NULL** en el constructor del objeto de clase.  
  
### <a name="remarks"></a>Comentarios  
 Si no se usa la interfaz, esto reduce el tamaño total de la instancia del objeto.  
  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF  
 Expone las interfaces divisibles.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID de la interfaz desplazable.  
  
 *x*  
 [in] El nombre de la clase que implementa la interfaz.  
  
### <a name="remarks"></a>Comentarios  
 Una interfaz desplazable se implementa como un objeto independiente que se crea una instancia cada vez que la interfaz representa se consulta para. Por lo general, compilar la interfaz como un desplazable si rara vez se usa la interfaz, ya que esto ahorra un puntero vtable en cada instancia del objeto principal. El desplazable se elimina cuando su recuento de referencias se convierte en cero. La clase que implementa el desplazable debe derivarse de `CComTearOffObjectBase` y tiene su propio mapa COM.  
  
  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN  
 Procesa el mapa COM de la clase base cuando el procesamiento alcanza esta entrada en el mapa COM.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Parámetros  
 *classname*  
 [in] Una clase base del objeto actual.  
  
### <a name="remarks"></a>Comentarios  
 Por ejemplo, en el código siguiente:  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 Tenga en cuenta que la primera entrada en el mapa COM debe ser una interfaz en el objeto que contiene la asignación COM. Por lo tanto, no se puede iniciar las entradas de mapa COM con `COM_INTERFACE_ENTRY_CHAIN`, lo que hace que la asignación de COM de un objeto diferente que se buscará en el punto donde **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** aparece en el mapa de COM del objeto. Si desea buscar el mapa COM de otro objeto en primer lugar, agregue una entrada de la interfaz para **IUnknown** al mapa COM, a continuación, encadenar mapa de COM del otro objeto. Por ejemplo:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC  
 Un mecanismo general para enlazar con de ATL `QueryInterface` lógica.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El GUID de la interfaz expuesta.  
  
 `dw`  
 [in] Pasa un parámetro a la `func`.  
  
 `func`  
 [in] El puntero a función devolverá `iid`.  
  
### <a name="remarks"></a>Comentarios  
 Si *iid* coincide con el IID de la interfaz de consulta para, a continuación, la función especificada por `func` se llama. La declaración de la función debe ser:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 Cuando se llama a la función, `pv` apunta a su objeto de clase. El `riid` parámetro hace referencia a la interfaz que se está consulta, `ppv` es el puntero a la ubicación donde la función debe almacenar el puntero a la interfaz, y `dw` es el parámetro especificado en la entrada. Debe establecer la función \* `ppv` a **NULL** y devolver **E_NOINTERFACE** o **S_FALSE** si elige no devuelven una interfaz. Con **E_NOINTERFACE**, procesamiento de asignación COM finaliza. Con **S_FALSE**, continúa el procesamiento de asignación COM, incluso si se ha devuelto ningún puntero de interfaz. Si la función devuelve un puntero de interfaz, debe devolver `S_OK`.  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND  
 Igual que [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), salvo que consultar los IID da como resultado una llamada a `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Parámetros  
 `dw`  
 [in] Pasa un parámetro a la `func`.  
  
 `func`  
 [in] La función que se llamará cuando se procesa esta entrada en el mapa COM.  
  
### <a name="remarks"></a>Comentarios  
 Cualquier error hará que el procesamiento continúe en el mapa COM. Si la función devuelve un puntero de interfaz, debe devolver `S_OK`.  
  
  
##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE  
 Devuelve **E_NOINTERFACE** y finaliza el procesamiento de asignación COM cuando se consulta la interfaz especificada para.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Parámetros  
 *x*  
 [in] Texto utilizado para construir el identificador de interfaz.  
  
### <a name="remarks"></a>Comentarios  
 Puede utilizar esta macro para impedir que una interfaz que se va a usar en un caso concreto. Por ejemplo, puede insertar esta macro en su COM justo antes de asignar `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` para impedir que una consulta para la interfaz se reenvían al desconocido interno del agregado.  
  
 La interfaz se construirá IID anexando *x* a `IID_`. Por ejemplo, si *x* es `IPersistStorage`, será el IID `IID_IPersistStorage`.  
  
  