---
title: Crear un nuevo proyecto de C++ para Linux en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2017
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 4d4d11ec459215d81996d1daea420513c21b10b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="create-a-new-linux-project"></a>Crear un nuevo proyecto de Linux
Al codificar para Linux, tiene la opción de crear un proyecto de Visual Studio o un proyecto de CMake. En este tema se describe cómo crear un proyecto de Visual Studio. Para obtener información acerca de los proyectos de CMake, consulte [Configurar un proyecto de CMake de Linux](cmake-linux-project.md).

Para crear un nuevo proyecto de Linux en Visual Studio, haga lo siguiente:

1. Seleccione **Archivo > Nuevo proyecto** en Visual Studio o pulse **Ctrl + Mayús + N**.
1. Seleccione el nodo **Visual C++ > Multiplataforma > Linux** y, luego, seleccione el tipo de proyecto que le gustaría crear, escriba un nombre o ubicación y haga clic en Aceptar.

   ![Nuevo proyecto de Linux](media/newproject.png)

   | Tipo de proyecto | Description
   | ------------ | ---
   | **Blink (Raspberry)**           | Proyecto destinado a un dispositivo Raspberry Pi con código de ejemplo escrito para hacer parpadear un LED
   | **Aplicación de consola (Linux)** | Proyecto destinado a cualquier equipo Linux con código de ejemplo escrito para mostrar texto en la consola
   | **Proyecto vacío (Linux)**       | Proyecto destinado a cualquier equipo Linux sin código de ejemplo escrito
   | **Proyecto de archivos MAKE (Linux)**    | Proyecto destinado a cualquier equipo Linux que se compilará con un sistema de compilación estándar de archivos Make

