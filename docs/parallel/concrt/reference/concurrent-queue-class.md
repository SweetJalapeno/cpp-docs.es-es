---
title: Clase concurrent_queue | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
dev_langs:
- C++
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9a3ee82b8b81532b4e63f080ad321a93725ce41
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentqueue-class"></a>Clase concurrent_queue
La clase `concurrent_queue` es una clase de contenedor de secuencias que permite el acceso primero en entrar, primero en salir a sus elementos. Habilita un conjunto limitado de operaciones seguras para simultaneidad, como `push` y `try_pop`.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 El tipo de datos de los elementos que se almacenará en la cola.  
  
 `_Ax`  
 El tipo que representa el objeto de asignador almacenado que encapsula los detalles sobre la asignación y desasignación de memoria para esta cola simultánea. Este argumento es opcional y el valor predeterminado es `allocator<T>`.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-typedefs"></a>Definiciones de tipos públicas  
  
|Name|Descripción|  
|----------|-----------------|  
|`allocator_type`|Tipo que representa la clase de asignador de la cola simultánea.|  
|`const_iterator`|Un tipo que representa un no subprocesos `const` iterador sobre los elementos en una cola simultánea.|  
|`const_reference`|Un tipo que proporciona una referencia a un `const` elemento almacenado en una cola simultánea para leer y realizar `const` operaciones.|  
|`difference_type`|Un tipo que proporciona la distancia firmada entre dos elementos en una cola simultánea.|  
|`iterator`|Tipo que representa un iterador no es segura para subprocesos sobre los elementos en una cola simultánea.|  
|`reference`|Un tipo que proporciona una referencia a un elemento almacenado en una cola simultánea.|  
|`size_type`|Tipo que cuenta el número de elementos en una cola simultánea.|  
|`value_type`|Tipo que representa el tipo de datos almacenados en una cola simultánea.|  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|Sobrecargado. Construye una cola simultánea.|  
|[~ concurrent_queue (destructor)](#dtor)|Destruye la cola simultánea.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[clear](#clear)|Borra la cola simultánea, los destruyendo actualmente los elementos en cola. Este método no es seguro para la simultaneidad.|  
|[empty](#empty)|Comprueba si la cola simultánea está vacía en el momento en que se llama a este método. Este método es seguro para simultaneidad.|  
|[get_allocator](#get_allocator)|Devuelve una copia del asignador usada para construir la cola simultánea. Este método es seguro para simultaneidad.|  
|[push](#push)|Sobrecargado. Pone en cola un elemento al final de la cola simultánea. Este método es seguro para simultaneidad.|  
|[try_pop](#try_pop)|Quita un elemento de la cola si está disponible. Este método es seguro para simultaneidad.|  
|[unsafe_begin](#unsafe_begin)|Sobrecargado. Devuelve un iterador de tipo `iterator` o `const_iterator` al principio de la cola simultánea. Este método no es seguro para la simultaneidad.|  
|[unsafe_end](#unsafe_end)|Sobrecargado. Devuelve un iterador de tipo `iterator` o `const_iterator` al final de la cola simultánea. Este método no es seguro para la simultaneidad.|  
|[unsafe_size](#unsafe_size)|Devuelve el número de elementos en la cola. Este método no es seguro para la simultaneidad.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información, consulte [contenedores y objetos paralelos](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `concurrent_queue`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** concurrent_queue.h  
  
 **Espacio de nombres:** simultaneidad  
  
##  <a name="clear"></a> Borrar 

 Borra la cola simultánea, los destruyendo actualmente los elementos en cola. Este método no es seguro para la simultaneidad.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_queue 

 Construye una cola simultánea.  
  
```
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>Parámetros  
 `_InputIterator`  
 El tipo de iterador de entrada que especifica un intervalo de valores.  
  
 `_Al`  
 La clase de asignador que se usa con este objeto.  
  
 `_OtherQ`  
 El objeto de origen `concurrent_queue` del que copiar o mover elementos.  
  
 `_Begin`  
 Posición del primer elemento en el intervalo de elementos que se va a copiar.  
  
 `_End`  
 Posición del primer elemento más allá del intervalo de elementos que se va a copiar.  
  
### <a name="remarks"></a>Comentarios  
 Todos los constructores almacenan un objeto de asignador `_Al` e inicializar la cola.  
  
 El primer constructor especifica una cola inicial vacía y especifica explícitamente el tipo de asignador que se usará.  
  
 El segundo constructor especifica una copia de la cola simultánea `_OtherQ`.  
  
 El tercer constructor especifica una operación de traslado de la cola simultánea `_OtherQ`.  
  
 El cuarto constructor especifica los valores proporcionados por el intervalo de iterador [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~ concurrent_queue 

 Destruye la cola simultánea.  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a> vacía 

 Comprueba si la cola simultánea está vacía en el momento en que se llama a este método. Este método es seguro para simultaneidad.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si la cola simultánea estaba vacía en el momento en que hemos explicado, `false` en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Aunque este método es seguro para simultaneidad con respecto a las llamadas a los métodos `push`, `try_pop`, y `empty`, el valor devuelto podría ser incorrecto durante el tiempo que es inspeccionado por el subproceso que realiza la llamada.  
  
##  <a name="get_allocator"></a> get_allocator 

 Devuelve una copia del asignador usada para construir la cola simultánea. Este método es seguro para simultaneidad.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Una copia del asignador usada para construir la cola simultánea.  
  
##  <a name="push"></a> Inserción 

 Pone en cola un elemento al final de la cola simultánea. Este método es seguro para simultaneidad.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Src`  
 El elemento que se va a agregarse a la cola.  
  
### <a name="remarks"></a>Comentarios  
 `push` es seguro para simultaneidad con respecto a las llamadas a los métodos `push`, `try_pop`, y `empty`.  
  
##  <a name="try_pop"></a> try_pop 

 Quita un elemento de la cola si está disponible. Este método es seguro para simultaneidad.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Dest`  
 Una referencia a una ubicación para almacenar el elemento quitado de la cola.  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si un elemento se quitó correctamente la cola, `false` en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Si un elemento se quitó correctamente la cola, el parámetro `_Dest` recibe el valor quitado de la cola, se destruye el valor original que se retienen en la cola y esta función devuelve `true`. Si no había ningún elemento para quitar de la cola, esta función devuelve `false` sin bloqueo y el contenido de la `_Dest` parámetro son indefinidos.  
  
 `try_pop` es seguro para simultaneidad con respecto a las llamadas a los métodos `push`, `try_pop`, y `empty`.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 Devuelve un iterador de tipo `iterator` o `const_iterator` al principio de la cola simultánea. Este método no es seguro para la simultaneidad.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un iterador de tipo `iterator` o `const_iterator` al principio del objeto de cola simultáneos.  
  
### <a name="remarks"></a>Comentarios  
 Los iteradores para la `concurrent_queue` clase están pensados principalmente para la depuración, como son lentas e iteración no es seguro para simultaneidad con respecto a otras operaciones de cola.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 Devuelve un iterador de tipo `iterator` o `const_iterator` al final de la cola simultánea. Este método no es seguro para la simultaneidad.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un iterador de tipo `iterator` o `const_iterator` al final de la cola simultánea.  
  
### <a name="remarks"></a>Comentarios  
 Los iteradores para la `concurrent_queue` clase están pensados principalmente para la depuración, como son lentas e iteración no es seguro para simultaneidad con respecto a otras operaciones de cola.  
  
##  <a name="unsafe_size"></a> unsafe_size 

 Devuelve el número de elementos en la cola. Este método no es seguro para la simultaneidad.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 El tamaño de la cola simultánea.  
  
### <a name="remarks"></a>Comentarios  
 `unsafe_size` no es seguro para simultaneidad y puede generar resultados incorrectos si se llama al mismo tiempo que las llamadas a los métodos `push`, `try_pop`, y `empty`.  
  
## <a name="see-also"></a>Vea también  
 [concurrency (espacio de nombres)](concurrency-namespace.md)
