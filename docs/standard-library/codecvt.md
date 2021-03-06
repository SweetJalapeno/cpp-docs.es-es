---
title: '&lt;codecvt&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt
- <codecvt>
dev_langs:
- C++
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d4e07c4869bd345e77f0af4f30f694773aed114
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;

Define varias clases de plantilla que describen objetos en función de la clase de plantilla [codecvt](../standard-library/codecvt-class.md). Los objetos pueden actuar como [facetas de configuración regional](../standard-library/locale-class.md#facet_class) que controlan las conversiones entre una secuencia de valores de tipo `Elem` y una secuencia de valores de tipo `char`.

## <a name="syntax"></a>Sintaxis

```cpp
#include <codecvt>

```

## <a name="remarks"></a>Comentarios

Las facetas de configuración regional declaradas en este encabezado convierten entre varias codificaciones de caracteres. Para los caracteres anchos (almacenados en el programa en enteros de tamaño fijo):

- UCS-4 es la codificación Unicode (ISO 10646) dentro del programa como un entero de 32 bits.

- UCS-2 es la codificación Unicode dentro del programa como un entero de 16 bits.

- UCS-16 es la codificación Unicode dentro del programa como uno o dos enteros de 16 bits. (Tenga en cuenta que esto no cumple todos los requisitos de una codificación de caracteres anchos válida para el estándar de C o C++; no obstante, se usa ampliamente como tal).

Para los flujos de bytes (almacenados en un archivo, transmitidos como una secuencia de bytes o almacenados en el programa en una matriz de `char`):

- UTF-8 es la codificación Unicode en un flujo de bytes como uno o varios bytes de ocho bits con un orden de bytes deterministas.

- UTF-16LE es la codificación Unicode en un flujo de bytes como UTF-16 con cada entero de 16 bits presentado como dos bytes de ocho bits, el byte menos significativo en primer lugar.

- UTF-16BE es la codificación Unicode en un flujo de bytes como UTF-16 con cada entero de 16 bits presentado como dos bytes de ocho bits, el byte más significativo en primer lugar.

### <a name="enumerations"></a>Enumeraciones

|||
|-|-|
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|Especifica la información de configuración de las facetas de configuración regional.|

### <a name="classes"></a>Clases

|Clase|Descripción|
|-|-|
|[codecvt_utf8](codecvt-utf8-class.md)|Representa una faceta de configuración regional que convierte entre caracteres anchos codificados como UCS-2 o UCS-4 y un flujo de bytes codificados como UTF-8.|
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|Representa una faceta de configuración regional que convierte entre caracteres anchos codificados como UTF-16 y un flujo de bytes codificados como UTF-8.|
|[codecvt_utf16](codecvt-utf16-class.md)|Representa una faceta de configuración regional que convierte entre caracteres anchos codificados como UCS-2 o UCS-4 y un flujo de bytes codificados como UTF-16LE o UTF-16BE.|

## <a name="requirements"></a>Requisitos

**Encabezado:** \<codecvt >

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)<br/>
