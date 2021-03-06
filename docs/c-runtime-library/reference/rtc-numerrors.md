---
title: _RTC_NumErrors | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af223e1e2d183f5357cf1d1bac96aabb042a99da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="rtcnumerrors"></a>_RTC_NumErrors

Devuelve el número total de errores que se pueden detectar mediante las comprobaciones de errores en tiempo de ejecución (RTC). Puede usar este número como control de un bucle **for**, donde cada valor del bucle se pasa a [_RTC_GetErrDesc](rtc-geterrdesc.md).

## <a name="syntax"></a>Sintaxis

```C

int _RTC_NumErrors( void );

```

## <a name="return-value"></a>Valor devuelto

Un entero cuyo valor representa el número total de errores que se pueden detectar mediante las comprobaciones de errores en tiempo de ejecución de Visual C++.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_RTC_NumErrors**|\<rtcapi.h>|

Para obtener más información, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotecas

Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Vea también

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Comprobar errores en tiempo de ejecución](../../c-runtime-library/run-time-error-checking.md)<br/>
