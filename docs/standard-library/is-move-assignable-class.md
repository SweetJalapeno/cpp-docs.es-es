---
title: Clase is_move_assignable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adda28e4c6cc2a7ba7a387e125bd873b2107b687
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="ismoveassignable-class"></a>Clase is_move_assignable

Comprueba si el tipo se puede asignar mediante movimiento.

## <a name="syntax"></a>Sintaxis

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parámetros

`T` El tipo de consulta.

## <a name="remarks"></a>Comentarios

Un tipo se puede asignar mediante movimiento si una referencia a un valor R al tipo se puede asignar a una referencia al tipo. El predicado de tipo es equivalente a `is_assignable<T&, T&&>`. Los tipos que se pueden asignar mediante movimiento incluyen tipos escalares a los que se puede hacer referencia y tipos de clase que tienen operadores de asignación de movimiento generados por el compilador o definidos por el usuario.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<type_traits>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[<type_traits>](../standard-library/type-traits.md)<br/>
