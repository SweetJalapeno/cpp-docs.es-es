---
title: recursive_mutex (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 89c39f006cee8c62c22f3caf7e2c10ee9a0c1d03
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="recursivemutex-class"></a>recursive_mutex (Clase)

Representa un *tipo de exclusión mutua*. Al contrario que [mutex](../standard-library/mutex-class-stl.md), el comportamiento de las llamadas a métodos de bloqueo para objetos que ya están bloqueados está bien definido.

## <a name="syntax"></a>Sintaxis

```cpp
class recursive_mutex;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Construye un objeto `recursive_mutex`.|
|[~recursive_mutex (Destructor)](#dtorrecursive_mutex_destructor)|Libera todos los recursos usados por el objeto `recursive_mutex`.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[lock](#lock)|Bloquea el subproceso de llamada hasta que este obtiene la propiedad de la exclusión mutua.|
|[try_lock](#try_lock)|Intenta obtener la propiedad de la exclusión mutua sin bloquearla.|
|[unlock](#unlock)|Libera la propiedad de la exclusión mutua.|

## <a name="requirements"></a>Requisitos

**Encabezado:** \<mutex >

**Espacio de nombres:** std

## <a name="lock"></a> lock

Bloquea el subproceso que realiza la llamada hasta que este obtiene la propiedad `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Comentarios

Si el subproceso que realiza la llamada ya posee `mutex`, el método se devuelve inmediatamente, y el bloqueo anterior permanece vigente.

## <a name="recursive_mutex"></a> recursive_mutex

Crea un objeto `recursive_mutex` que no está bloqueado.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a> ~recursive_mutex

Libera todos los recursos usados por el objeto.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Comentarios

Si el objeto está bloqueado cuando se ejecuta el destructor, el comportamiento es indefinido.

## <a name="try_lock"></a> try_lock

Intenta obtener la propiedad de `mutex` sin bloquearlo.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Valor devuelto

`true` si el método obtiene correctamente la propiedad de `mutex` o si el subproceso que realiza la llamada ya posee `mutex`; de otro modo, `false`.

### <a name="remarks"></a>Comentarios

Si el subproceso que realiza la llamada ya posee `mutex`, la función devuelve `true` inmediatamente, y el bloqueo anterior permanece vigente.

## <a name="unlock"></a> unlock

Libera la propiedad de la exclusión mutua.

```cpp
void unlock();
```

### <a name="remarks"></a>Comentarios

Este método libera la propiedad de `mutex` solo después de que se llame tantas veces como se ha llamado a [lock](#lock) y [try_lock](#try_lock) correctamente en el objeto `recursive_mutex`.

Si el subproceso que realiza la llamada no posee `mutex`, el comportamiento es indefinido.

## <a name="see-also"></a>Vea también

[Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
