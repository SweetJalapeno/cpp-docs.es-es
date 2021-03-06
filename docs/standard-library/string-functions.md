---
title: Funciones &lt;string&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: 0089a7259601b766bff3b470c5ba23c1b9952fb6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="ltstringgt-functions"></a>Funciones &lt;string&gt;

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>  getline

Extraiga las cadenas de la secuencia de entrada línea por línea.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);


template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);


// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);


template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parámetros

`is` El flujo de entrada desde el que es una cadena se va a extraer.

`str` La cadena en la que se leen los caracteres del flujo de entrada.

`delim` El delimitador de línea.

### <a name="return-value"></a>Valor devuelto

La secuencia de entrada `is`.

### <a name="remarks"></a>Comentarios

El par de firmas de función marcado como `(1)` extrae caracteres de `is` hasta encontrar `delim` y los almacena en `str`.

El par de firmas de función marcado como `(2)` usa una nueva línea como el delimitador de línea predeterminado y se comporta como **getline**( `is`, `str`, `is`. `widen`(' `\n`')).

La segunda función de cada par es análoga a la primera para admitir las [referencias rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).

La extracción se detiene en los siguientes casos:

- El fin de archivo, en cuyo caso la marca de estado interno de `is` se establece en `ios_base::eofbit`.

- Después de que la función extraiga un elemento que se compare con relación de igualdad con **delim**, en cuyo caso el elemento no se vuelve a colocar ni se anexa a la secuencia controlada.

