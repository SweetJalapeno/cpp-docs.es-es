---
title: _set_doserrno | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_doserrno
- set_doserrno
dev_langs:
- C++
helpviewer_keywords:
- _set_doserrno function
- doserrno global variable
- set_doserrno function
- _doserrno global variable
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb3a8e7503ae27177fded4ff240bbf5ec5a670e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="setdoserrno"></a>_set_doserrno

Establece el valor de la variable global [_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="syntax"></a>Sintaxis

```C
errno_t _set_doserrno( int error_value );
```

### <a name="parameters"></a>Parámetros

*error_value*<br/>
El nuevo valor de **_doserrno**.

## <a name="return-value"></a>Valor devuelto

Devuelve cero si es correcto.

## <a name="remarks"></a>Comentarios

Los valores posibles se definen en Errno.h.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|Encabezado opcional|
|-------------|---------------------|---------------------|
|**_set_doserrno**|\<stdlib.h>|\<errno.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Vea también

[_get_doserrno](get-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
