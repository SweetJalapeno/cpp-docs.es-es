---
title: Event (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb02865b20d1603be38192e770eb26627e6900e7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="event-class"></a>event (Clase)
Un evento de reinicio manual que es explícitamente consciente del runtime de simultaneidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class event;
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[~ event (destructor)](#dtor)|Destruye un evento.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[reset](#reset)|Restablece el evento a un estado no señalado.|  
|[set](#set)|Señala el evento.|  
|[espera](#wait)|Espera a que se señale el evento.|  
|[wait_for_multiple](#wait_for_multiple)|Espera a que se señalen varios eventos.|  
  
### <a name="public-constants"></a>Constantes públicas  
  
|nombre|Descripción|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|Valor que indica que una espera nunca debe agotar el tiempo de espera.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [estructuras de datos de sincronización](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `event`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** concrt.h  
  
 **Espacio de nombres:** simultaneidad  
  
##  <a name="ctor"></a> Evento 

 Construye un nuevo evento.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Comentarios  
  
##  <a name="dtor"></a> ~ eventos 

 Destruye un evento.  
  
```
~event();
```  
  
### <a name="remarks"></a>Comentarios  
 Se espera que no haya ningún subproceso esperando en el evento cuando el destructor se ejecuta. Permitir que el evento se destruya con subprocesos que todavía esperan da como resultado un comportamiento no definido.  
  
##  <a name="reset"></a> Restablecer 

 Restablece el evento a un estado no señalado.  
  
```
void reset();
```  
  
##  <a name="set"></a> Conjunto 

 Señala el evento.  
  
```
void set();
```  
  
### <a name="remarks"></a>Comentarios  
 Señalar el evento puede producir un número arbitrario de contextos que esperan en el evento para que se convierta en ejecutable.  
  
##  <a name="timeout_infinite"></a> timeout_infinite 

 Valor que indica que una espera nunca debe agotar el tiempo de espera.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a> espera 

 Espera a que se señale el evento.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Timeout`  
 Indica el número de milisegundos antes de que se agote el tiempo de espera. El valor `COOPERATIVE_TIMEOUT_INFINITE` significa que no hay tiempo de espera.  
  
### <a name="return-value"></a>Valor devuelto  
 Si se satisfizo la espera, se devuelve el valor `0`; de lo contrario, se devuelve el valor `COOPERATIVE_WAIT_TIMEOUT` para indicar que el tiempo de la espera se agota sin haber señalado el evento.  
  
> [!IMPORTANT]
>  En una aplicación de plataforma Universal de Windows (UWP), no llame a `wait` en el subproceso ASTA puesto que esta llamada puede bloquear el subproceso actual y puede provocar que la aplicación deje de responder.  
  
##  <a name="wait_for_multiple"></a> wait_for_multiple 

 Espera a que se señalen varios eventos.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parámetros  
 `_PPEvents`  
 Matriz de eventos en la que se va a esperar. El número de eventos dentro de la matriz viene indicado por el parámetro `count`.  
  
 `count`  
 El número de eventos dentro de la matriz proporcionado por el parámetro `_PPEvents`.  
  
 `_FWaitAll`  
 Si está establecido en el valor `true`, el parámetro especifica que todos los eventos de la matriz proporcionada en el parámetro `_PPEvents` deben señalarse para satisfacer la espera. Si está establecido en el valor `false`, especifica que cualquier evento de la matriz proporcionada en el parámetro `_PPEvents` que se ha señalado satisfará la espera.  
  
 `_Timeout`  
 Indica el número de milisegundos antes de que se agote el tiempo de espera. El valor `COOPERATIVE_TIMEOUT_INFINITE` significa que no hay tiempo de espera.  
  
### <a name="return-value"></a>Valor devuelto  
 Si se satisfizo la espera, el índice de la matriz proporcionada en el parámetro `_PPEvents` que satisfizo la condición de espera; de lo contrario, el valor `COOPERATIVE_WAIT_TIMEOUT` para indicar que el tiempo de la espera se agota sin satisfacer la condición.  
  
### <a name="remarks"></a>Comentarios  
 Si el parámetro `_FWaitAll` está establecido en el valor `true` para indicar que todos los eventos se deben señalar para satisfacer la espera, el índice que devuelve la función no tiene ninguna importancia especial aparte del hecho de que no es el valor `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  En una aplicación de plataforma Universal de Windows (UWP), no llame a `wait_for_multiple` en el subproceso ASTA puesto que esta llamada puede bloquear el subproceso actual y puede provocar que la aplicación deje de responder.  
  
## <a name="see-also"></a>Vea también  
 [concurrency (espacio de nombres)](concurrency-namespace.md)
