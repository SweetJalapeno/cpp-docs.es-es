---
title: '&lt;ios&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <ios>
- ios/std::<ios>
dev_langs:
- C++
helpviewer_keywords:
- ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e7ae83cd92ac8441d842e704446d519f57d4f65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="ltiosgt"></a>&lt;ios&gt;

Define varios tipos y funciones básicos para el funcionamiento de iostreams. Este encabezado se suele incluir automáticamente mediante otro encabezado de iostreams; rara vez se incluye directamente.

## <a name="syntax"></a>Sintaxis

```cpp
#include <ios>

```

## <a name="remarks"></a>Comentarios

Un grupo grande de funciones son los manipuladores. Un manipulador declarado en \<ios> modifica los valores almacenados en su objeto de argumento de la clase [ios_base](../standard-library/ios-base-class.md). Otros manipuladores realizan acciones en flujos controlados por objetos de un tipo derivado de esta clase, tales como una especialización de una de las clases de plantilla [basic_istream](../standard-library/basic-istream-class.md) o [basic_ostream](../standard-library/basic-ostream-class.md). Por ejemplo, [noskipws](../standard-library/ios-functions.md#noskipws)(**str**) borra la marca de formato `ios_base::skipws` en el objeto **str**, que puede ser de uno de estos tipos.

También puede llamar a un manipulador insertándolo en un flujo de salida o extrayéndolo de un flujo de entrada, gracias a las operaciones especiales de inserción y extracción proporcionadas para las clases derivadas de `ios_base`. Por ejemplo:

```cpp
istr>> noskipws;
```

llama a [noskipws](../standard-library/ios-functions.md#noskipws)(**istr**).

### <a name="typedefs"></a>Typedefs

|Nombre de tipo|Descripción|
|-|-|
|[ios](../standard-library/ios-typedefs.md#ios)|Es compatible con la clase ios de la antigua biblioteca iostream.|
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|Admite operaciones internas.|
|[streampos](../standard-library/ios-typedefs.md#streampos)|Contiene la posición actual del puntero de búfer o el puntero de archivo.|
|[streamsize](../standard-library/ios-typedefs.md#streamsize)|Especifica el tamaño del flujo.|
|[wios](../standard-library/ios-typedefs.md#wios)|Es compatible con la clase wios de la antigua biblioteca iostream.|
|[wstreampos](../standard-library/ios-typedefs.md#wstreampos)|Contiene la posición actual del puntero de búfer o el puntero de archivo.|

### <a name="manipulators"></a>Manipuladores

|||
|-|-|
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|Especifica que las variables de tipo [bool](../cpp/bool-cpp.md) aparezcan como **True** o **False** en el flujo.|
|[dec](../standard-library/ios-functions.md#dec)|Especifica que las variables de entero aparezcan en notación de base 10.|
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|Configura los indicadores de un objeto `ios_base` para que utilicen un formato de presentación predeterminado para valores float.|
|[fixed](../standard-library/ios-functions.md#fixed)|Especifica que un número de punto flotante se muestre en notación de decimal fijo.|
|[hex](../standard-library/ios-functions.md#hex)|Especifica que las variables de entero aparezcan en notación de base 16.|
|[internal](../standard-library/ios-functions.md#internal)|Hace que el signo de un número esté justificado a la izquierda y el número se alinee a la derecha.|
|[left](../standard-library/ios-functions.md#left)|Hace que el texto con un ancho menor que el ancho de salida aparezca en el vaciado de flujo con el margen izquierdo.|
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|Especifica que las variables de tipo [bool](../cpp/bool-cpp.md) aparezcan como 1 o 0 en el flujo.|
|[noshowbase](../standard-library/ios-functions.md#noshowbase)|Desactiva la opción que indica la base notacional en que se muestra un número.|
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|Muestra solo la parte de número entero en los números de punto flotante cuya parte fraccionaria es cero.|
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|Hace que los números positivos no tengan signo explícito.|
|[noskipws](../standard-library/ios-functions.md#noskipws)|Hace que el flujo de entrada lea los espacios.|
|[nounitbuf](../standard-library/ios-functions.md#nounitbuf)|Hace que la salida se almacene en búfer y se procese cuando el búfer esté lleno.|
|[nouppercase](../standard-library/ios-functions.md#nouppercase)|Especifica que los dígitos hexadecimales y el exponente en notación científica aparezcan en minúscula.|
|[oct](../standard-library/ios-functions.md#oct)|Especifica que las variables de entero aparezcan en notación de base 8.|
|[right](../standard-library/ios-functions.md#right)|Hace que el texto con un ancho menor que el ancho de salida aparezca en el vaciado de flujo con el margen derecho.|
|[scientific](../standard-library/ios-functions.md#scientific)|Hace que los números de punto flotante se muestren con notación científica.|
|[showbase](../standard-library/ios-functions.md#showbase)|Indica la base notacional en que se muestra un número.|
|[showpoint](../standard-library/ios-functions.md#showpoint)|Muestra la parte de número entero de un número de punto flotante y los dígitos que hay a la derecha del separador decimal, incluso cuando la parte fraccionaria es cero.|
|[showpos](../standard-library/ios-functions.md#showpos)|Hace que los números positivos tengan signo explícito.|
|[skipws](../standard-library/ios-functions.md#skipws)|Hace que el flujo de entrada no lea los espacios.|
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|Hace que la salida se procese cuando el búfer no está lleno.|
|[uppercase](../standard-library/ios-functions.md#uppercase)|Especifica que los dígitos hexadecimales y el exponente en notación científica aparezcan en mayúscula.|

### <a name="classes"></a>Clases

|Clase|Descripción|
|-|-|
|[basic_ios](../standard-library/basic-ios-class.md)|La clase de plantilla describe las funciones de almacenamiento y miembro comunes tanto a los flujos de entrada (de la clase de plantilla [basic_istream](../standard-library/basic-istream-class.md)) como a los de salida (de la clase de plantilla [basic_ostream](../standard-library/basic-ostream-class.md)) que dependen de los parámetros de plantilla.|
|[fpos](../standard-library/fpos-class.md)|La clase de plantilla describe un objeto que puede almacenar toda la información necesaria para restaurar un indicador de posición de archivo arbitraria en cualquier flujo.|
|[ios_base](../standard-library/ios-base-class.md)|La clase describe las funciones de almacenamiento y miembro comunes al flujo de entrada y al de salida que no dependen de los parámetros de plantilla.|

## <a name="see-also"></a>Vea también

[Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)<br/>
[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Programación con iostream](../standard-library/iostream-programming.md)<br/>
[Convenciones de iostreams](../standard-library/iostreams-conventions.md)<br/>
