---
title: signal | Microsoft Docs
ms.custom: ''
ms.date: 04/12/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- signal
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
- signal
dev_langs:
- C++
helpviewer_keywords:
- signal function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a87978ec3b0840be6ab1779af86765208c80832c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="signal"></a>signal

Determina el control de señales de interrupción.

> [!IMPORTANT]
> No utilice este método para cerrar una aplicación de Microsoft Store, excepto en pruebas o en escenarios de depuración. No se permiten formas mediante programación o la interfaz de usuario para cerrar una aplicación de tienda según la [las directivas de Microsoft Store](http://go.microsoft.com/fwlink/?LinkId=865936). Para obtener más información, consulte [ciclo de vida de aplicación UWP](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Sintaxis

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>Parámetros

*sig*<br/>
Valor de la señal.

*Func*<br/>
El segundo parámetro es un puntero a la función que se ejecuta. El primer parámetro es un valor de señal y el segundo es un subcódigo que se puede usar cuando el primer parámetro es SIGFPE.

## <a name="return-value"></a>Valor devuelto

**señal** devuelve el valor anterior de func que esté asociada con la señal determinada. Por ejemplo, si el valor anterior de *func* era **SIG_IGN**, el valor devuelto también es **SIG_IGN**. Un valor devuelto de **SIG_ERR** indica un error; en ese caso, **errno** está establecido en **EINVAL**.

Vea [errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) para obtener más información sobre los códigos de retorno.

## <a name="remarks"></a>Comentarios

El **señal** función permite que un proceso elegir una de varias formas de controlar una señal de interrupción desde el sistema operativo. El *sig* argumento es la interrupción a la que **señal** responde; debe ser una de las constantes de manifiesto siguientes, que se definen en la señal. H.

|*SIG* valor|Descripción|
|-----------------|-----------------|
|**SIGABRT**|Terminación anómala|
|**SIGFPE**|Error de punto flotante|
|**SIGILL**|Instrucción no válida|
|**SIGINT**|Señal de CTRL+C|
|**SIGSEGV**|Acceso no válido a almacenamiento|
|**SIGTERM**|Solicitud de finalización|

Si *sig* no es uno de los valores anteriores, se invoca el controlador de parámetros no válidos, tal como se define en [validación de parámetros](../../c-runtime-library/parameter-validation.md) . Si la ejecución puede continuar, esta función establece **errno** a **EINVAL** y devuelve **SIG_ERR**.

De forma predeterminada, **señal** finaliza el programa que realiza la llamada con el código de salida 3, independientemente del valor de *sig*.

> [!NOTE]
> **SIGINT** no es compatible con cualquier aplicación de Win32. Cuando se produce una interrupción de CTRL+C, los sistemas operativos de Win32 generan un subproceso nuevo para controlar esa interrupción específicamente. Así se puede hacer que una aplicación de un único subproceso, por ejemplo una de UNIX, se convierta en aplicación multiproceso y provoque un comportamiento inesperado.

El *func* argumento es una dirección de un controlador de señal creado por usted o a una de las constantes predefinidas **SIG_DFL** o **SIG_IGN**, que también se definen en la señal. H. Si *func* es una función, se instala como controlador de señal para la señal determinada. Prototipo del controlador de señal requiere un argumento formal, *sig*, del tipo **int**. El sistema operativo proporciona el argumento real mediante *sig* cuando se produce una interrupción; el argumento es la señal que generó la interrupción. Por consiguiente, puede usar las seis constantes de manifiesto de la tabla anterior en el controlador de señal para determinar qué interrupción se produjo y tomar las medidas adecuadas. Por ejemplo, puede llamar a **señal** dos veces para asignar el mismo controlador a dos señales distintas y, a continuación, probar la *sig* argumento en el controlador para realizar acciones distintas en función de la señal recibida.

Si va a probar para excepciones de punto flotante (**SIGFPE**), *func* señala a una función que toma un segundo argumento opcional que es una de varias constantes de manifiesto, definidas en FLOAT. H, del formulario **FPE_xxx**. Cuando un **SIGFPE** señal se produce, puede probar el valor del segundo argumento para determinar el tipo de excepción de punto flotante y, a continuación, tome las medidas adecuadas. Este argumento y sus valores posibles son extensiones de Microsoft.

Para las excepciones de punto flotante, el valor de *func* no se restablece cuando se recibe la señal. Para recuperarse de excepciones de punto flotante, utilice cláusulas Try o Except para rodear las operaciones de punto flotante. También se puede recuperar usando [setjmp](setjmp.md) con [longjmp](longjmp.md). En cualquier caso, el proceso de llamada reanuda la ejecución y deja el estado de punto flotante del proceso sin definir.

Si vuelve el controlador de señal, el proceso de llamada reanuda la ejecución inmediatamente después del punto en el que recibió la señal de interrupción. Es así independientemente de la clase de señal o del modo de funcionamiento.

Antes de que se ejecuta la función especificada, el valor de *func* está establecido en **SIG_DFL**. La siguiente señal de interrupción se trata como se describe en **SIG_DFL**, a menos que una llamada intermedia a **señal** especifique otra cosa. Puede usar esta característica para restablecer señalas en la función a la que se llama.

Dado que se suele llamar a las rutinas de controlador de señal de forma asincrónica cuando se produce una interrupción, la función del controlador de señal puede hacerse con el control cuando una operación de tiempo de ejecución no está completa y está en un estado desconocido. En la lista siguiente se resumen las restricciones que determinan qué funciones se pueden usar en la rutina del controlador de señal.

- Realice el problema no bajo nivel o STDIO. Rutinas de E/S H (por ejemplo, **printf** o **fread**).

- No llame a rutinas del montón ni a ninguna rutina que usa las rutinas del montón (por ejemplo, **malloc**, **_strdup**, o **_putenv**). Vea [malloc](malloc.md) para obtener más información.

- No use ninguna función que genere una llamada del sistema (por ejemplo, **_getcwd** o **tiempo**).

- No utilice **longjmp** a menos que la interrupción sea consecuencia de una excepción de punto flotante (es decir, *sig* es **SIGFPE**). En este caso, reinicialice primero el paquete de punto flotante con una llamada a **_fpreset**.

- No use ninguna rutina superpuesta.

Un programa debe contener código de punto flotante para interceptar la **SIGFPE** excepción mediante la función. Si el programa no tiene código de punto flotante y requiere el código de control de señal de la biblioteca en tiempo de ejecución, simplemente declare un doble volátil e inicialícelo en cero:

```C
volatile double d = 0.0f;
```

El **SIGILL** y **SIGTERM** señales no se generan en Windows. Se incluyen para razones de compatibilidad con ANSI. Por lo tanto, puede establecer controladores de señal para estas señales mediante **señal**, y puede generar estas señales explícitamente mediante una llamada a [generar](raise.md).

Configuraciones de las señales no se conservan en los procesos que se crean mediante llamadas a [_exec](../../c-runtime-library/exec-wexec-functions.md) o [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) funciones. Las configuraciones de las señales se restablecen a los valores predeterminados en el proceso nuevo.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**signal**|\<signal.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar **señal** para agregar comportamiento personalizado a la **SIGABRT** señal. Para obtener más información sobre el comportamiento de anulación, vea [_set_abort_behavior](set-abort-behavior.md).

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Vea también

[Control de proceso y de entorno](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[_exec, _wexec (funciones)](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_fpreset](fpreset.md)<br/>
[_spawn, _wspawn (funciones)](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
