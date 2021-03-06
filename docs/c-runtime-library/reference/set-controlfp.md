---
title: _set_controlfp | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_controlfp
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
- set_controlfp
- _set_controlfp
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2647e9719c2aa3fe303393fcc1da55de0385581
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="setcontrolfp"></a>_set_controlfp

Establece la palabra de control de punto flotante.

## <a name="syntax"></a>Sintaxis

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parámetros

*newControl*<br/>
Valores de bit de la nueva palabra de control.

*máscara*<br/>
Máscara de los bits de la nueva palabra de control que se va a definir.

## <a name="return-value"></a>Valor devuelto

Ninguno.

## <a name="remarks"></a>Comentarios

El **_set_controlfp** es similar a la función **_control87**, pero solo establece la palabra de control de punto flotante *newControl*. Los bits de los valores indican el estado de control de punto flotante. El estado de control de punto flotante permite que el programa cambie los modos de precisión, redondeo e infinito en el paquete matemático de punto flotante. También puede enmascarar o desenmascarar excepciones de punto flotante mediante **_set_controlfp**. Para obtener más información, vea [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md).

Esta función está en desuso cuando se compila con [/clr (compilación de Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) porque common language runtime solo admite la precisión de punto flotante predeterminada.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|Compatibilidad|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|Solo para procesadores x86|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Vea también

[Compatibilidad con el punto flotante](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
