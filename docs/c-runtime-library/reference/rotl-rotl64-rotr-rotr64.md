---
title: _rotl, _rotl64, _rotr, _rotr64 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _rotr64
- _rotl
- _rotr
- _rotl64
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _rotr64
- rotl64
- _rotl64
- rotr64
- rotr
- _rotr
- _rotl
- rotl
dev_langs:
- C++
helpviewer_keywords:
- rotl64 function
- _rotl function
- rotr function
- rotr64 function
- _rotr function
- rotl function
- _rotl64 function
- rotating bits
- _rotr64 function
- bits, rotating
ms.assetid: cfce439b-366f-4584-8ab1-d527b13fcfc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4ec4844c54bef09522191be62599ed79b97eb6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="rotl-rotl64-rotr-rotr64"></a>_rotl, _rotl64, _rotr, _rotr64

Gira bits a la izquierda (**_rotl**) o a la derecha (**_rotr**).

## <a name="syntax"></a>Sintaxis

```C

unsigned int _rotl(
   unsigned int value,
   int shift
);
unsigned __int64 _rotl64(
   unsigned __int64 value,
   int shift
);
unsigned int _rotr(
   unsigned int value,
   int shift
);
unsigned __int64 _rotr64(
   unsigned __int64 value,
   int shift
);
```

### <a name="parameters"></a>Parámetros

*valor*<br/>
Valor que se va a girar.

*shift*<br/>
Número de bits que se van a desplazar.

## <a name="return-value"></a>Valor devuelto

El valor girado. No se devuelve ningún error.

## <a name="remarks"></a>Comentarios

El **_rotl** y **_rotr** funciones girar el sin signo *valor* por *MAYÚS* bits. **_rotl** gira el valor a la izquierda. **_rotr** gira a la derecha del valor. Ambas funciones ajustan los bits girados de un extremo de *value* al otro extremo.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_rotl**, **_rotl64**|\<stdlib.h>|
|**_rotr**, **_rotr64**|\<stdlib.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotecas

Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Ejemplo

```C
// crt_rot.c
/* This program shifts values to rotate an integer.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   unsigned val = 0x0fd93;
   __int64 val2 = 0x0101010101010101;

   printf( "0x%4.4x rotated left three times is 0x%4.4x\n",
           val, _rotl( val, 3 ) );
   printf( "0x%4.4x rotated right four times is 0x%4.4x\n",
           val, _rotr( val, 4 ) );

   printf( "%I64x rotated left three times is %I64x\n",
           val2, _rotl64( val2, 3 ) );
   printf( "%I64x rotated right four times is %I64x\n",
           val2, _rotr64( val2, 4 ) );
}
```

### <a name="output"></a>Salida

```Output
0xfd93 rotated left three times is 0x7ec98
0xfd93 rotated right four times is 0x30000fd9
101010101010101 rotated left three times is 808080808080808
101010101010101 rotated right four times is 1010101010101010
```

## <a name="see-also"></a>Vea también

[Compatibilidad con el punto flotante](../../c-runtime-library/floating-point-support.md)<br/>
[_lrotl, _lrotr](lrotl-lrotr.md)<br/>
