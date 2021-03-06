---
title: result_of (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13dcadc87c23e288c7f8c8a7f5bc9752aae5db7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="resultof-class"></a>result_of (Clase)

Determina el tipo de valor devuelto del tipo que se puede llamar que toma los tipos de argumento especificados.

## <a name="syntax"></a>Sintaxis

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>Parámetros

`Fn` El tipo que se puede llamar a la consulta.

`ArgTypes` Los tipos de la lista de argumentos para el tipo que se puede llamar a la consulta.

## <a name="remarks"></a>Comentarios

Use esta plantilla para determinar en tiempo de compilación el tipo de resultado de `Fn`(`ArgTypes`), donde `Fn` es un tipo que se puede llamar, la referencia a la función o la referencia al tipo que se puede llamar, invocado mediante una lista de argumentos de los tipos de `ArgTypes`. El miembro `type` de la clase de plantilla menciona el tipo de resultado de `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` si la expresión no evaluada `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` tiene el formato correcto. De lo contrario, la clase de plantilla no tiene ningún miembro `type`. El tipo `Fn` y todos los tipos en el paquete de parámetros `ArgTypes` deben ser tipos completos, `void` o matrices de límite desconocido.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<type_traits>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[<type_traits>](../standard-library/type-traits.md)<br/>