- Después de que la función extraiga los elementos `str.`[max_size](../standard-library/basic-string-class.md#max_size), en cuyo caso la marca de estado interno de `is` se establece en `ios_base::failbit`.

- Otros errores distintos de los que mencionamos, en cuyo caso la marca de estado interno de `is` se establece en `ios_base::badbit`.

Para obtener información sobre las marcas de estado interno, vea [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Si la función no extrae ningún elemento, la marca de estado interno de `is` se establece en `ios_base::failbit`. En cualquier caso, `getline` devuelve `is`.

Si se lanza una excepción, `is` y `str` se dejan en un estado válido.

### <a name="example"></a>Ejemplo

El código siguiente muestra `getline()` en dos modos: primero, con el delimitador predeterminado (nueva línea) y, después, con un espacio en blanco como delimitador. El carácter de fin de archivo (CTRL-Z en el teclado) se utiliza para controlar la terminación de los bucles while. Establece la marca de estado interno de `cin` en `eofbit`, que se debe borrar con [basic_ios::clear()](../standard-library/basic-ios-class.md#clear) para que el segundo bucle while funcione correctamente.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}

```

## <a name="stod"></a>  stod

Convierte una secuencia de caracteres en una `double`.

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|

### <a name="return-value"></a>Valor devuelto

Valor de `double`.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `double` como si se llamara a `strtod( str.c_str(), _Eptr)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="stof"></a>  stof

Convierte una secuencia de caracteres en un float.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|

### <a name="return-value"></a>Valor devuelto

El valor del float.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `float` como si se llamara a `strtof( str.c_str(), _Eptr)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="stoi"></a>  stoi

Convierte una secuencia de caracteres en un entero.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Valor devuelto

El valor del entero.

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|Contiene el índice del primer carácter que no se convertirá en la devolución.|
|`base`|La base numérica que se usará.|

### <a name="remarks"></a>Comentarios

La función `stoi` convierte la secuencia de caracteres de `str` en un valor de tipo `int` y devuelve el valor. Por ejemplo, cuando se pasa la secuencia de caracteres “10”, el valor devuelto por `stoi` es el número entero 10.

`stoi` se comporta de manera similar a la función `strtol` con caracteres de byte único cuando se llama a esta función con la forma `strtol( str.c_str(), _Eptr, idx)`, donde `_Eptr` es un objeto interno de la función. Con caracteres anchos, es similar a la función `wcstol` cuando se llama a esta función de modo similar, `wcstol(Str.c_str(), _Eptr, idx)`. Para más información, vea [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Si `str.c_str() == *_Eptr`, `stoi` lanza un objeto de tipo `invalid_argument`. Si esa llamada establece `errno`, o si el valor devuelto no se puede representar como un objeto del tipo `int`, lanza un objeto del tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr - str.c_str()` en `*idx`.

## <a name="stol"></a>  stol

Convierte una secuencia de caracteres en una `long`.

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|
|`base`|La base numérica que se usará.|

### <a name="return-value"></a>Valor devuelto

El valor de entero largo.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `long` como si se llamara a `strtol( str.c_str(), _Eptr, idx)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="stold"></a>  stold

Convierte una secuencia de caracteres en una `long double`.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|

### <a name="return-value"></a>Valor devuelto

Valor de `long double`.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `long double` como si se llamara a `strtold( str.c_str(), _Eptr)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="stoll"></a>  stoll

Convierte una secuencia de caracteres en una `long long`.

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|
|`base`|La base numérica que se usará.|

### <a name="return-value"></a>Valor devuelto

Valor de `long long`.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `long long` como si se llamara a `strtoll( str.c_str(), _Eptr, idx)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="stoul"></a>  stoul

Convierte una secuencia de caracteres en un entero largo sin signo.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|
|`base`|La base numérica que se usará.|

### <a name="return-value"></a>Valor devuelto

El valor del entero largo sin signo.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `unsigned long` como si se llamara a `strtoul( str.c_str(), _Eptr, idx)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="stoull"></a>  stoull

Convierte una secuencia de caracteres en un `unsigned long long`.

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`str`|La secuencia de caracteres que se convertirá.|
|`idx`|El valor del índice del primer carácter que no se convertirá.|
|`base`|La base numérica que se usará.|

### <a name="return-value"></a>Valor devuelto

Valor de `unsigned long long`.

### <a name="remarks"></a>Comentarios

La función convierte la secuencia de elementos de `str` en un valor `val` de tipo `unsigned long long` como si se llamara a `strtoull( str.c_str(), _Eptr, idx)`, donde `_Eptr` es un objeto interno de la función. Si ` str.c_str() == *_Eptr`, lanza un objeto de tipo `invalid_argument`. Si esa llamada, al ejecutarse, establecería `errno`, lanza un objeto de tipo `out_of_range`. Si no, siempre que `idx` no sea un puntero nulo, la función almacena `*_Eptr -  str.c_str()` en `*idx` y devuelve `val`.

## <a name="swap"></a>  swap

Intercambia las matrices de caracteres de dos cadenas.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parámetros

`left` Una cadena cuyos elementos se deben intercambiar con los de otra cadena.

`right` La otra cadena cuyos elementos se deben intercambiar con la primera cadena.

### <a name="remarks"></a>Comentarios

La función de plantilla ejecuta la función miembro especializada *izquierdo*.[ intercambio](../standard-library/basic-string-class.md#swap)(*derecho*) para las cadenas, lo que garantiza la complejidad constante.

### <a name="example"></a>Ejemplo

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a>  to_string

Convierte un valor en `string`.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`Val`|El valor que se va a convertir.|

### <a name="return-value"></a>Valor devuelto

`string` que representa el valor.

### <a name="remarks"></a>Comentarios

La función convierte `Val` en una secuencia de elementos almacenados en un objeto de matriz `Buf` interno de la función como si se llamara a `sprintf(Buf, Fmt, Val)`, donde `Fmt` es

- `"%d"` si `Val` tiene el tipo `int`

- `"%u"` si `Val` tiene el tipo `unsigned int`

- `"%ld"` si `Val` tiene el tipo `long`

- `"%lu"` si `Val` tiene el tipo `unsigned long`

- `"%lld"` si `Val` tiene el tipo `long long`

- `"%llu"` si `Val` tiene el tipo `unsigned long long`

- `"%f"` si `Val` tiene el tipo `float` o `double`

- `"%Lf"` si `Val` tiene el tipo `long double`

La función devuelve `string(Buf)`.

## <a name="to_wstring"></a>  to_wstring

Convierte un valor en una cadena de tipo ancho.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|`Val`|El valor que se va a convertir.|

### <a name="return-value"></a>Valor devuelto

Cadena de tipo ancho que representa el valor.

### <a name="remarks"></a>Comentarios

La función convierte `Val` en una secuencia de elementos almacenados en un objeto de matriz `Buf` interno de la función como si se llamara a `swprintf(Buf, Len, Fmt, Val)`, donde `Fmt` es

- `L"%d"` si `Val` tiene el tipo `int`

- `L"%u"` si `Val` tiene el tipo `unsigned int`

- `L"%ld"` si `Val` tiene el tipo `long`

- `L"%lu"` si `Val` tiene el tipo `unsigned long`

- `L"%lld"` si `Val` tiene el tipo `long long`

- `L"%llu"` si `Val` tiene el tipo `unsigned long long`

- `L"%f"` si `Val` tiene el tipo `float` o `double`

- `L"%Lf"` si `Val` tiene el tipo `long double`

La función devuelve `wstring(Buf)`.

## <a name="see-also"></a>Vea también

[\<string>](../standard-library/string.md)<br/>
