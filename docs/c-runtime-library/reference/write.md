---
title: _write | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _write
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
apitype: DLLExport
f1_keywords:
- _write
dev_langs:
- C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f800c42480b6518c7482c15bfa18646b1988dc8a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="write"></a>_write

Escribe datos en un archivo.

## <a name="syntax"></a>Sintaxis

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parámetros

*FD*<br/>
Descriptor de archivo del archivo en el que se van a escribir datos.

*buffer*<br/>
Datos que se van a escribir.

*count*<br/>
Número de bytes.

## <a name="return-value"></a>Valor devuelto

Si se realiza correctamente, **_write** devuelve el número de bytes escritos realmente. Si el espacio real que queda en el disco es menor que el tamaño del búfer de la función está intentando escribir en el disco, **_write** se produce un error y no se vuelca ningún contenido del búfer en el disco. Un valor devuelto de -1 indica un error. Si se pasan parámetros no válidos, esta función invoca al controlador de parámetros no válidos, como se explica en [Validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, la función devuelve -1 y **errno** se establece en uno de estos tres valores: **EBADF**, lo que significa que el descriptor de archivo no es válido o el archivo no está abierto para escritura; **ENOSPC**, lo que significa que no hay suficiente espacio restante en el dispositivo para la operación; o **EINVAL**, lo que significa que *búfer* era un puntero nulo, o que un impar *recuento* de bytes que se pasó para escribirse en un archivo en modo Unicode.

Para obtener más información sobre estos y otros códigos de retorno, consulte [errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Si el archivo se abre en modo de texto, se reemplaza cada carácter de avance de línea con un retorno de carro - par de avance de línea en la salida. Este reemplazo no tiene efecto alguno en el valor devuelto.

Cuando se abre el archivo en el modo de traducción de Unicode, por ejemplo, si *fd* se abre mediante **_open** o **_sopen** y un parámetro de modo que incluya **_O_ WTEXT**, **_O_U16TEXT**, o **_O_U8TEXT**, o si se abre mediante **fopen** y un parámetro de modo que incluya **ccs = UNICODE**, **ccs = UTF-16LE**, o **ccs = UTF-8**, o si el modo se cambia a un modo de traducción de Unicode mediante el uso de **_setmode**:*búfer* se interpreta como un puntero a una matriz de **wchar_t** que contiene **UTF-16** datos. Si se intenta escribir un número impar de bytes en este modo, se producirá un error de validación de parámetros.

## <a name="remarks"></a>Comentarios

El **_write** función escrituras *recuento* bytes a partir de *búfer* en el archivo asociado a *fd*. La operación de escritura se inicia en la posición actual del puntero de archivo (si existe) asociado al archivo en cuestión. Si el archivo se abre para anexarlo, la operación comenzará en el final actual del archivo. Tras la operación de escritura, el puntero de archivo se incrementará según el número de bytes escrito realmente.

Al escribir en archivos abiertos en modo de texto, **_write** trata un carácter CTRL+Z como la relación final de archivo lógico. Cuando se escribe en un dispositivo, **_write** trata un carácter CTRL+Z en el búfer como un terminador de salida.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_write**|\<io.h>|

Para obtener información adicional sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occured
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>Vea también

[E/S de bajo nivel](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
