---
title: 'Tutorial: Compilar un C++ / CLI programa en la línea de comandos | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81e5b8119c8921da28c6ad93b257234e0998083a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>Tutorial: Compilar un programa de C++/CLI en la línea de comandos
Puede crear programas de Visual C++ destinados a Common Language Runtime (CLR) que usen .NET Framework y compilarlos en la línea de comandos. Visual C++ admite el lenguaje de programación C++/CLI, con tipos y operadores adicionales para tener como destino el modelo de programación .NET. Para obtener una introducción a C++ / lenguaje CLI, consulte [puro C++: Hola, C++ / CLI](http://msdn.microsoft.com/magazine/cc163681.aspx). Para obtener información general, vea [programación de .NET con C++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 En este tutorial, utilizará un editor de texto para crear un programa básico de C++/CLI y, luego, lo compilará en la línea de comandos. (Puede usar su propio programa de C++/CLI en lugar de escribir el que se muestra, o usar un código de ejemplo de C++/CLI de otro artículo de ayuda. Esta técnica es útil para compilar y probar módulos pequeños que no contienen ningún elemento de IU).  
  
> [!NOTE]
>  También puede usar el IDE de Visual Studio para compilar programas de C++/CLI. Para obtener más información, consulte [Tutorial: compilar un programa de C++ orientado a CLR en Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe entender los principios del lenguaje C++.  
  
## <a name="compiling-a-ccli-program"></a>Compilación de un programa de C++/CLI  
 En los pasos siguientes, se muestra cómo compilar una aplicación de consola de C++/CLI que utiliza clases de .NET Framework.  
  
 Para habilitar la compilación de C++ / CLI, debe usar el [/CLR](../build/reference/clr-common-language-runtime-compilation.md) opción del compilador. El compilador de Visual C++ genera un archivo .exe que contiene código MSIL (o código nativo y MSIL combinado) y que vincula a las bibliotecas .NET Framework necesarias.  
  
#### <a name="to-compile-a-ccli-application-on-the-command-line"></a>Para compilar una aplicación de C++/CLI en la línea de comandos  
  
1.  Abra un **símbolo** ventana. Para obtener instrucciones específicas, consulte [para abrir una ventana de símbolo del sistema para desarrolladores](../build/building-on-the-command-line.md#developer_command_prompt).  
  
     Puede que se requieran credenciales de administrador para compilar el código correctamente,en función del sistema operativo y de la configuración del equipo. Para ejecutar la ventana de símbolo del sistema como administrador, haga clic en para abrir el menú contextual de la línea de comandos y, a continuación, elija **más**, **ejecutar como administrador**.  
  
2.  En el símbolo del sistema, escriba **basicclr.cpp el Bloc de notas**.  
  
     Elija **Sí** cuando le pedirá que cree un archivo.  
  
3.  En el Bloc de notas, escriba estas líneas:  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  En la barra de menús, elija **archivo**, **guardar**.  
  
     Ha creado un archivo de código fuente de Visual C++ que utiliza una clase .NET Framework (<xref:System.Console>) en el espacio de nombres <xref:System>.  
  
5.  En el símbolo del sistema, escriba **cl /clr basicclr.cpp**. El compilador cl.exe compila el código fuente en un archivo .obj que contiene código MSIL y, después, ejecuta el enlazador para generar un programa ejecutable llamado basicclr.exe.  
  
6.  Para ejecutar el programa basicclr.exe, en el símbolo del sistema, escriba **basicclr**.  
  
     El programa mostrará este texto y se cerrará:  
  
    ```Output  
    This is a C++/CLI program.  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Referencia del lenguaje C++](../cpp/cpp-language-reference.md)   
 [Compilación de programas de C/C++](../build/building-c-cpp-programs.md)   
 [Opciones del compilador](../build/reference/compiler-options.md)