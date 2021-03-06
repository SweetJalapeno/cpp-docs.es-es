---
title: Crear archivos de encabezado precompilados | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- pch
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31d9708f203c3d79d4cf369583c75d348278d06a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="creating-precompiled-header-files"></a>Crear archivos de encabezado precompilados
  
Los compiladores de Microsoft C y C++ ofrecen opciones para precompilar cualquier código de C o C++, incluido el código en línea. Usar esta función de rendimiento le permite compilar un cuerpo estable de código, almacenar el estado compilado del código en un archivo y, en las posteriores compilaciones, combinar el código precompilado con código que aun se esté desarrollando. Cada compilación posterior se realizará más rápidamente porque no se tendrá que volver a compilar el código estable.  
  
En este tema se trata a los siguientes temas de encabezado precompilado:  
  
-   [Cuándo precompilar código fuente](#when-to-precompile-source-code)  
  
-   [Dos opciones para precompilar código](#two-choices-for-precompiling-code)  
  
-   [Reglas de coherencia del encabezado precompilado](#precompiled-header-consistency-rules)  
  
-   [Reglas de coherencia para el uso de encabezados precompilados por cada archivo](#consistency-rules-for-per-file-use-of-precompiled-headers)  
  
-   [Reglas de coherencia para /Yc e /Yu](#consistency-rules-for-yc-and-yu)  
  
-   [Usar encabezados precompilados en un proyecto](#using-precompiled-headers-in-a-project)  
  
-   [Archivos PCH en el proceso de compilación](#pch-files-in-the-build-process)  
  
-   [Ejemplo de archivo MAKE para PCH](#sample-makefile-for-pch)  
  
-   [Código de ejemplo para PCH](#example-code-for-pch)  
  
Para obtener información de referencia sobre las opciones del compilador relacionadas con encabezados precompilados, vea [/Y (encabezados precompilados)](../../build/reference/y-precompiled-headers.md).  
  
<a name="when-to-precompile-source-code"></a>  
  
## <a name="when-to-precompile-source-code"></a>Cuándo precompilar código fuente  
  
El código precompilado resulta útil durante el ciclo de desarrollo para reducir el tiempo de compilación, especialmente si:  
  
-   Utilice siempre una gran cantidad de código que cambia con poca frecuencia.  
  
-   El programa consta de varios módulos, todos los cuales utilizan un conjunto estándar de archivos de inclusión y las mismas opciones de compilación. En este caso, todos los archivos de inclusión pueden precompilarse en un encabezado precompilado.  
  
La primera compilación, lo que crea el archivo de encabezado precompilado (PCH): tarda un poco más que las compilaciones subsiguientes. Las compilaciones posteriores pueden continuar más rápidamente si se incluye el código precompilado.  
  
Puede precompilar programas C y C++. En programación de C++, es una práctica común para separar la información de la interfaz de clase en archivos de encabezado. Estos archivos de encabezado pueden incluirse posteriormente en programas que utilizan la clase. Mediante la precompilación de estos encabezados, puede reducir el tiempo que un programa necesario para compilar.  
  
> [!NOTE]
>  Aunque puede usar un único archivo de encabezado precompilado (.pch) por cada archivo de código fuente, puede utilizar varios archivos .pch en un proyecto.  
  
<a name="two-choices-for-precompiling-code"></a>  
  
# <a name="two-choices-for-precompiling-code"></a>Dos opciones para precompilar código  
  
Con Visual C++, puede precompilar cualquier código de C o C++; no se limita a precompilar solo los archivos de encabezado.  
  
La precompilación requiere planificación, pero proporciona compilaciones mucho más rápidas si precompilar código fuente que no sean archivos de encabezado sencillos.  
  
Precompilar código cuando sepa que los archivos de fuente usan conjuntos comunes de archivos de encabezado, pero no incluyen en el mismo orden, o cuando desee incluir código fuente en la precompilación.  
  
Las opciones de encabezado precompilado son [/Yc (crear archivo de encabezado precompilado)](../../build/reference/yc-create-precompiled-header-file.md) y [/Yu (utilizar el archivo de encabezado precompilado)](../../build/reference/yu-use-precompiled-header-file.md). Use **/Yc** para crear un encabezado precompilado. Cuando se usa con la parte opcional [hdrstop](../../preprocessor/hdrstop.md) pragma, **/Yc** permite precompilar tanto archivos de encabezado y código fuente. Seleccione **/Yu** para utilizar un encabezado precompilado existente en la compilación existente. También puede usar **/FP** con el **/Yc** y **/Yu** opciones para proporcionar un nombre alternativo para el encabezado precompilado.  
  
Los temas de referencia de la opción de compilador para **/Yu** y **/Yc** explican cómo obtener acceso a esta funcionalidad en el entorno de desarrollo.  
  
<a name="precompiled-header-consistency-rules"></a>  
  
## <a name="precompiled-header-consistency-rules"></a>Reglas de coherencia del encabezado precompilado  
  
Dado que PCH (archivos) contienen información sobre el entorno del equipo, así como información de dirección de memoria acerca del programa, solo se debe utilizar un archivo de encabezado Precompilado en el equipo donde se creó.  
  
<a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>  
  
## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Reglas de coherencia para el uso de encabezados precompilados por cada archivo

El [/Yu](../../build/reference/yu-use-precompiled-header-file.md) opción del compilador permite especificar qué archivo de encabezado Precompilado para utilizar.  
  
Cuando se usa un archivo de encabezado Precompilado, el compilador supone que el mismo entorno de compilación: uno que usa opciones coherentes del compilador, pragmas etc., que estaba en vigor cuando se creó el archivo de encabezado Precompilado, a menos que se especifique lo contrario. Si el compilador detecta una incoherencia, emite una advertencia e identifica la incoherencia siempre que sea posible. Tales advertencias no indican necesariamente un problema con el archivo PCH; simplemente avisan de posibles conflictos. Requisitos de coherencia para PCH (archivos) se describen en las secciones siguientes.  
  
### <a name="compiler-option-consistency"></a>Coherencia de la opción de compilador  
  
Las siguientes opciones del compilador pueden desencadenar una advertencia de incoherencia cuando se usa un archivo PCH:  
  
-   Las macros creadas con el preprocesador (/ d.) opción deben coincidir entre la compilación que creó el archivo de encabezado Precompilado y la compilación actual. No se comprueba el estado de constantes definidas, pero pueden producirse resultados imprevisibles si éstas cambian.  
  
-   PCH (archivos) no funcionan con las opciones /E y/EP.  
  
-   PCH (archivos) deben crearse con cualquier la generar información de exploración (/ FR) opción o excluir Variables locales (/ Fr) opción para las compilaciones subsiguientes que utilizan el archivo de encabezado Precompilado pueden usar estas opciones.  
  
### <a name="c-70-compatible-z7"></a>Compatible con 7.0 C (/ Z7)  
  
Si esta opción está activada cuando se crea el archivo de encabezado Precompilado, las compilaciones subsiguientes que utilizan el archivo de encabezado Precompilado pueden usar la información de depuración.  
  
Si el compatible con 7.0 de C (/ Z7) opción no está en vigor cuando se crea el archivo de encabezado Precompilado, las compilaciones subsiguientes que utilizan el archivo de encabezado Precompilado y/Z7 desencadenan una advertencia. La información de depuración se coloca en el archivo .obj actual, y los símbolos locales definidos en el archivo de encabezado Precompilado no están disponibles para el depurador.  
  
### <a name="include-path-consistency"></a>Incluir la coherencia de la ruta de acceso  
  
Un archivo PCH no contiene información acerca de la ruta de acceso de inclusión que estaba activa cuando se creó. Cuando se usa un archivo de encabezado Precompilado, el compilador siempre usa la ruta de acceso de inclusión especificada en la compilación actual.  
  
### <a name="source-file-consistency"></a>Coherencia del archivo de origen  
  
Cuando se especifica la opción de utilizar archivo de encabezado precompilado (/Yu), el compilador omite todas las directivas de preprocesador (incluidas las pragmas) que aparecen en el código fuente que se va a precompilar. La compilación especificada por esas directivas de preprocesador debe ser la misma que la compilación utilizada para la opción de crear encabezado precompilado (/Yc).  
  
### <a name="pragma-consistency"></a>Coherencia de pragma    
  
Las directivas pragma procesadas durante la creación de un archivo de encabezado Precompilado normalmente afectan al archivo con el que se utiliza posteriormente el archivo de encabezado Precompilado. El `comment` y `message` pragmas no afectan al resto de la compilación.  
  
Estas directivas pragma afectan únicamente al código en el archivo PCH; no afectan al código que posteriormente se utiliza el archivo de encabezado Precompilado:  
  
||||  
|-|-|-|  
|`comment`|`page`|`subtitle`|  
|`linesize`|`pagesize`|`title`|  
|`message`|`skip`||  
  
Estas directivas pragma se conservan como parte de un encabezado precompilado y afectan al resto de una compilación que utiliza el encabezado precompilado:  
  
||||  
|-|-|-|  
|`alloc_text`|`include_alias`|`pack`|  
|`auto_inline`|`init_seg`|`pointers_to_members`|  
|`check_stack`|`inline_depth`|`setlocale`|  
|`code_seg`|`inline_recursion`|`vtordisp`|  
|`data_seg`|`intrinsic`|`warning`|  
|`function`|`optimize`||  
  
<a name="consistency-rules-for-yc-and-yu"></a>  
  
## <a name="consistency-rules-for-yc-and-yu"></a>Reglas de coherencia para /Yc e /Yu  
  
Cuando se utiliza un encabezado precompilado creado mediante /Yc o/Yu, el compilador compara el entorno de compilación actual con el que existía cuando se creó el archivo de encabezado Precompilado. Asegúrese de especificar un entorno coherente con el anterior (mediante las opciones del compilador coherente, pragmas etc.) para la compilación actual. Si el compilador detecta una incoherencia, emite una advertencia e identifica la incoherencia siempre que sea posible. Tales advertencias no indican necesariamente un problema con el archivo PCH; simplemente avisan de posibles conflictos. Las siguientes secciones explican los requisitos de coherencia para encabezados precompilados.  
  
### <a name="compiler-option-consistency"></a>Coherencia de la opción de compilador  
  
Esta tabla enumera las opciones de compilador que pueden desencadenar una advertencia de incoherencia cuando se utiliza un encabezado precompilado:  
  
|Opción|nombre|Regla|  
|------------|----------|----------|  
|/D|Definir constantes y macros|Debe ser el mismo entre la compilación que creó el encabezado precompilado y la compilación actual. No se comprueba el estado de constantes definidas, pero pueden producirse resultados imprevisibles si los archivos dependen de los valores de las constantes que cambian.|  
|/E o /EP|Copia los resultados del preprocesador a resultados estándar|Los encabezados precompilados no funcionan con la opción /E o/EP.|  
|/FR o/fr|Generar información del explorador de código fuente de Microsoft|Para que las opciones /Fr y /FR sean válidas con la opción/Yu, debe también han tenido en vigor cuando se creó el encabezado precompilado. Compilaciones subsiguientes que utilizan el encabezado precompilado también generan información del explorador de origen. Información del explorador se coloca en un único archivo .sbr y otros archivos al que hace referencia en la misma manera que la información de CodeView. No se puede invalidar la ubicación de la información del explorador de origen.|  
|/ GA, /GD, /GE, /Gw o /GW|Opciones de protocolo de Windows|Debe ser el mismo entre la compilación que creó el encabezado precompilado y la compilación actual. Si las opciones difieren, se produce un mensaje de advertencia.|  
|/ZI|Generar información de depuración completa|Si esta opción está en vigor cuando se crea el encabezado precompilado, las compilaciones subsiguientes que utilizan la precompilación pueden utilizar esa información de depuración. Si /Zi no está en vigor cuando se crea el encabezado precompilado, las compilaciones subsiguientes que utilizan la precompilación y la opción/Zi desencadenan una advertencia. La información de depuración se coloca en el archivo de objeto actual y los símbolos locales definidos en el encabezado precompilado no están disponibles para el depurador.|  
  
> [!NOTE]
>  La funcionalidad de encabezado precompilado está pensada para su uso únicamente en los archivos de código fuente de C y C++.  
  
<a name="using-precompiled-headers-in-a-project"></a>  
  
## <a name="using-precompiled-headers-in-a-project"></a>Utilizar encabezados precompilados en un proyecto  
  
Las secciones anteriores presentan información general sobre los encabezados precompilados: /Yc y/Yu, la opción/Fp y el [hdrstop](../../preprocessor/hdrstop.md) pragma. En esta sección se describe un método para usar las opciones de encabezado precompilado manuales en un proyecto; termina con un archivo MAKE de ejemplo y el código que administra.  
  
Para ver otro enfoque para utilizar las opciones de encabezado precompilado manuales en un proyecto, estudie uno de los archivos MAKE ubicados en el directorio MFC\SRC que se crea durante la instalación predeterminada de Visual C++. Estos archivos MAKE adoptan un enfoque similar a la que se presentan en esta sección, pero hacer un uso mayor de macros de Microsoft programa mantenimiento Utility (NMAKE) y ofrecen un mayor control del proceso de compilación.  
  
<a name="pch-files-in-the-build-process"></a>  
  
## <a name="pch-files-in-the-build-process"></a>Archivos PCH en el proceso de compilación  
  
Normalmente se incluye la base de código de un proyecto de software en varios C o C++ archivos de código fuente, archivos objeto, bibliotecas y archivos de encabezado. Normalmente, un archivo MAKE que coordina la combinación de estos elementos en un archivo ejecutable. En la siguiente ilustración muestra la estructura de un archivo MAKE que utiliza un archivo de encabezado precompilado. Los nombres de macro NMAKE y los nombres de archivo en este diagrama están coherentes con la en el código de ejemplo se encuentra en [ejemplo de archivo MAKE para PCH](#sample-makefile-for-pch) y [código de ejemplo para PCH](#example-code-for-pch).  
  
En la ilustración utiliza tres dispositivos esquemáticas para mostrar el flujo del proceso de compilación. Rectángulos con nombre representan cada archivo o una macro; las tres macros representan uno o varios archivos. Las áreas sombreadas representan cada acción de compilación o un vínculo. Las flechas muestran qué archivos y macros se combinan durante la compilación o el proceso de vinculación.  
  
![Archivo MAKE que utiliza un archivo de encabezado precompilado](../../build/reference/media/vc30ow1.gif "estructura de un archivo MAKE que utiliza un archivo de encabezado precompilado")  
##### <a name="structure-of-a-makefile-that-uses-a-precompiled-header-file"></a>Estructura de un archivo MAKE que utiliza un archivo de encabezado precompilado  
  
Comenzando en la parte superior del diagrama, STABLEHDRS y BOUNDRY son macros NMAKE en el que se indican los archivos que probablemente no necesitan volver a compilar. Estos archivos se compilan con la cadena de comando  
  
`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`  
  
solo si el archivo de encabezado precompilado (STABLE.pch) no existe o si realiza cambios en los archivos enumerados en las dos macros. En cualquier caso, el archivo de encabezado precompilado contendrá código solo de los archivos enumerados en la macro STABLEHDRS. Indique el último archivo que desee precompilar en la macro de límite.  
  
Los archivos que se indican en estas macros pueden ser archivos de encabezado o archivos de código fuente de C o C++. (No se puede usar un único archivo de encabezado Precompilado con módulos de C y C++). Tenga en cuenta que puede usar el **hdrstop** macro para detener la precompilación en algún momento dentro del archivo de límite. Vea [hdrstop](../../preprocessor/hdrstop.md) para obtener más información.  
  
Continuar hacia abajo en el diagrama, APPLIB.obj representa el código auxiliar utilizado en la aplicación final. Se crea a partir de APPLIB.cpp, los archivos indicados en la macro UNSTABLEHDRS y el código precompilan de encabezado precompilado.  
  
MYAPP.obj representa la aplicación final. Se crea a partir de MYAPP.cpp, los archivos indicados en la macro UNSTABLEHDRS y el código precompilan de encabezado precompilado.  
  
Por último, el archivo ejecutable (MYAPP. (EXE) se crea vinculando los archivos indicados en la macro OBJS (APPLIB.obj y MYAPP.obj).  
  
<a name="sample-makefile-for-pch"></a>  
  
## <a name="sample-makefile-for-pch"></a>Ejemplo de archivo MAKE para PCH  
  
El siguiente archivo de MAKE utiliza macros y una! ¡IF! ¡ELSE! Estructura del comando de flujo de control ENDIF para simplificar su adaptación a su proyecto.  
  
```NMAKE  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
Además de las macros STABLEHDRS, BOUNDRY y UNSTABLEHDRS se muestra en la ilustración "Estructura de un archivo MAKE que utiliza un archivo de encabezado precompilado" en [archivos PCH en el proceso de compilación](#pch-files-in-the-build-process), este archivo MAKE incluye una macro CLFLAGS y una LINKFLAGS macro. Debe usar estas macros para mostrar las opciones del compilador y del vinculador que se aplican si se compila un versión final del archivo ejecutable de la aplicación o depuración. También hay una macro LIBS donde se indican las bibliotecas de su proyecto requiere.  
  
¡El archivo MAKE también utiliza! ¡IF! ¡ELSE! ENDIF para detectar si se define un símbolo DEBUG en la línea de comandos NMAKE:  
  
```NMAKE  
NMAKE DEBUG=[1|0]  
```  
  
Esta característica hace posible que puede usar el mismo archivo MAKE durante el desarrollo y para las versiones finales del programa, utilice DEBUG = 0 para las versiones finales. Las siguientes líneas de comandos son equivalentes:  
  
```NMAKE  
NMAKE   
NMAKE DEBUG=0  
```  
  
Para obtener más información sobre archivos MAKE, vea [referencia de NMAKE](../../build/nmake-reference.md). Consulte también [opciones del compilador](../../build/reference/compiler-options.md) y [opciones del vinculador](../../build/reference/linker-options.md).  
  
<a name="example-code-for-pch"></a>  
  
## <a name="example-code-for-pch"></a>Código de ejemplo para PCH  
  
Los siguientes archivos de origen se utilizan en el archivo MAKE descrito en [archivos PCH en el proceso de compilación](#pch-files-in-the-build-process) y [ejemplo de archivo MAKE para PCH](#sample-makefile-for-pch). Tenga en cuenta que los comentarios contienen información importante.  
  
```cpp  
// ANOTHER.H : Contains the interface to code that is not  
//             likely to change.  
//  
#ifndef __ANOTHER_H  
#define __ANOTHER_H  
#include<iostream>  
void savemoretime( void );  
#endif // __ANOTHER_H  
```  
  
```cpp  
// STABLE.H : Contains the interface to code that is not likely  
//            to change. List code that is likely to change   
//            in the makefile's STABLEHDRS macro.  
//  
#ifndef __STABLE_H  
#define __STABLE_H  
#include<iostream>  
void savetime( void );  
#endif // __STABLE_H  
```  
  
```cpp  
// UNSTABLE.H : Contains the interface to code that is  
//              likely to change. As the code in a header  
//              file becomes stable, remove the header file  
//              from the makefile's UNSTABLEHDR macro and list  
//              it in the STABLEHDRS macro.  
//  
#ifndef __UNSTABLE_H  
#define __UNSTABLE_H  
#include<iostream.h>  
void notstable( void );  
#endif // __UNSTABLE_H  
```  
  
```cpp
// APPLIB.CPP : This file contains the code that implements  
//              the interface code declared in the header  
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
// The following code represents code that is deemed stable and  
// not likely to change. The associated interface code is  
// precompiled. In this example, the header files STABLE.H and  
// ANOTHER.H are precompiled.  
void savetime( void )  
    { cout << "Why recompile stable code?\n"; }  
void savemoretime( void )  
    { cout << "Why, indeed?\n\n"; }  
// The following code represents code that is still under  
// development. The associated header file is not precompiled.  
void notstable( void )  
    { cout << "Unstable code requires"  
            << " frequent recompilation.\n"; 
    }  
```  
  
```cpp
// MYAPP.CPP : Sample application  
//             All precompiled code other than the file listed  
//             in the makefile's BOUNDRY macro (stable.h in  
//             this example) must be included before the file  
//             listed in the BOUNDRY macro. Unstable code must  
//             be included after the precompiled code.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
int main( void )  
{  
    savetime();  
    savemoretime();  
    notstable();  
}  
```  
    
## <a name="see-also"></a>Vea también  
[Referencia de compilación de C/C++](../../build/reference/c-cpp-building-reference.md)   
[Opciones del compilador](../../build/reference/compiler-options.md)