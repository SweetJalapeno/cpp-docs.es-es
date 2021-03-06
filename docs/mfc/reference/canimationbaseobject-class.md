---
title: Clase CAnimationBaseObject | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db9f7a66b60d70231628ded5dc096bad702bf088
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="canimationbaseobject-class"></a>Clase CAnimationBaseObject
La clase base para todos los objetos de animación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Sobrecargado. Construye un objeto de animación.|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|Destructor. Se llama cuando se destruye un objeto de animación.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Agrega las transiciones para guión gráfico con la variable de animación encapsulado.|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Quita todas las transiciones relacionadas.|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Determina si un objeto de animación contiene una variable de animación determinado.|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Crea las transiciones asociados con un objeto de animación.|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Desasocia un objeto de animación de controlador de animación del elemento primario.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Establece el controlador de eventos cambia de valor entero.|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Establece el valor cambiado el controlador de eventos.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Indica si la transición relacionado se destruyen automáticamente.|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Devuelve el identificador del grupo actual.|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Devuelve el identificador del objeto actual.|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|Devuelve los datos definidos por el usuario.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Establece una marca que están ordenadas para destruir automáticamente las transiciones.|  
|[CAnimationBaseObject::SetID](#setid)|Establece nuevos identificadores.|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|Datos de los conjuntos definidos por el usuario.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|Recopila los punteros a variables de animación independiente.|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Establece la relación entre las variables de animación, incluidos en un objeto de animación y su contenedor.|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Especifica si las transiciones relacionadas deben se destruyen automáticamente.|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Almacena los datos definidos por el usuario.|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Especifica el identificador de grupo del objeto de animación.|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Especifica el identificador de objeto del objeto de animación.|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Un puntero en el controlador de animación principal.|  
  
## <a name="remarks"></a>Comentarios  
 Esta clase implementa los métodos básicos para todos los objetos de animación. Un objeto de animación puede representar un valor, el punto, el tamaño, el rectángulo o el color en una aplicación, así como cualquier entidad personalizada. Objetos de animación se almacenan en grupos de animación (consulte CAnimationGroup). Cada grupo se puede animar por separado y se puede tratar como analógicos de guión gráfico. Un objeto de animación encapsula una o más animación variables (vea CAnimationVariable), dependiendo de su representación lógica. Por ejemplo, CAnimationRect contiene cuatro variables de animación: una variable para cada lado del rectángulo. Cada clase de objeto de animación expone AddTransition método sobrecargado, la que se debe usar para las transiciones se aplican a las variables de animación encapsulado. Un objeto de animación se puede identificar por Id. de objeto (opcionalmente) y por identificador de grupo. Un identificador de grupo es necesario para colocar un objeto de animación al grupo correcto, pero si no se especifica un identificador de grupo, un objeto se coloca en el grupo predeterminado con el Id. 0. Si se llama a SetID con diferentes Id. de grupo, un objeto de animación se moverán a otro grupo (se crea un nuevo grupo si es necesario).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>  CAnimationBaseObject:: ~ CAnimationBaseObject  
 Destructor. Se llama cuando se destruye un objeto de animación.  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>  CAnimationBaseObject::ApplyTransitions  
 Agrega las transiciones para guión gráfico con la variable de animación encapsulado.  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parámetros  
 `pStoryboard`  
 Un puntero a un guión gráfico.  
  
 `bDependOnKeyframes`  
 Con FALSE este método agrega solo las transiciones que no dependen de los fotogramas clave.  
  
### <a name="return-value"></a>Valor devuelto  
 Es TRUE si las transiciones se agregaron correctamente.  
  
### <a name="remarks"></a>Comentarios  
 Agrega transiciones relacionadas, que se han agregado con AddTransition (métodos sobrecargados en clases derivadas), en guiones gráficos.  
  
##  <a name="canimationbaseobject"></a>  CAnimationBaseObject::CAnimationBaseObject  
 Construye un objeto de animación.  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo.  
  
 `nObjectID`  
 Especifica el identificador de objeto.  
  
 `dwUserData`  
 Datos definidos por el usuario, que se pueden asociados con el objeto de animación y recuperarse más adelante en tiempo de ejecución.  
  
### <a name="remarks"></a>Comentarios  
 Construye un objeto de animación y asigna Id. de objeto predeterminado (0) y un Id. de grupo (0).  
  
##  <a name="cleartransitions"></a>  CAnimationBaseObject::ClearTransitions  
 Quita todas las transiciones relacionadas.  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parámetros  
 `bAutodestroy`  
 Especifica si se debe destruir objetos de transición automáticamente, o solo los quita de la lista relacionada.  
  
### <a name="remarks"></a>Comentarios  
 Quita todos ellos relacionados con las transiciones y destruyendo si marca bAutodestroy o m_bAutodestroyTransitions es TRUE. Las transiciones se deben destruir automáticamente solo si no se asignan en la pila. Si las marcas anteriores son FALSE, las transiciones sólo se quitan de la lista interna de transiciones relacionadas.  
  
##  <a name="containsvariable"></a>  CAnimationBaseObject::ContainsVariable  
 Determina si un objeto de animación contiene una variable de animación determinado.  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parámetros  
 `pVariable`  
 Un puntero a la variable de animación.  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si la variable de animación se encuentra en el objeto de animación; en caso contrario, FALSE.  
  
### <a name="remarks"></a>Comentarios  
 Este método puede utilizarse para determinar si una variable de animación especificada por pVariable está dentro de un objeto de animación. Un objeto de animación, dependiendo de su tipo, puede contener varias variables de animación. Por ejemplo, CAnimationColor contiene tres variables, uno para cada componente de color (rojo, verde y azul). Cuando ha cambiado un valor de variable de animación, la API de animación de Windows envía eventos ValueChanged o IntegerValueChanged (si está habilitado) y el parámetro de este evento es un puntero a interfaz IUIAnimationVariable de variable de animación. Este método ayuda a obtener un puntero a la animación de un puntero al objeto COM independiente.  
  
##  <a name="createtransitions"></a>  CAnimationBaseObject::CreateTransitions  
 Crea las transiciones asociados con un objeto de animación.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si las transiciones se crean correctamente; en caso contrario, FALSE.  
  
### <a name="remarks"></a>Comentarios  
 Recorre la lista de variables de animación encapsulada en un objeto de animación derivada y crea las transiciones asociados con cada variable de animación.  
  
##  <a name="detachfromcontroller"></a>  CAnimationBaseObject::DetachFromController  
 Desasocia un objeto de animación de controlador de animación del elemento primario.  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>Comentarios  
 Este método se usa internamente.  
  
##  <a name="enableintegervaluechangedevent"></a>  CAnimationBaseObject::EnableIntegerValueChangedEvent  
 Establece el controlador de eventos cambia de valor entero.  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parámetros  
 `pController`  
 Un puntero a un controlador principal.  
  
 `bEnable`  
 Especifica si se debe habilitar o deshabilitar eventos de cambio de valor de entero.  
  
### <a name="remarks"></a>Comentarios  
 Si está habilitado el controlador de eventos cambia de valor entero, puede controlar este evento en el método CAnimationController::OnAnimationIntegerValueChanged, que se debe invalidar en una clase derivada de CAnimationController. Este método se llama cada vez que ha cambiado el valor del entero de animación.  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationBaseObject::EnableValueChangedEvent  
 Establece el valor cambiado el controlador de eventos.  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parámetros  
 `pController`  
 Un puntero a un controlador principal.  
  
 `bEnable`  
 Especifica si se debe habilitar o deshabilitar eventos de cambio de valor.  
  
### <a name="remarks"></a>Comentarios  
 Si está habilitado el controlador de eventos cambia de valor, puede controlar este evento en el método CAnimationController::OnAnimationValueChanged, que se debe invalidar en una clase derivada de CAnimationController. Este método se llama cada vez que ha cambiado el valor de la animación.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationBaseObject::GetAnimationVariableList  
 Recopila los punteros a variables de animación independiente.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>Parámetros  
 `lst`  
 Una lista que se debe rellenar con variables de animación contenidas en un objeto de animación.  
  
### <a name="remarks"></a>Comentarios  
 Se trata de un método virtual puro que se debe invalidar en una clase derivada. Un objeto de animación, dependiendo de su tipo, contiene una o más variables de animación. Por ejemplo, CAnimationPoint contiene dos variables de coordenadas X e Y respectivamente. La clase base CAnimationBaseObject implementa algunos métodos genéricos, que actúan en una lista de variables de animación: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Estos métodos llamar a GetAnimationVariableList, que se rellena en una clase derivada con variables de animación real contenidas en un objeto de animación determinado, a continuación, recorrer la lista y emprenda las acciones necesarias. Si crea un objeto de animación personalizado, debe agregar a lst todas las variables de animación contenidas en ese objeto.  
  
##  <a name="getautodestroytransitions"></a>  CAnimationBaseObject::GetAutodestroyTransitions  
 Indica si la transición relacionado se destruyen automáticamente.  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es TRUE, las transiciones relacionadas se destruyen automáticamente; Si es FALSE, los objetos de transición deben desasignarse mediante una llamada a la aplicación.  
  
### <a name="remarks"></a>Comentarios  
 De forma predeterminada, esta marca es TRUE. Establezca esta marca únicamente si ha asignado la transición en la pila o transiciones deben desasignarse por la aplicación que realiza la llamada.  
  
##  <a name="getgroupid"></a>  CAnimationBaseObject::GetGroupID  
 Devuelve el identificador del grupo actual.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Identificador de grupo actual.  
  
### <a name="remarks"></a>Comentarios  
 Utilice este método para recuperar el identificador de grupo. 'S 0 si el Id. de grupo no se estableció explícitamente en el constructor o con SetID.  
  
##  <a name="getobjectid"></a>  CAnimationBaseObject::GetObjectID  
 Devuelve el identificador del objeto actual.  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Identificador del objeto actual.  
  
### <a name="remarks"></a>Comentarios  
 Utilice este método para recuperar el identificador de objeto. 'S 0 si el Id. de objeto no se estableció explícitamente en el constructor o con SetID.  
  
##  <a name="getuserdata"></a>  CAnimationBaseObject::GetUserData  
 Devuelve los datos definidos por el usuario.  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor de datos personalizados.  
  
### <a name="remarks"></a>Comentarios  
 Llamar a este método para recuperar los datos personalizados en tiempo de ejecución. El valor devuelto será 0 si no se inicializó explícitamente en el constructor o con SetUserData.  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationBaseObject::m_bAutodestroyTransitions  
 Especifica si las transiciones relacionadas deben se destruyen automáticamente.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>  CAnimationBaseObject::m_dwUserData  
 Almacena los datos definidos por el usuario.  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>  CAnimationBaseObject::m_nGroupID  
 Especifica el identificador de grupo del objeto de animación.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>  CAnimationBaseObject::m_nObjectID  
 Especifica el identificador de objeto del objeto de animación.  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>  CAnimationBaseObject::m_pParentController  
 Un puntero en el controlador de animación principal.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>  CAnimationBaseObject::SetAutodestroyTransitions  
 Establece una marca que están ordenadas para destruir automáticamente las transiciones.  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bValue`  
 Especifica el auto destruir marca.  
  
### <a name="remarks"></a>Comentarios  
 Establezca esta marca únicamente si ha asignado los objetos de transición con nuevo operador. Si por algún motivo se asignan los objetos de transición en la pila, destruir automáticamente marca debe ser FALSE. De forma predeterminada, esta marca es TRUE.  
  
##  <a name="setid"></a>  CAnimationBaseObject::SetID  
 Establece nuevos identificadores.  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>Parámetros  
 `nObjectID`  
 Especifica el identificador de objeto nuevo.  
  
 `nGroupID`  
 Especifica el nuevo identificador de grupo.  
  
### <a name="remarks"></a>Comentarios  
 Permite cambiar el identificador de objeto y el identificador de grupo. Si el nuevo identificador de grupo es diferente del identificador de la actual, un objeto de animación se mueve a otro grupo (un nuevo grupo se creará, si es necesario).  
  
##  <a name="setparentanimationobjects"></a>  CAnimationBaseObject::SetParentAnimationObjects  
 Establece la relación entre las variables de animación, incluidos en un objeto de animación y su contenedor.  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>Comentarios  
 Se trata de una aplicación auxiliar que puede usarse para establecer la relación entre las variables de animación, incluidos en un objeto de animación y su contenedor. Ejecuta un bucle sobre las variables de animación y establece un puntero a un objeto de animación de principal a cada variable de animación. En la implementación actual de que la relación real se establece en CAnimationBaseObject::ApplyTransitions, por lo tanto, espera punteros no se establecen hasta que llame a CAnimationGroup::Animate. Conocer la relación puede ser útil cuando, procesamiento de eventos y la necesidad de obtener una animación principal objeto de CAnimationVariable (use CAnimationVariable::GetParentAnimationObject).  
  
##  <a name="setuserdata"></a>  CAnimationBaseObject::SetUserData  
 Datos de los conjuntos definidos por el usuario.  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwUserData`  
 Especifica los datos personalizados.  
  
### <a name="remarks"></a>Comentarios  
 Utilice este método para asociar un datos personalizados a un objeto de animación. Estos datos se pueden recuperar más adelante en tiempo de ejecución por GetUserData.  
  
## <a name="see-also"></a>Vea también  
 [Clases](../../mfc/reference/mfc-classes.md)
