---
title: pointer_to_binary_function (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39549a277a203d9daa894f48437224caf50a0521
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function (Clase)

Convierte un puntero a función binaria en una función binaria adaptable.

## <a name="syntax"></a>Sintaxis

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parámetros

`pfunc` La función binaria que se va a convertir.

`left` Objeto de la izquierda el  *\*pfunc* se llama en.

`right` Objeto de la derecha el  *\*pfunc* se llama en.

## <a name="return-value"></a>Valor devuelto

La clase de plantilla almacena una copia de **pfunc**. Define su función miembro `operator()` para que devuelva (\* **pfunc**)(_ *Left*, \_ *Right*).

## <a name="remarks"></a>Comentarios

Un puntero de función binaria es un objeto de función y puede pasarse a cualquier algoritmo de la biblioteca estándar de C++ que esté esperando una función binaria como un parámetro, pero no es adaptable. Para usarlo como un adaptador, por ejemplo al enlazar un valor a este o usándolo con un negador, debe proporcionarse con los tipos anidados **first_argument_type**, **second_argument_type** y **result_type** que hacen posible dicha adaptación. La conversión mediante `pointer_to_binary_function` permite a los adaptadores de función que funcionen con punteros de función binaria.

## <a name="example"></a>Ejemplo

El constructor de `pointer_to_binary_function` no suele usarse directamente. Vea la función auxiliar [ptr_fun](../standard-library/functional-functions.md#ptr_fun) para obtener un ejemplo de cómo declarar y usar el predicador del adaptador de `pointer_to_binary_function`.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<functional>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)<br/>
