---
title: Clase CAnimationController | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
dev_langs:
- C++
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ec93c2d39206bbc0c3076835f55e624d3eef715
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="canimationcontroller-class"></a>Clase CAnimationController
Implementa el controlador de animación, que proporciona una interfaz central para crear y administrar las animaciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CAnimationController : public CObject;  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](#canimationcontroller)|Crea un controlador de animación.|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|Destructor. Se llama cuando se está destruyendo el objeto de controlador de animación.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](#addanimationobject)|Agrega un objeto de animación a un grupo al que pertenece el controlador de animación.|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Agrega un fotograma clave al grupo.|  
|[CAnimationController::AnimateGroup](#animategroup)|Prepara un grupo para ejecutar la animación y lo programa si lo desea.|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Sobrecargado. Lo llama el marco para limpiar el grupo cuando se ha programado la animación.|  
|[CAnimationController::CreateKeyframe](#createkeyframe)|Sobrecargado. Crea un fotograma clave que depende de la transición y lo agrega al grupo especificado.|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Establece o libera un controlador al que llamar cuando cambia el estado del Administrador de animación.|  
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Establece o libera un controlador de eventos de sincronización y el controlador para las actualizaciones de control de tiempo.|  
|[Canimationcontroller:: Enableprioritycomparisonhandler](#enableprioritycomparisonhandler)|Establece o libera el controlador de comparación de prioridad para llamar para determinar si un guion gráfico programado puede cancelar, finalizado, recorta o comprimido.|  
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Establece o libera un controlador de eventos de estado y la actualización de guión gráfico.|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Sobrecargado. Busca un grupo de animación con su guión gráfico.|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|Busca el objeto de animación que contiene una variable de animación especificado.|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Devuelve un fotograma clave que identifica el inicio del guión gráfico.|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Proporciona acceso al objeto IUIAnimationManager encapsulado.|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Proporciona acceso al objeto IUIAnimationTimer encapsulado.|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|Un puntero a interfaz IUIAnimationTransitionFactory o NULL si no se pudo crear la biblioteca de transición.|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Proporciona acceso al objeto IUIAnimationTransitionLibrary encapsulado.|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|Indica si al menos un grupo reproduce la animación.|  
|[CAnimationController::IsValid](#isvalid)|Indica si el controlador de animación es válido.|  
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Lo llama el marco de trabajo cuando ha cambiado el valor del entero de animación.|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Lo llama el marco de trabajo en respuesta al evento StatusChanged del Administrador de animación.|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Lo llama el marco de trabajo una vez finalizada una actualización de la animación.|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Lo llama el marco de trabajo antes de que comience una actualización de la animación.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Lo llama el marco cuando la velocidad de fotogramas de representación para una animación cae por debajo de una velocidad de fotogramas deseable mínimo.|  
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|Lo llama el marco de trabajo cuando ha cambiado el valor de variable de animación.|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Lo llama el marco derecho antes de programa la animación.|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Lo llama el marco para resolver los conflictos de programación.|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Lo llama el marco para resolver los conflictos de programación.|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Lo llama el marco para resolver los conflictos de programación.|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Lo llama el marco para resolver los conflictos de programación.|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Lo llama el marco de trabajo cuando ha cambiado el estado de guión gráfico.|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Llamado por el marco de trabajo cuando se ha actualizado el guión gráfico.|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Quita todos los grupos de animación de controlador de animación.|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Quita un grupo de animación con el identificador especificado de controlador de animación.|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Quitar un objeto de animación de controlador de animación.|  
|[CAnimationController::RemoveTransitions](#removetransitions)|Quita las transiciones de los objetos de animación que pertenecen al grupo especificado.|  
|[CAnimationController::ScheduleGroup](#schedulegroup)|Programa una animación.|  
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Establece una relación entre el controlador de animación y una ventana.|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Hace que el Administrador de animación para actualizar los valores de todas las variables de la animación.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Sobrecargado. Una aplicación auxiliar que limpie el grupo.|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Lo llama el marco cuando solo se ha programado una animación para el grupo especificado.|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Un fotograma clave que representa el inicio del guión gráfico.|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|Especifica si un controlador de animación es válido o no. Este miembro se establece en FALSE si el sistema operativo actual no es compatible con la API de animación de Windows.|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Una lista de grupos de animación que pertenecen a este controlador de animación.|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Almacena un puntero al objeto COM del Administrador de animación.|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Almacena un puntero al objeto COM de temporizador de animación.|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Un puntero a un objeto relacionado de CWnd, que puede ser vuelve a dibujarse automáticamente cuando el estado de administrador de animación ha cambiado o se ha producido el evento posterior a la actualización. Puede ser NULL.|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Almacena un puntero al objeto COM de fábrica de transición.|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Almacena un puntero al objeto COM de la biblioteca de transición.|  
  
## <a name="remarks"></a>Comentarios  
 La clase CAnimationController es la clase de clave que administra las animaciones. Puede crear una o más instancias de controlador de animación en una aplicación y, opcionalmente, conectar una instancia de controlador de animación a un objeto CWnd mediante CAnimationController::SetRelatedWnd. Esta conexión es necesario enviar automáticamente mensajes WM_PAINT a la ventana relacionada cuando ha cambiado el estado del Administrador de animación o se ha actualizado el temporizador de animación. Si no habilita a esta relación, debe volver a dibujar una ventana que muestra una animación manualmente. Para ello puede derivar una clase de CAnimationController y reemplazo OnAnimationManagerStatusChanged y OnAnimationTimerPostUpdate e invalidar una o varias ventanas cuando sea necesario.  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationController`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationcontroller"></a>  CAnimationController:: ~ CAnimationController  
 Destructor. Se llama cuando se está destruyendo el objeto de controlador de animación.  
  
```  
virtual ~CAnimationController(void);
```   
  
##  <a name="addanimationobject"></a>  CAnimationController::AddAnimationObject  
 Agrega un objeto de animación a un grupo al que pertenece el controlador de animación.  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>Parámetros  
 `pObject`  
 Un puntero a un objeto de animación.  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero al grupo de animación nueva o existente que se ha agregado pObject si la función se realiza correctamente; Es NULL si pObject ya se ha agregado a un grupo al que pertenece a otro controlador de animación.  
  
### <a name="remarks"></a>Comentarios  
 Llamar a este método para agregar un objeto de animación para el controlador de animación. Un objeto se agregará a un grupo de acuerdo con el Id. de grupo del objeto (consulte CAnimationBaseObject::SetID). El controlador de animación creará un nuevo grupo si es el primer objeto que se agrega con el Id. de grupo especificado. Un objeto de animación puede agregarse al controlador de uno animación solo. Si necesita agregar un objeto a otro controlador, llame primero a RemoveAnimationObject. Si se llama a SetID con Id. de grupo nueva para un objeto que ya se ha agregado a un grupo, el objeto se quita del grupo anterior y se agrega a otro grupo con el identificador especificado.  
  
##  <a name="addkeyframetogroup"></a>  CAnimationController::AddKeyframeToGroup  
 Agrega un fotograma clave al grupo.  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo.  
  
 `pKeyframe`  
 Un puntero a un fotograma clave.  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si la función se realiza correctamente; en caso contrario, FALSE.  
  
### <a name="remarks"></a>Comentarios  
 Normalmente no es necesario llamar a este método, use CAnimationController::CreateKeyframe en su lugar, que crea y agrega el fotograma clave creado a un grupo automáticamente.  
  
##  <a name="animategroup"></a>  CAnimationController::AnimateGroup  
 Prepara un grupo para ejecutar la animación y lo programa si lo desea.  
  
```  
BOOL AnimateGroup(
    UINT32 nGroupID,  
    BOOL bScheduleNow = TRUE);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el Id. de grupo.  
  
 `bScheduleNow`  
 Especifica si se ejecuta inmediatamente la animación.  
  
### <a name="return-value"></a>Valor devuelto  
 Es TRUE si la animación se ha programado y ejecutar correctamente.  
  
### <a name="remarks"></a>Comentarios  
 Este método realiza el trabajo real crear guión gráfico, agregar variables de animación, aplicar las transiciones y establecimiento de fotogramas clave. Es posible retrasar la programación si establece bScheduleNow en FALSE. En este caso, el grupo especificado contendrá un guión gráfico que se ha configurado para la animación. En ese momento, puede configurar eventos para las variables de guión gráfico y animación. Cuando necesita realmente ejecutar la llamada de animación CAnimationController::ScheduleGroup.  
  
##  <a name="canimationcontroller"></a>  CAnimationController::CAnimationController  
 Crea un controlador de animación.  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>  CAnimationController::CleanUpGroup  
 Lo llama el marco para limpiar el grupo cuando se ha programado la animación.  
  
```  
void CleanUpGroup(UINT32 nGroupID);  
void CleanUpGroup(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el Id. de grupo.  
  
 `pGroup`  
 Un puntero al grupo de animación para limpiar.  
  
### <a name="remarks"></a>Comentarios  
 Este método quita todas las transiciones y los fotogramas clave del grupo especificado, ya que no son relevantes después de que se ha programado una animación.  
  
##  <a name="createkeyframe"></a>  CAnimationController::CreateKeyframe  
 Crea un fotograma clave que depende de la transición y lo agrega al grupo especificado.  
  
```  
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,  
    CBaseTransition* pTransition);

 
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo para el que se crea el fotograma clave.  
  
 `pTransition`  
 Puntero a la transición. El fotograma clave se insertará en el guion gráfico después de esta transición.  
  
 `pKeyframe`  
 Puntero al fotograma clave base de este fotograma clave.  
  
 `offset`  
 Desplazamiento en segundos desde el fotograma clave base especificado por pKeyframe.  
  
### <a name="return-value"></a>Valor devuelto  
 Puntero al fotograma clave recién creado si la función se ejecuta correctamente.  
  
### <a name="remarks"></a>Comentarios  
 Puede almacenar el puntero devuelto y basar otros fotogramas clave en el fotograma clave recién creado (véase la segunda sobrecarga). Es posible iniciar las transiciones en los fotogramas clave (véase CBaseTransition::SetKeyframes). No es necesario eliminar fotogramas clave creados de esta manera, ya que los grupos de animación los eliminan automáticamente. Tenga cuidado al crear fotogramas clave basados en otros fotogramas clave y transiciones, y evite las referencias circulares.  
  
##  <a name="enableanimationmanagerevent"></a>  CAnimationController::EnableAnimationManagerEvent  
 Establece o libera un controlador al que llamar cuando cambia el estado del Administrador de animación.  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parámetros  
 `bEnable`  
 Especifica si se debe establecer o liberar un controlador.  
  
### <a name="return-value"></a>Valor devuelto  
 Es TRUE si el controlador se ha establecido correctamente o se libera.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se configura un controlador (habilitado) animaciones de Windows llama a OnAnimationManagerStatusChanged cuando cambia el estado del Administrador de animación.  
  
##  <a name="enableanimationtimereventhandler"></a>  CAnimationController::EnableAnimationTimerEventHandler  
 Establece o libera un controlador de eventos de sincronización y el controlador para las actualizaciones de control de tiempo.  
  
```  
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,  
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```  
  
### <a name="parameters"></a>Parámetros  
 `bEnable`  
 Especifica si se debe establecer o liberar los controladores.  
  
 `idleBehavior`  
 Especifica el comportamiento inactivo para el controlador de actualización de temporizador.  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si los controladores correctamente se establece o liberarse; FALSE si este método se llama por segunda vez sin liberar primero los controladores, o si cualquier otro error.  
  
### <a name="remarks"></a>Comentarios  
 Cuando los controladores se establecen (habilitadas) llamadas de API de animación de Windows OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate, OnRenderingTooSlow métodos. Debe permitir que los temporizadores de animación permitir que los guiones gráficos de API de animación de Windows update. En caso contrario, debe llamar a CAnimationController::UpdateAnimationManager con el fin de dirigir la animación de administrador para actualizar los valores de todas las variables de la animación.  
  
##  <a name="enableprioritycomparisonhandler"></a>  Canimationcontroller:: Enableprioritycomparisonhandler  
 Establece o libera el controlador de comparación de prioridad para llamar para determinar si un guion gráfico programado puede cancelar, finalizado, recorta o comprimido.  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwHandlerType`  
 Una combinación de UI_ANIMATION_PHT_ marcas (vea la sección Comentarios), que especifica qué controladores establecer o liberar.  
  
### <a name="return-value"></a>Valor devuelto  
 Es TRUE si el controlador se ha establecido correctamente o se libera.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se configura un controlador (habilitado) animaciones de Windows llama a los métodos virtuales siguientes según dwHandlerType: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler puede ser una combinación de los siguientes indicadores: UI_ANIMATION_PHT_NONE - versión todos los controladores de UI_ANIMATION_PHT_CANCEL - establece Cancel controlador comparación UI_ANIMATION_PHT_CONCLUDE - establecer el controlador de comparación de concluir UI_ANIMATION_PHT_COMPRESS Controlador de comparación de comprimir UI_ANIMATION_PHT_TRIM - establecer el controlador de recorte comparación UI_ANIMATION_PHT_CANCEL_REMOVE - quitar el controlador de comparación de cancelación UI_ANIMATION_PHT_CONCLUDE_REMOVE - quitar el controlador de comparación de concluir UI_ANIMATION_PHT_COMPRESS_ QUITAR: quitar el controlador de comparación de comprimir UI_ANIMATION_PHT_TRIM_REMOVE - controlador de recorte comparación remove  
  
##  <a name="enablestoryboardeventhandler"></a>  CAnimationController::EnableStoryboardEventHandler  
 Establece o libera un controlador de eventos de estado y la actualización de guión gráfico.  
  
```  
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo.  
  
 `bEnable`  
 Especifica si se debe establecer o liberar un controlador.  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si el controlador se ha establecido correctamente o se libera; FALSE si ahora se encuentra el grupo de animación especificado o no se inició la animación para el grupo especificado y el guión gráfico interno es NULL.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se configura un controlador de API de animación de Windows (habilitado) llama a métodos virtuales OnStoryboardStatusChanges y OnStoryboardUpdated. Un controlador debe establecerse después de haber llamado CAnimationController::Animate para el grupo de animación especificado, ya que crea el objeto IUIAnimationStoryboard encapsulado.  
  
##  <a name="findanimationgroup"></a>  CAnimationController::FindAnimationGroup  
 Busca un grupo de animación con su identificador de grupo.  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica un Id. de grupo.  
  
 `pStoryboard`  
 Un puntero a un guión gráfico.  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero al grupo de animación o NULL si no se encuentra el grupo con el identificador especificado.  
  
### <a name="remarks"></a>Comentarios  
 Utilice este método para buscar un grupo de animación en tiempo de ejecución. Un grupo se crea y se agrega a la lista interna de grupos de animación cuando se agrega un objeto de animación primer con GroupID determinado a controlador de animación.  
  
##  <a name="findanimationobject"></a>  CAnimationController::FindAnimationObject  
 Busca el objeto de animación que contiene una variable de animación especificado.  
  
```  
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,  
    CAnimationBaseObject** ppObject,  
    CAnimationGroup** ppGroup);
```  
  
### <a name="parameters"></a>Parámetros  
 `pVariable`  
 Un puntero a la variable de animación.  
  
 `ppObject`  
 Salida. Contiene un puntero al objeto de animación o NULL.  
  
 `ppGroup`  
 Salida. Contiene un puntero al grupo de animación que contiene el objeto de animación, o NULL.  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si se encontró el objeto; en caso contrario, FALSE.  
  
### <a name="remarks"></a>Comentarios  
 Se llama desde controladores de eventos cuando lo necesario para buscar un objeto de animación de entrada variable de animación.  
  
##  <a name="g_keyframestoryboardstart"></a>  CAnimationController::gkeyframeStoryboardStart  
 Un fotograma clave que representa el inicio del guión gráfico.  
  
```  
static CBaseKeyFrame gkeyframeStoryboardStart;  
```  
  
##  <a name="getkeyframestoryboardstart"></a>  CAnimationController::GetKeyframeStoryboardStart  
 Devuelve un fotograma clave que identifica el inicio del guión gráfico.  
  
```  
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero al fotograma clave base, que identifica el inicio del guión gráfico.  
  
### <a name="remarks"></a>Comentarios  
 Obtener este fotograma clave para basar otros fotogramas clave o transiciones en el momento en el tiempo cuando se inicia un guión gráfico.  
  
##  <a name="getuianimationmanager"></a>  CAnimationController::GetUIAnimationManager  
 Proporciona acceso al objeto IUIAnimationManager encapsulado.  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a interfaz IUIAnimationManager o NULL si no se pudo crear el Administrador de animación.  
  
### <a name="remarks"></a>Comentarios  
 Si el sistema operativo actual no es compatible con la API de animación de Windows, este método devuelve NULL y después de que todas las llamadas subsiguientes en CAnimationController::IsValid devuelven FALSE. Debe tener acceso a IUIAnimationManager para poder llamar a sus métodos de interfaz, que no están encapsuladas por controlador de animación.  
  
##  <a name="getuianimationtimer"></a>  CAnimationController::GetUIAnimationTimer  
 Proporciona acceso al objeto IUIAnimationTimer encapsulado.  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a interfaz IUIAnimationTimer o NULL si no se pudo crear el temporizador de animación.  
  
### <a name="remarks"></a>Comentarios  
 Si el sistema operativo actual no es compatible con la API de animación de Windows, este método devuelve NULL y después de que todas las llamadas subsiguientes en CAnimationController::IsValid devuelven FALSE.  
  
##  <a name="getuitransitionfactory"></a>  CAnimationController::GetUITransitionFactory  
 Un puntero a interfaz IUIAnimationTransitionFactory o NULL si no se pudo crear la biblioteca de transición.  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a IUIAnimationTransitionFactory o NULL si no se pudo crear el generador de transición.  
  
### <a name="remarks"></a>Comentarios  
 Si el sistema operativo actual no es compatible con la API de animación de Windows, este método devuelve NULL y después de que todas las llamadas subsiguientes en CAnimationController::IsValid devuelven FALSE.  
  
##  <a name="getuitransitionlibrary"></a>  CAnimationController::GetUITransitionLibrary  
 Proporciona acceso al objeto IUIAnimationTransitionLibrary encapsulado.  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a interfaz IUIAnimationTransitionLibrary o NULL si no se pudo crear la biblioteca de transición.  
  
### <a name="remarks"></a>Comentarios  
 Si el sistema operativo actual no es compatible con la API de animación de Windows, este método devuelve NULL y después de que todas las llamadas subsiguientes en CAnimationController::IsValid devuelven FALSE.  
  
##  <a name="isanimationinprogress"></a>  CAnimationController::IsAnimationInProgress  
 Indica si al menos un grupo reproduce la animación.  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si hay una animación en curso para este controlador de animación en caso contrario, FALSE.  
  
### <a name="remarks"></a>Comentarios  
 Comprueba el estado de administrador de animación y devuelve TRUE si el estado es UI_ANIMATION_MANAGER_BUSY.  
  
##  <a name="isvalid"></a>  CAnimationController::IsValid  
 Indica si el controlador de animación es válido.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si el controlador de animación es válida; en caso contrario, FALSE.  
  
### <a name="remarks"></a>Comentarios  
 Este método devuelve FALSE solo si la API de animación de Windows no es compatible con la creación de administrador de animación y el sistema operativo actual no se pudo porque no está registrado. Debe llamar a GetUIAnimationManager al menos una vez después de la inicialización de las bibliotecas COM para hacer que la configuración de esta marca.  
  
##  <a name="m_bisvalid"></a>  CAnimationController::m_bIsValid  
 Especifica si un controlador de animación es válido o no. Este miembro se establece en FALSE si el sistema operativo actual no es compatible con la API de animación de Windows.  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>  CAnimationController::m_lstAnimationGroups  
 Una lista de grupos de animación que pertenecen a este controlador de animación.  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>  CAnimationController::m_pAnimationManager  
 Almacena un puntero al objeto COM del Administrador de animación.  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>  CAnimationController::m_pAnimationTimer  
 Almacena un puntero al objeto COM de temporizador de animación.  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>  CAnimationController::m_pRelatedWnd  
 Un puntero a un objeto relacionado de CWnd, que puede ser vuelve a dibujarse automáticamente cuando el estado de administrador de animación ha cambiado o se ha producido el evento posterior a la actualización. Puede ser NULL.  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>  CAnimationController::m_pTransitionFactory  
 Almacena un puntero al objeto COM de fábrica de transición.  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>  CAnimationController::m_pTransitionLibrary  
 Almacena un puntero al objeto COM de la biblioteca de transición.  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>  CAnimationController::OnAfterSchedule  
 Lo llama el marco cuando solo se ha programado una animación para el grupo especificado.  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroup`  
 Un puntero a un grupo de animación, que se ha programado.  
  
### <a name="remarks"></a>Comentarios  
 La implementación predeterminada quita los fotogramas clave del grupo especificado y realiza la transición de las variables de animación que pertenecen al grupo especificado. Puede invalidarse en una clase derivada para realizar cualquier acción adicional en la programación de la animación.  
  
##  <a name="onanimationintegervaluechanged"></a>  CAnimationController::OnAnimationIntegerValueChanged  
 Lo llama el marco de trabajo cuando ha cambiado el valor del entero de animación.  
  
```  
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    INT32 newValue,  
    INT32 prevValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroup`  
 Un puntero a un grupo de animación que contiene un objeto de animación cuyo valor ha cambiado.  
  
 `pObject`  
 Un puntero a un objeto de animación que contiene una variable de animación cuyo valor ha cambiado.  
  
 `variable`  
 Un puntero a una variable de animación.  
  
 `newValue`  
 Especifica el nuevo valor.  
  
 `prevValue`  
 Especifica el valor anterior.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si habilita los eventos de variable de animación con EnableIntegerValueChangedEvent llamado a una variable de animación específico o un objeto de animación. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación.  
  
##  <a name="onanimationmanagerstatuschanged"></a>  CAnimationController::OnAnimationManagerStatusChanged  
 Lo llama el marco de trabajo en respuesta al evento StatusChanged del Administrador de animación.  
  
```  
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,  
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parámetros  
 `newStatus`  
 Nuevo estado de administrador de animación.  
  
 `previousStatus`  
 Estado anterior del Administrador de animación.  
  
### <a name="remarks"></a>Comentarios  
 Si habilita los eventos del Administrador de animación con EnableAnimationManagerEvent llama a este método. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación. La implementación predeterminada actualiza una ventana relacionada si se ha establecido con SetRelatedWnd.  
  
##  <a name="onanimationtimerpostupdate"></a>  CAnimationController::OnAnimationTimerPostUpdate  
 Lo llama el marco de trabajo una vez finalizada una actualización de la animación.  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>Comentarios  
 Si habilita a los controladores de eventos de temporizador mediante EnableAnimationTimerEventHandler llama a este método. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación.  
  
##  <a name="onanimationtimerpreupdate"></a>  CAnimationController::OnAnimationTimerPreUpdate  
 Lo llama el marco de trabajo antes de que comience una actualización de la animación.  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>Comentarios  
 Si habilita a los controladores de eventos de temporizador mediante EnableAnimationTimerEventHandler llama a este método. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación.  
  
##  <a name="onanimationtimerrenderingtooslow"></a>  CAnimationController::OnAnimationTimerRenderingTooSlow  
 Lo llama el marco cuando la velocidad de fotogramas de representación para una animación cae por debajo de una velocidad de fotogramas deseable mínimo.  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>Parámetros  
 `fps`  
 La velocidad de fotogramas actual en fotogramas por segundo.  
  
### <a name="remarks"></a>Comentarios  
 Si habilita a los controladores de eventos de temporizador mediante EnableAnimationTimerEventHandler llama a este método. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación. La velocidad de fotogramas deseable mínimo se especifica mediante una llamada a IUIAnimationTimer::SetFrameRateThreshold.  
  
##  <a name="onanimationvaluechanged"></a>  CAnimationController::OnAnimationValueChanged  
 Lo llama el marco de trabajo cuando ha cambiado el valor de variable de animación.  
  
```  
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    DOUBLE newValue,  
    DOUBLE prevValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroup`  
 Un puntero a un grupo de animación que contiene un objeto de animación cuyo valor ha cambiado.  
  
 `pObject`  
 Un puntero a un objeto de animación que contiene una variable de animación cuyo valor ha cambiado.  
  
 `variable`  
 Un puntero a una variable de animación.  
  
 `newValue`  
 Especifica el nuevo valor.  
  
 `prevValue`  
 Especifica el valor anterior.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si habilita los eventos de variable de animación con EnableValueChangedEvent llamado a una variable de animación específico o un objeto de animación. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación.  
  
##  <a name="onbeforeanimationstart"></a>  CAnimationController::OnBeforeAnimationStart  
 Lo llama el marco derecho antes de programa la animación.  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroup`  
 Un puntero a un grupo de animación cuya animación está a punto de iniciarse.  
  
### <a name="remarks"></a>Comentarios  
 Esta llamada se enruta a CWnd relacionado y puede invalidarse en una clase derivada para realizar acciones adicionales antes de que comience la animación para el grupo especificado.  
  
##  <a name="onhasprioritycancel"></a>  CAnimationController::OnHasPriorityCancel  
 Lo llama el marco para resolver los conflictos de programación.  
  
```  
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroupScheduled`  
 El grupo que posee el guion gráfico actualmente programado.  
  
 `pGroupNew`  
 El grupo que posee el nuevo guion gráfico que está en conflicto de programación con el guion gráfico programado que pertenece a pGroupScheduled.  
  
 `priorityEffect`  
 Efecto potencial en pGroupNew si pGroupScheduled tiene una prioridad más alta.  
  
### <a name="return-value"></a>Valor devuelto  
 Debe devolver TRUE si el guion gráfico propiedad de pGroupNew tiene prioridad. Debe devolver FALSE si el guion gráfico propiedad de pGroupNew tiene prioridad.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si se habilitan eventos de comparación de prioridad mediante CAnimationController::EnablePriorityComparisonHandler y se especifica UI_ANIMATION_PHT_CANCEL. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación. Documentación de API de animación de Windows de lectura para obtener más información acerca de la administración de conflictos (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritycompress"></a>  CAnimationController::OnHasPriorityCompress  
 Lo llama el marco para resolver los conflictos de programación.  
  
```  
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroupScheduled`  
 El grupo que posee el guion gráfico actualmente programado.  
  
 `pGroupNew`  
 El grupo que posee el nuevo guion gráfico que está en conflicto de programación con el guion gráfico programado que pertenece a pGroupScheduled.  
  
 `priorityEffect`  
 Efecto potencial en pGroupNew si pGroupScheduled tiene una prioridad más alta.  
  
### <a name="return-value"></a>Valor devuelto  
 Debe devolver TRUE si el guion gráfico propiedad de pGroupNew tiene prioridad. Debe devolver FALSE si el guion gráfico propiedad de pGroupNew tiene prioridad.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si se habilitan eventos de comparación de prioridad mediante CAnimationController::EnablePriorityComparisonHandler y se especifica UI_ANIMATION_PHT_COMPRESS. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación. Documentación de API de animación de Windows de lectura para obtener más información acerca de la administración de conflictos (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhaspriorityconclude"></a>  CAnimationController::OnHasPriorityConclude  
 Lo llama el marco para resolver los conflictos de programación.  
  
```  
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroupScheduled`  
 El grupo que posee el guion gráfico actualmente programado.  
  
 `pGroupNew`  
 El grupo que posee el nuevo guion gráfico que está en conflicto de programación con el guion gráfico programado que pertenece a pGroupScheduled.  
  
 `priorityEffect`  
 Efecto potencial en pGroupNew si pGroupScheduled tiene una prioridad más alta.  
  
### <a name="return-value"></a>Valor devuelto  
 Debe devolver TRUE si el guion gráfico propiedad de pGroupNew tiene prioridad. Debe devolver FALSE si el guion gráfico propiedad de pGroupNew tiene prioridad.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si se habilitan eventos de comparación de prioridad mediante CAnimationController::EnablePriorityComparisonHandler y se especifica UI_ANIMATION_PHT_CONCLUDE. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación. Documentación de API de animación de Windows de lectura para obtener más información acerca de la administración de conflictos (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritytrim"></a>  CAnimationController::OnHasPriorityTrim  
 Lo llama el marco para resolver los conflictos de programación.  
  
```  
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroupScheduled`  
 El grupo que posee el guion gráfico actualmente programado.  
  
 `pGroupNew`  
 El grupo que posee el nuevo guion gráfico que está en conflicto de programación con el guion gráfico programado que pertenece a pGroupScheduled.  
  
 `priorityEffect`  
 Efecto potencial en pGroupNew si pGroupScheduled tiene una prioridad más alta.  
  
### <a name="return-value"></a>Valor devuelto  
 Debe devolver TRUE si el guion gráfico propiedad de pGroupNew tiene prioridad. Debe devolver FALSE si el guion gráfico propiedad de pGroupNew tiene prioridad.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si se habilitan eventos de comparación de prioridad mediante CAnimationController::EnablePriorityComparisonHandler y se especifica UI_ANIMATION_PHT_TRIM. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación. Documentación de API de animación de Windows de lectura para obtener más información acerca de la administración de conflictos (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationController::OnStoryboardStatusChanged  
 Lo llama el marco de trabajo cuando ha cambiado el estado de guión gráfico.  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroup`  
 Un puntero a un grupo de animación que posee el guión gráfico cuyo estado ha cambiado.  
  
 `newStatus`  
 Especifica el nuevo estado.  
  
 `previousStatus`  
 Especifica el estado anterior.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si se habilitan eventos de guión gráfico mediante CAnimationController::EnableStoryboardEventHandler. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación.  
  
##  <a name="onstoryboardupdated"></a>  CAnimationController::OnStoryboardUpdated  
 Llamado por el marco de trabajo cuando se ha actualizado el guión gráfico.  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parámetros  
 `pGroup`  
 Un puntero a un grupo que posee el guión gráfico.  
  
### <a name="remarks"></a>Comentarios  
 Se llama a este método si se habilitan eventos de guión gráfico mediante CAnimationController::EnableStoryboardEventHandler. Se puede invalidar en una clase derivada para realizar acciones específicas de la aplicación.  
  
##  <a name="removeallanimationgroups"></a>  CAnimationController::RemoveAllAnimationGroups  
 Quita todos los grupos de animación de controlador de animación.  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>Comentarios  
 Todos los grupos será eliminado, el puntero, si se almacenan en el nivel de aplicación, debe invalidarse. Si CAnimationGroup::m_bAutodestroyAnimationObjects para un grupo que se va a eliminar es TRUE, se eliminarán todos los objetos de animación que pertenecen a ese grupo; de lo contrario, sus referencias al controlador de animación primario se establecerá en NULL y se pueden agregar a otro controlador.  
  
##  <a name="removeanimationgroup"></a>  CAnimationController::RemoveAnimationGroup  
 Quita un grupo de animación con el identificador especificado de controlador de animación.  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo de animación.  
  
### <a name="remarks"></a>Comentarios  
 Este método quita de la lista interna de los grupos de un grupo de animación y lo elimina, por lo tanto, si almacena un puntero a ese grupo de animación, debe invalidarse. Si CAnimationGroup::m_bAutodestroyAnimationObjects es TRUE, se eliminarán todos los objetos de animación que pertenecen a ese grupo; de lo contrario, sus referencias al controlador de animación primario se establecerá en NULL y se pueden agregar a otro controlador.  
  
##  <a name="removeanimationobject"></a>  CAnimationController::RemoveAnimationObject  
 Quitar un objeto de animación de controlador de animación.  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>Parámetros  
 `pObject`  
 Un puntero a un objeto de animación.  
  
 `bNoDelete`  
 Si este parámetro es TRUE el objeto no se eliminará tras quitar.  
  
### <a name="remarks"></a>Comentarios  
 Quita un objeto de animación de controlador de animación y el grupo de animación. Llame a esta función si un objeto determinado no se debe animar ya, o si tiene que mover el objeto a otro controlador de animación. En el último caso bNoDelete debe ser TRUE.  
  
##  <a name="removetransitions"></a>  CAnimationController::RemoveTransitions  
 Quita las transiciones de los objetos de animación que pertenecen al grupo especificado.  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo.  
  
### <a name="remarks"></a>Comentarios  
 El grupo recorre sus objetos de animación y llama a ClearTransitions(FALSE) para cada objeto de animación. El marco de trabajo llama a este método después de que se ha programado la animación.  
  
##  <a name="schedulegroup"></a>  CAnimationController::ScheduleGroup  
 Programa una animación.  
  
```  
BOOL ScheduleGroup(
    UINT32 nGroupID,  
    UI_ANIMATION_SECONDS time = 0.0);
```  
  
### <a name="parameters"></a>Parámetros  
 `nGroupID`  
 Especifica el identificador de grupo para programar la animación.  
  
 `time`  
 Especifica el momento de programar.  
  
### <a name="return-value"></a>Valor devuelto  
 Es TRUE si la animación se programó correctamente. FALSE si no se creó el guión gráfico o se produce otro error.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a AnimateGroup con bScheduleNow parámetro establecido en FALSE ScheduleGroup anterior. Puede especificar el tiempo de animación deseado obtenido de IUIAnimationTimer::GetTime. Si el parámetro de tiempo es 0,0, la animación está programada para la hora actual.  
  
##  <a name="setrelatedwnd"></a>  CAnimationController::SetRelatedWnd  
 Establece una relación entre el controlador de animación y una ventana.  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parámetros  
 `pWnd`  
 Un puntero al objeto de ventana para establecer.  
  
### <a name="remarks"></a>Comentarios  
 Si se establece un objeto relacionado de CWnd, el controlador de animación automáticamente puede actualizar (Enviar mensaje WM_PAINT) cuando ha cambiado el estado de administrador de animación o se ha producido el evento de temporizador posterior actualización.  
  
##  <a name="updateanimationmanager"></a>  CAnimationController::UpdateAnimationManager  
 Hace que el Administrador de animación para actualizar los valores de todas las variables de la animación.  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>Comentarios  
 Llamar a que este método avanza el Administrador de animación a la hora actual, cambiar los Estados de guiones gráficos según sea necesario y actualizar las variables de animación a correspondiente interpolan valores. Este método llama internamente IUIAnimationTimer::GetTime(timeNow) y IUIAnimationManager::Update(timeNow). Invalide este método en una clase derivada para personalizar este comportamiento.  
  
## <a name="see-also"></a>Vea también  
 [Clases](../../mfc/reference/mfc-classes.md)
