---
title: remove, _wremove | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wremove
- remove
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- remove
- _wremove
- _tremove
dev_langs:
- C++
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36cdc09107a66067b358cb2fd72ec9bd1b2b30a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="remove-wremove"></a>remove, _wremove

Elimina un archivo.

## <a name="syntax"></a>Sintaxis

```C
int remove(
   const char *path
);
int _wremove(
   const wchar_t *path
);
```

### <a name="parameters"></a>Parámetros

*path*<br/>
Ruta de acceso del archivo que se va a quitar.

## <a name="return-value"></a>Valor devuelto

Cada una de estas funciones devuelve 0 si el archivo se elimina correctamente. En caso contrario, devuelve -1 y establece **errno** a **EACCES** para indicar que la ruta de acceso especifica un archivo de solo lectura o el archivo está abierto, o a **ENOENT** para indicar que el no se encontró el nombre de archivo o ruta de acceso o que la ruta de acceso especifica un directorio.

Vea [_doserrno, errno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) para obtener más información sobre estos y otros códigos de retorno.

## <a name="remarks"></a>Comentarios

La función **remove** elimina el archivo especificado por *path*. **_wremove** es una versión con caracteres anchos de **_Eliminar**; el *ruta de acceso* argumento pasado a **_wremove** es una cadena de caracteres anchos. **_wremove** y **_Eliminar** se comportan exactamente igual. Para poder eliminar un archivo, primero se deben cerrar todos los controladores correspondientes.

### <a name="generic-text-routine-mappings"></a>Asignaciones de rutina de texto genérico

|Rutina TCHAR.H|_UNICODE y _MBCS no definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**remove**|\<stdio.h> o \<io.h>|
|**_wremove**|\<stdio.h> o \<wchar.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotecas

Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Ejemplo

```C
// crt_remove.c
/* This program uses remove to delete crt_remove.txt */

#include <stdio.h>

int main( void )
{
   if( remove( "crt_remove.txt" ) == -1 )
      perror( "Could not delete 'CRT_REMOVE.TXT'" );
   else
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );
}
```

### <a name="input-crtremovetxt"></a>Entrada: crt_remove.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Resultados del ejemplo

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>Vea también

[Control de archivos](../../c-runtime-library/file-handling.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
