---
title: hash_compare (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_set/stdext::hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb1e42bf61c1fa70ee74063cd6857d842ee87de7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="hashcompare-class"></a>hash_compare (Clase)

La clase de plantilla describe un objeto que se puede usar con cualquiera de los contenedores asociativos hash (hash_map, hash_multimap, hash_set o hash_multiset) como un objeto de parámetro **Traits** predeterminado para ordenar y aplicar algoritmos hash a los elementos que contienen.

## <a name="syntax"></a>Sintaxis

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Comentarios

Cada contenedor asociativo de hash almacena un objeto traits hash de tipo **Traits** (un parámetro de plantilla). Puede derivar una clase de una especialización de hash_compare para reemplazar de forma selectiva ciertas funciones y objetos o puede proporcionar su propia versión de esta clase si cumple ciertos requisitos mínimos. En concreto, para un objeto hash_comp de tipo **hash_compare\<Key, Traits>**, los contenedores anteriores requieren el siguiente comportamiento:

- Para todos los valores `key` de tipo **Key**, la llamada **hash_comp**( `key`) actúa como una función hash, que produce una distribución de valores de tipo **size_t**. La función suministrada por hash_compare devuelve `key`.

- Para cualquier valor `key1` de tipo **Key** que preceda a `key2` en la secuencia y que tenga el mismo valor hash (valor devuelto por la función hash), **hash_comp**( `key2`, `key1`) es False. La función debe imponer una ordenación total en los valores de tipo **Key**. La función proporcionada por hash_compare devuelve *comp*( `key2`, `key1`) `,` donde *comp* es un objeto almacenado de tipo **Traits** que puede especificar al construir el objeto hash_comp. Para el tipo de parámetro **Traits** predeterminado **less\<Key>**, los criterios de ordenación nunca disminuyen en valor.

- La constante entera **bucket_size** especifica el número medio de elementos por "depósito" (entrada de tabla hash) que el contenedor debe intentar no superar. Debe ser mayor que cero. El valor proporcionado por hash_compare es 4.

- La constante entera **min_buckets** especifica el número mínimo de depósitos que se deben mantener en la tabla hash. Debe ser una potencia de dos y mayor que cero. El valor proporcionado por hash_compare es 8.

## <a name="example"></a>Ejemplo

Vea los ejemplos de [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) y [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset) para ver ejemplos sobre cómo declarar y usar hash_compare.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<hash_map>

**Espacio de nombres:** stdext

## <a name="see-also"></a>Vea también

[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)<br/>
