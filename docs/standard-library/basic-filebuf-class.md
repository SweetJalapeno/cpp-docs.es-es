---
title: basic_filebuf (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65dc91bebf55c617d5c18d86d308558e57cbd3c3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="basicfilebuf-class"></a>basic_filebuf (Clase)

Describe un búfer de secuencia que controla la transmisión de elementos de tipo `Elem`, cuyos rasgos de caracteres están determinados por la clase `Tr`, a y desde una secuencia de elementos almacenados en un archivo externo.

## <a name="syntax"></a>Sintaxis

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parámetros

`Elem` El elemento básico del búfer del archivo.

`Tr` Características del elemento básico del búfer del archivo (normalmente `char_traits` <  `Elem`>).

## <a name="remarks"></a>Comentarios

La clase de plantilla describe un búfer de secuencia que controla la transmisión de elementos de tipo `Elem`, cuyos rasgos de caracteres están determinados por la clase `Tr`, a y desde una secuencia de elementos almacenados en un archivo externo.

> [!NOTE]
> Los objetos de tipo `basic_filebuf` se crean con un búfer interno de tipo `char *`, independientemente del `char_type` especificado por el parámetro de tipo `Elem`. Esto significa que una cadena Unicode (que contiene caracteres `wchar_t`) se convertirá en una cadena ANSI (que contiene caracteres `char`) antes de que se escriba en el búfer interno. Para almacenar cadenas Unicode en el búfer, cree un nuevo búfer de tipo `wchar_t` y establézcalo mediante el método [basic_streambuf::pubsetbuf](../standard-library/basic-streambuf-class.md#pubsetbuf)`()`. Para ver un ejemplo que muestra este comportamiento, vea a continuación.

Un objeto de clase `basic_filebuf`< `Elem`, `Tr`> almacena un puntero de archivo, que designa el objeto `FILE` que controla el flujo asociado a un archivo abierto. También almacena punteros a dos facetas de conversión de archivo para su uso por parte de las funciones miembro protegidas [overflow](#overflow) y [underflow](#underflow). Para más información, vea [basic_filebuf::open](#open).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo forzar un objeto de tipo `basic_filebuf<wchar_t>` para almacenar caracteres Unicode en su búfer interno mediante una llamada al método `pubsetbuf()`.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>Constructores

|Constructor|Descripción|
|-|-|
|[basic_filebuf](#basic_filebuf)|Construye un objeto de tipo `basic_filebuf`.|

### <a name="typedefs"></a>Typedefs

|Nombre de tipo|Descripción|
|-|-|
|[char_type](#char_type)|Asocia un nombre de tipo con el parámetro de plantilla `Elem`.|
|[int_type](#int_type)|Hace que este tipo en el ámbito de `basic_filebuf` equivalga al tipo con el mismo nombre del ámbito `Tr`.|
|[off_type](#off_type)|Hace que este tipo en el ámbito de `basic_filebuf` equivalga al tipo con el mismo nombre del ámbito `Tr`.|
|[pos_type](#pos_type)|Hace que este tipo en el ámbito de `basic_filebuf` equivalga al tipo con el mismo nombre del ámbito `Tr`.|
|[traits_type](#traits_type)|Asocia un nombre de tipo con el parámetro de plantilla `Tr`.|

### <a name="member-functions"></a>Funciones miembro

|Función miembro|Descripción|
|-|-|
|[close](#close)|Cierra un archivo.|
|[is_open](#is_open)|Indica si un archivo está abierto.|
|[open](#open)|Abre un archivo.|
|[overflow](#overflow)|Función virtual protegida a la que se puede llamar cuando se inserta un carácter nuevo en un búfer lleno.|
|[pbackfail](#pbackfail)|La función miembro virtual protegida intenta colocar un elemento en el flujo de entrada y, a continuación, convertirlo en el elemento actual (indicado por el puntero siguiente).|
|[seekoff](#seekoff)|La función miembro virtual protegida trata de modificar las posiciones actuales de las secuencias controladas.|
|[seekpos](#seekpos)|La función miembro virtual protegida trata de modificar las posiciones actuales de las secuencias controladas.|
|[setbuf](#setbuf)|La función miembro virtual protegida realiza una determinada operación para cada búfer de secuencia derivado.|
|[Swap](#swap)|Intercambia el contenido de `basic_filebuf` por el contenido del parámetro `basic_filebuf` proporcionado.|
|[sync](#sync)|Función virtual protegida que intenta sincronizar las secuencias controladas con cualquier flujo externo asociado.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Función virtual protegida que extrae el elemento actual de la secuencia de entrada.|
|[underflow](#underflow)|Función virtual protegida que extrae el elemento actual de la secuencia de entrada.|

## <a name="requirements"></a>Requisitos

**Encabezado:** \<fstream>

**Espacio de nombres:** std

## <a name="basic_filebuf"></a>  basic_filebuf::basic_filebuf

Construye un objeto de tipo `basic_filebuf`.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Comentarios

El primer constructor almacena un puntero nulo en todos los punteros que controlan el búfer de entrada y el de salida. También almacena un puntero nulo en el puntero de archivo.

El segundo constructor inicializa el objeto con el contenido de `right`, tratado como una referencia a un valor R.

## <a name="char_type"></a>  basic_filebuf::char_type

Asocia un nombre de tipo al parámetro de plantilla **Elem**.

```cpp
typedef Elem char_type;
```

## <a name="close"></a>  basic_filebuf::close

Cierra un archivo.

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>Valor devuelto

La función miembro devuelve un puntero nulo si el puntero de archivo es un puntero nulo.

### <a name="remarks"></a>Comentarios

**close** llama a `fclose`(**fp**). Si esa función devuelve un valor distinto de cero, la función devuelve un puntero nulo. De lo contrario, devuelve **this** para indicar que el archivo se ha cerrado correctamente.

En un flujo ancho, si se han producido inserciones desde la apertura del flujo o desde la última llamada a `streampos`, la función llama a [overflow](#overflow). Además se inserta cualquier secuencia necesaria para restaurar el estado de conversión inicial mediante la faceta de conversión de archivo **fac** para llamar a **fac.unshift** según sea necesario. Cada elemento **byte** de tipo `char` producido así se escribe en el flujo asociado designado por el puntero de archivo **fp** como si se hiciera mediante llamadas sucesivas del formato `fputc`(**byte**, **fp**). Si se produce un error en la llamada a **fac.unshift** o en cualquier escritura, la función no se ejecuta correctamente.

### <a name="example"></a>Ejemplo

En el ejemplo siguiente se asume que hay dos archivos en el directorio actual: basic_filebuf_close.txt (el contenido es "testing") e iotest.txt (el contenido es "ssss").

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="int_type"></a>  basic_filebuf::int_type

Hace que este tipo en el ámbito de basic_filebuf equivalga al tipo con el mismo nombre del ámbito **Tr**.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>  basic_filebuf::is_open

Indica si un archivo está abierto.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Valor devuelto

**True** si el puntero de archivo no es un puntero nulo.

### <a name="example"></a>Ejemplo

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="off_type"></a>  basic_filebuf::off_type

Hace que este tipo en el ámbito de basic_filebuf equivalga al tipo con el mismo nombre del ámbito **Tr**.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>  basic_filebuf::open

Abre un archivo.

```cpp
basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Parámetros

`_Filename` El nombre de archivo que se abre.

`_Mode` Una de las enumeraciones en [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode).

`_Prot` El archivo predeterminado abrir protección, equivalente a la `shflag` parámetro en [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="return-value"></a>Valor devuelto

Si el puntero de archivo es un puntero nulo, la función devuelve un puntero nulo. De lo contrario, devuelve **this**.

### <a name="remarks"></a>Comentarios

La función miembro abre el archivo con el nombre de archivo *filename* al llamar a [fopen](../c-runtime-library/reference/fopen-wfopen.md)(*filename*, **strmode**). **strmode** se determina a partir de **mode &**~([ate](../standard-library/ios-base-class.md#openmode) & &#124; [binary](../standard-library/ios-base-class.md#openmode)):

- **ios_base::in** se convierte en **"r"** (abra el archivo existente para su lectura).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) o **ios_base::out &#124; ios_base::trunc** se convierten en **"w"** (trunque el archivo existente o cree para escritura).

- **ios_base::out &#124; app** se convierte en **"a"** (abra el archivo existente para anexar todas las escrituras).

- **ios_base::in &#124; ios_base::out** se convierte en **"r+"** (abra el archivo existente para leer y escribir).

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc** se convierte en **"w+"** (trunque el archivo existente o cree para lectura y escritura).

- **ios_base::in &#124; ios_base::out &#124; ios_base::app** se convierte en **"a+"** (abra el archivo existente para lectura y para anexar todas las escrituras).

Si **mode & ios_base::binary** es distinto de cero, la función anexa **b** a **strmode** para abrir un flujo binario en lugar de un flujo de texto. Luego almacena el valor devuelto por `fopen` en el puntero de archivo **fp**. Si **mode & ios_base::ate** es distinto de cero y el puntero de archivo no es un puntero nulo, la función llama a `fseek`(**fp**, 0, `SEEK_END`) para colocar el flujo al final del archivo. Si se produce un error en esa operación de posicionamiento, la función llama a [close](#close)(**fp**) y almacena un puntero nulo en el puntero de archivo.

Si el puntero de archivo no es un puntero nulo, la función determina la faceta de conversión de archivo: `use_facet`< `codecvt`< **Elem**, `char`, **traits_type::**[state_type](../standard-library/char-traits-struct.md#state_type)> >([getloc](../standard-library/basic-streambuf-class.md#getloc)) para que la usen [underflow](#underflow) y [overflow](#overflow).

Si el puntero de archivo es un puntero nulo, la función devuelve un puntero nulo. De lo contrario, devuelve **this**.

### <a name="example"></a>Ejemplo

Vea [basic_filebuf::close](#close) para obtener un ejemplo de uso de **open**.

## <a name="op_eq"></a>  basic_filebuf::operator=

Asigna el contenido de este objeto de búfer de secuencia. Se trata de una asignación de movimiento que implica un valor R que no deja ninguna copia atrás.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parámetros

`right` Una referencia a valor r a un [basic_filebuf](../standard-library/basic-filebuf-class.md) objeto.

### <a name="return-value"></a>Valor devuelto

Devuelve *this.

### <a name="remarks"></a>Comentarios

El operador de miembro reemplaza el contenido del objeto por el contenido de `right`, que se trata como referencia rvalue. Para más información, vea [Declarador de referencia a un valor R: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="overflow"></a>  basic_filebuf::overflow

Se llama cuando se inserta un nuevo carácter en un búfer lleno.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parámetros

`_Meta` El carácter que se va a insertar en el búfer o **traits_type::eof**.

### <a name="return-value"></a>Valor devuelto

Si la función no se puede ejecutar correctamente, devuelve **traits_type::eof**. De lo contrario, devuelve **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Comentarios

Si _ *Meta***!= traits_type::**[eof](../standard-library/char-traits-struct.md#eof), la función miembro virtual protegida intenta insertar el elemento **ch = traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) en el búfer de salida. Puede hacerlo de varias maneras:

- Si está disponible una posición de escritura, puede almacenar el elemento en la posición de escritura e incrementar el puntero siguiente para el búfer de salida.

- Puede proporcionar una posición de escritura al asignar almacenamiento nuevo o adicional para el búfer de salida.

- Puede convertir cualquier salida pendiente en el búfer de salida, seguida de **ch**, mediante la faceta de conversión de archivo **fac** para llamar a **fac.out** según sea necesario. Cada elemento `ch` de tipo *char* producido así se escribe en el flujo asociado designado por el puntero de archivo **fp** como si se hiciera mediante llamadas sucesivas del formato `fputc`(**ch**, **fp**). Si se produce un error en cualquier conversión o escritura, la función no se ejecuta correctamente.

## <a name="pbackfail"></a>  basic_filebuf::pbackfail

Intenta volver a colocar un elemento en el flujo de entrada y luego convertirlo en el elemento actual (al que apunta el puntero siguiente).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parámetros

`_Meta` El carácter que se va a insertar en el búfer, o **traits_type::eof**.

### <a name="return-value"></a>Valor devuelto

Si la función no se puede ejecutar correctamente, devuelve **traits_type::eof**. De lo contrario, devuelve **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Comentarios

La función miembro virtual protegida vuelve a colocar un elemento en el búfer de entrada y luego lo convierte en el elemento actual (al que apunta el siguiente puntero). Si _ *Meta* **== traits_type::**[eof](../standard-library/char-traits-struct.md#eof), el elemento que se va a devolver es realmente el que ya estaba en el flujo por delante del elemento actual. De lo contrario, ese elemento se sustituye por **ch = traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*). La función puede devolver un elemento de distintas maneras:

- Si hay disponible una posición de devolución y el elemento almacenado es igual a **ch**, puede disminuir el puntero siguiente para el búfer de entrada.

- Si la función puede conseguir que haya una posición `putback` disponible, puede hacerlo, establecer el siguiente puntero para que apunte a esa posición y almacenar **ch** en ella.

- Si la función puede insertar nuevo un elemento en el flujo de entrada, puede hacerlo, por ejemplo, mediante una llamada a `ungetc` para un elemento de tipo `char`.

## <a name="pos_type"></a>  basic_filebuf::pos_type

Hace que este tipo en el ámbito de basic_filebuf equivalga al tipo con el mismo nombre del ámbito **Tr**.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_filebuf::seekoff

Intenta modificar las posiciones actuales de los flujos controlados.

```cpp
virtual pos_type seekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parámetros

`_Off` La posición que realice una búsqueda para relativo a `_Way`.

`_Way` El punto de partida para desplazar las operaciones. Vea los valores posibles en [seekdir](../standard-library/ios-base-class.md#seekdir).

`_Which` Especifica el modo de la posición del puntero. El valor predeterminado es permitirle modificar las posiciones de lectura y escritura.

### <a name="return-value"></a>Valor devuelto

Devuelve la posición nueva o una posición de flujo no válida.

### <a name="remarks"></a>Comentarios

La función miembro virtual protegida trata de modificar las posiciones actuales de los flujos controlados. Para un objeto de clase [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, un objeto de tipo `fpos_t` puede representar una posición del flujo, que almacena un desplazamiento y cualquier información de estado que se necesite para analizar un flujo ancho. El desplazamiento cero designa el primer elemento del flujo. (Un objeto de tipo [pos_type](../standard-library/basic-streambuf-class.md#pos_type) almacena al menos un objeto `fpos_t`).

En el caso de un archivo abierto para lectura y escritura, los flujos de entrada y salida se colocan en tándem. Para cambiar entre inserción y extracción, debe llamar a [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) o [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos). Las llamadas a `pubseekoff` (y por tanto a `seekoff`) tienen varias limitaciones para [flujos de texto](../c-runtime-library/text-and-binary-streams.md), [flujos binarios](../c-runtime-library/text-and-binary-streams.md) y [flujos anchos](../c-runtime-library/byte-and-wide-streams.md).

Si el puntero de archivo **fp** es un puntero nulo, se produce un error al ejecutar la función. De lo contrario, intenta modificar la posición del flujo al llamar a `fseek`(**fp**, `_Off`, `_Way`). Si esa función se ejecuta correctamente y la posición resultante **fposn** se puede determinar mediante una llamada a `fgetpos` (**fp**, **&fposn**), la función se ejecuta correctamente. Si la función se ejecuta correctamente, devuelve un valor de tipo **pos_type** que contiene **fposn**. De lo contrario, devuelve una posición de flujo no válida.

## <a name="seekpos"></a>  basic_filebuf::seekpos

Intenta modificar las posiciones actuales de los flujos controlados.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parámetros

`_Sp` La posición que realice una búsqueda para.

`_Which` Especifica el modo de la posición del puntero. El valor predeterminado es permitirle modificar las posiciones de lectura y escritura.

### <a name="return-value"></a>Valor devuelto

Si el puntero de archivo **fp** es un puntero nulo, se produce un error al ejecutar la función. De lo contrario, intenta modificar la posición del flujo al llamar a `fsetpos`(**fp**, **&fposn**), donde **fposn** es el objeto `fpos_t` almacenado en `pos`. Si esa función se ejecuta correctamente, la función devuelve `pos`. De lo contrario, devuelve una posición de flujo no válida. Para determinar si la posición del flujo no es válida, compare el valor devuelto con `pos_type(off_type(-1))`.

### <a name="remarks"></a>Comentarios

La función miembro virtual protegida trata de modificar las posiciones actuales de los flujos controlados. Para un objeto de clase [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**>, un objeto de tipo `fpos_t` puede representar una posición del flujo, que almacena un desplazamiento y cualquier información de estado que se necesite para analizar un flujo ancho. El desplazamiento cero designa el primer elemento del flujo. (Un objeto de tipo `pos_type` almacena al menos un objeto `fpos_t`).

En el caso de un archivo abierto para lectura y escritura, los flujos de entrada y salida se colocan en tándem. Para cambiar entre inserción y extracción, debe llamar a [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) o [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos). Las llamadas a `pubseekoff` (y por tanto a `seekoff`) tienen varias limitaciones para flujos de texto, flujos binarios y flujos anchos.

En un flujo ancho, si se han producido inserciones desde la apertura del flujo o desde la última llamada a `streampos`, la función llama a [overflow](#overflow). Además se inserta cualquier secuencia necesaria para restaurar el estado de conversión inicial mediante la faceta de conversión de archivo **fac** para llamar a **fac**`.unshift` según sea necesario. Cada elemento **byte** de tipo `char` producido así se escribe en el flujo asociado designado por el puntero de archivo **fp** como si se hiciera mediante llamadas sucesivas del formato `fputc`(**byte**, **fp**). Si se produce un error en la llamada a **fac.unshift** o en cualquier escritura, la función no se ejecuta correctamente.

## <a name="setbuf"></a>  basic_filebuf::setbuf

Realiza una determinada operación para cada búfer de flujo derivado.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parámetros

`_Buffer` Puntero a un búfer.

`count` Tamaño del búfer.

### <a name="return-value"></a>Valor devuelto

La función miembro protegida devuelve cero si el puntero de archivo `fp` es un puntero nulo.

### <a name="remarks"></a>Comentarios

`setbuf` llama a `setvbuf`(**fp**, (`char` \*) `_Buffer`, `_IOFBF`, `count` \* `sizeof` (**Elem**)) para ofrecer la matriz de `count` elementos a partir de _ *Buffer* como búfer del flujo. Si esa función devuelve un valor distinto de cero, la función devuelve un puntero nulo. De lo contrario, devuelve **this** para señalar el éxito.

## <a name="swap"></a>  basic_filebuf::swap

Intercambia el contenido de este `basic_filebuf` por el contenido del `basic_filebuf` proporcionado.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parámetros

`right` Un `lvalue` referencia a otro `basic_filebuf`.

## <a name="sync"></a>  basic_filebuf::sync

Intenta sincronizar los flujos controlados con cualquier flujo externo asociado.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Valor devuelto

Devuelve cero si el puntero de archivo **fp** es un puntero nulo. De lo contrario, devuelve cero solo si las llamadas a [overflow](#overflow) y `fflush`(**fp**) logran vaciar todas las salidas pendientes en el flujo.

## <a name="traits_type"></a>  basic_filebuf::traits_type

Asocia un nombre de tipo al parámetro de plantilla **Tr**.

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a>  basic_filebuf::underflow

Extrae el elemento actual del flujo de entrada.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Valor devuelto

Si la función no se ejecuta correctamente, devuelve **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). De lo contrario, devuelve **ch**, convertido como se describe en la sección Comentarios.

### <a name="remarks"></a>Comentarios

La función miembro virtual protegida intenta extraer el elemento actual **ch** del flujo de entrada y devolver el elemento como **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(**ch**). Puede hacerlo de varias maneras:

- Si hay una posición de lectura disponible, toma **ch** como elemento almacenado en la posición de lectura y avanza el puntero siguiente del búfer de entrada.

- Puede leer uno o más elementos de tipo `char`, como por las llamadas sucesivas del formulario `fgetc`(**fp**) y convertirlos a un elemento **ch** de tipo **Elem**utilizando el /Fac de faceta de conversión de archivo para llamar a **fac.in** según sea necesario. Si se produce un error en cualquier conversión o lectura, la función no se ejecuta correctamente.

## <a name="see-also"></a>Vea también

[\<fstream>](../standard-library/fstream.md)<br/>
[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Programación con iostream](../standard-library/iostream-programming.md)<br/>
[Convenciones de iostreams](../standard-library/iostreams-conventions.md)<br/>
