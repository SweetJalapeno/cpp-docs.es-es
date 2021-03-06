---
title: Referencia del lenguaje de Visual C++ (C++ / CX) | Documentos de Microsoft
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b251a89eee456905fae1e2096a74362fc6c44ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-language-reference-ccx"></a>Referencia del lenguaje Visual C++ (C++/CX)

C++ / CX es un conjunto de extensiones del lenguaje C++ que permite la creación de aplicaciones de Windows y componentes de Windows Runtime en una locución que sea lo más parecida posible a moderna de C++. Utilizar C++ / CX para escribir aplicaciones de Windows y componentes en código nativo que interactúen fácilmente con Visual C#, Visual Basic y JavaScript y otros lenguajes que admitan el tiempo de ejecución de Windows. En los pocos casos que requieren acceso directo a las interfaces COM sin procesar, o a código no excepcional, puede usar el [biblioteca de plantillas de C++ (WRL) de Windows en tiempo de ejecución](../windows/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> C++ / WinRT es una nueva, el estándar C ++ 17 lenguaje proyección para Windows Runtime APIs. Está disponible en Windows 10 SDK más reciente de la versión 1803 en adelante. C++ / WinRT se implementa por completo en archivos de encabezado y diseñado para proporcionarle acceso de primera clase a la API de Windows modernas.

> Con C++ / WinRT, se puede utilizar y crear mediante cualquier compilador de 17 C ++ compatible con los estándares de Windows en tiempo de ejecución APIs. C++ / WinRT normalmente se comporta mejor y genera archivos binarios más pequeños que cualquier otra opción de idioma para el tiempo de ejecución de Windows. Se seguirá siendo compatible con C++ / CX y WRL, pero se recomienda encarecidamente que las nuevas aplicaciones utilizar C++ / WinRT. Para obtener más información, consulte [C++ / WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).


Mediante el uso de C++ / CX, puede crear:

- Aplicaciones de plataforma Universal de Windows (UWP) de C++ que usan XAML para definir el usuario de la interfaz y la pila nativa. Para obtener más información, consulte [crear una aplicación "hello world" en C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- Componentes de tiempo de ejecución de Windows de C++ que pueden utilizarse en aplicaciones de Windows basadas en JavaScript. Para obtener más información, consulte [crear componentes de Windows en tiempo de ejecución en C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Aplicaciones con numerosos gráficos y juegos DirectX de Windows. Para obtener más información, consulte [crear un juego de UWP simple con DirectX](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game).

## <a name="related-articles"></a>Artículos relacionados

|||
|-|-|
|[Referencia rápida](../cppcx/quick-reference-c-cx.md)|Tabla de palabras clave y operadores de C++ / CX.|
|[Sistema de tipos](../cppcx/type-system-c-cx.md)|Describe básico de C++ / CX tipos y construcciones de programación y cómo utilizar C++ / CX para utilizar y crear tipos en tiempo de ejecución de Windows.|
|[Compilar aplicaciones y bibliotecas](../cppcx/building-apps-and-libraries-c-cx.md)|Explica cómo utilizar el IDE para compilar aplicaciones y vincular a bibliotecas estáticas y archivos DLL.|
|[Interoperar con otros lenguajes](../cppcx/interoperating-with-other-languages-c-cx.md)|Describe cómo los componentes que se escriben con C++ / CX puede utilizarse con componentes que se escriben en JavaScript, cualquier lenguaje administrado o la [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)].|
|[Subprocesamiento y cálculo de referencias](../cppcx/threading-and-marshaling-c-cx.md)|Describe cómo especificar el comportamiento de subprocesamiento y cálculo de referencias de los componentes que crees.|
|[Referencia de espacios de nombres](../cppcx/namespaces-reference-c-cx.md)|Hace referencia a documentación para el espacio de nombres predeterminado, el espacio de nombres Platform, Platform::Collections y los espacios de nombres relacionados.|
|[Funciones de CRT no admitidas en aplicaciones de la Plataforma universal de Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Enumera las funciones de CRT que no se pueden usar en aplicaciones de Windows Runtime.|
|[Guías de procedimientos para las aplicaciones de Windows 10](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Proporcionan orientación de alto nivel sobre las aplicaciones de Windows 10 y vínculos a más información.|
|[C++ / CX parte 0 de \[n\]: Introducción](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C++ / CX parte 1 de \[n\]: una clase Simple](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++ / CX parte 2 de \[n\]: tipos que usan sombreros](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++ / CX parte 3 de \[n\]: en construcción](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C++ / CX parte 4 de \[n\]: las funciones miembro estáticas](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Una serie de blogs de Visual C++ introductoria en C++ / CX.|
