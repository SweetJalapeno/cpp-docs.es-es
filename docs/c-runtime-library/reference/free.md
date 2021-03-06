---
title: free | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- free
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc6dfd832d18dbabc1ebc10aec252cc8afe15346
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="free"></a>free

Desasigna o libera un bloque de memoria.

## <a name="syntax"></a>Sintaxis

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Parámetros

*memblock* asignado previamente el bloque de memoria que se va a liberar.

## <a name="remarks"></a>Comentarios

El **libre** función desasigna un bloque de memoria (*memblock*) que se asignó previamente mediante una llamada a **calloc**, **malloc**, o **realloc**. El número de bytes liberados es equivalente al número de bytes solicitado si se asignó el bloque (o reasignado, en el caso de **realloc**). Si *memblock* es **NULL**, se omite el puntero y **libre** devuelve inmediatamente. Intentando liberar un puntero no válido (un puntero a un bloque de memoria que no se asignó por **calloc**, **malloc**, o **realloc**) pueden afectar a las solicitudes de asignación posteriores y producir errores.

Si se produce un error al liberar memoria, **errno** se configura con información del sistema operativo de la naturaleza del error. Para obtener más información, consulte [errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Una vez liberado un bloque de memoria, [_heapmin](heapmin.md) minimiza la cantidad de memoria libre en el montón al fusionar las regiones no usadas y liberarlas de nuevo en el sistema operativo. La memoria liberada que no se ha liberado en el sistema operativo se restaura en el grupo libre y vuelve a estar disponible para su asignación.

Cuando la aplicación se vincula con una versión de depuración de las bibliotecas de tiempo de ejecución de C, **libre** se resuelve como [_free_dbg](free-dbg.md). Para obtener más información sobre cómo se administra el montón durante el proceso de depuración, consulte [Detalles del montón de depuración de CRT](/visualstudio/debugger/crt-debug-heap-details).

**libre** está marcada como `__declspec(noalias)`, lo que significa que se garantiza que la función no se puede modificar las variables globales. Para obtener más información, consulte [noalias](../../cpp/noalias.md).

Para liberar la memoria asignada con [_malloca](malloca.md), use [_freea](freea.md).

## <a name="requirements"></a>Requisitos

|Función|Encabezado necesario|
|--------------|---------------------|
|**free**|\<stdlib.h> y \<malloc.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

Consulte el ejemplo de [malloc](malloc.md).

## <a name="see-also"></a>Vea también

[Asignación de memoria](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
