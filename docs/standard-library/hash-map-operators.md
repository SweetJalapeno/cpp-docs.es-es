---
title: Operadores de &lt;hash_map&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
dev_langs:
- C++
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
ms.openlocfilehash: aa5c2a662fb5e827978a7c00aa3035dcc6cc97f2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="lthashmapgt-operators"></a>Operadores de &lt;hash_map&gt;

|||
|-|-|
|[operator!=](#op_neq)|[operator!= (multimap)](#op_neq_mm)|
|[operator==](#op_eq_eq)|[operator== (multimap)](#op_eq_eq_mm)|

## <a name="op_neq"></a> operator!=

> [!NOTE]
> Esta API está obsoleta. La alternativa es la [clase unordered_map](unordered-map-class.md).

Comprueba si el objeto hash_map del lado izquierdo del operador no es igual que el objeto hash_map del lado derecho.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parámetros

`left` Un objeto de tipo `hash_map`.

`right` Un objeto de tipo `hash_map`.

### <a name="return-value"></a>Valor devuelto

**True** si los objetos hash_map no son iguales; **False** si los objetos hash_map son iguales.

### <a name="remarks"></a>Comentarios

La comparación entre los objetos hash_map se basa en una comparación en pares de sus elementos. Dos objetos hash_map son iguales si tienen el mismo número de elementos y sus elementos respectivos tienen los mismos valores. Si no se cumplen estas condiciones, significa que son distintas.

Los miembros de la [< hash_map >](hash-map.md) y [< hash_set >](hash-set.md) archivos de encabezado en la [ stdext Namespace](stdext-namespace.md).

### <a name="example"></a>Ejemplo

```cpp
// hash_map_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="op_eq_eq"></a>  operator==

> [!NOTE]
> Esta API está obsoleta. La alternativa es la [clase unordered_map](unordered-map-class.md).

Comprueba si el objeto hash_map del lado izquierdo del operador es igual que el objeto hash_map del lado derecho.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parámetros

`left` Un objeto de tipo `hash_map`.

`right` Un objeto de tipo `hash_map`.

### <a name="return-value"></a>Valor devuelto

**True** si el objeto hash_map del lado izquierdo del operador es igual que el objeto hash_map del lado derecho del operador. En caso contrario, **False**.

### <a name="remarks"></a>Comentarios

La comparación entre los objetos hash_map se basa en una comparación en pares de sus elementos. Dos objetos hash_map son iguales si tienen el mismo número de elementos y sus elementos respectivos tienen los mismos valores. Si no se cumplen estas condiciones, significa que son distintas.

### <a name="example"></a>Ejemplo

```cpp
// hash_map_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 == hm2 )
      cout << "The hash_maps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="op_neq_mm"></a>  operador! = (hash_multimap)

> [!NOTE]
> Esta API está obsoleta. La alternativa es la [clase unordered_multimap](unordered-multimap-class.md).

Comprueba si el objeto hash_multimap del lado izquierdo del operador no es igual que el objeto hash_multimap del lado derecho.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parámetros

`left` Un objeto de tipo `hash_multimap`.

`right` Un objeto de tipo `hash_multimap`.

### <a name="return-value"></a>Valor devuelto

**True** si los objetos hash_multimap no son iguales; **False** si los objetos hash_multimap son iguales.

### <a name="remarks"></a>Comentarios

La comparación entre los objetos hash_multimap se basa en una comparación en pares de sus elementos. Dos objetos hash_multimap son iguales si tienen el mismo número de elementos y sus elementos respectivos tienen los mismos valores. Si no se cumplen estas condiciones, significa que son distintas.

### <a name="example"></a>Ejemplo

```cpp
// hash_multimap_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="op_eq_eq_mm"></a>  operador == (hash_multimap)

> [!NOTE]
> Esta API está obsoleta. La alternativa es la [clase unordered_multimap](unordered-multimap-class.md).

Comprueba si el objeto hash_multimap del lado izquierdo del operador es igual que el objeto hash_multimap del lado derecho.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parámetros

`left` Un objeto de tipo `hash_multimap`.

`right` Un objeto de tipo `hash_multimap`.

### <a name="return-value"></a>Valor devuelto

**True** si el objeto hash_multimap del lado izquierdo del operador es igual que el objeto hash_multimap del lado derecho del operador. En caso contrario, **False**.

### <a name="remarks"></a>Comentarios

La comparación entre los objetos hash_multimap se basa en una comparación en pares de sus elementos. Dos objetos hash_multimap son iguales si tienen el mismo número de elementos y sus elementos respectivos tienen los mismos valores. Si no se cumplen estas condiciones, significa que son distintas.

### <a name="example"></a>Ejemplo

```cpp
// hash_multimap_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1, hm2, hm3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      hm1.insert(Int_Pair(i, i));
      hm2.insert(Int_Pair(i, i*i));
      hm3.insert(Int_Pair(i, i));
   }

   if ( hm1 == hm2 )
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="see-also"></a>Vea también

[<hash_map>](hash-map.md)<br/>
