---
title: Editor de cadena | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string.F1
dev_langs:
- C++
helpviewer_keywords:
- String editor
- string tables
- string tables, String editor
- string editing
- string editing, string tables
- resource editors, String editor
- strings [C++], editing
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23211293313135cb0341ac234014ae3c144b7fec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="string-editor"></a>Editor de cadenas
Una tabla de cadenas es un recurso de Windows que contiene una lista de id., valores y títulos para todas las cadenas de su aplicación. Por ejemplo, los mensajes de la barra de estado se encuentran en la tabla de cadenas.  
  
 Al desarrollar una aplicación, puede tener varias tablas de cadenas: una para cada idioma o condición. Sin embargo, un módulo ejecutable solo tiene una tabla de cadenas. Una aplicación en ejecución puede hacer referencia a varias tablas de cadenas si coloca las tablas en varias DLL diferentes.  
  
 Las tablas de cadenas facilitan la localización de la aplicación en diferentes idiomas. Si todas las cadenas se encuentran en una tabla de cadenas, puede localizar la aplicación mediante la traducción de las cadenas (y otros recursos) sin cambiar el código fuente. Esto suele ser más deseable que buscar y reemplazar manualmente las distintas cadenas en archivos de código fuente.  
  
 Con el editor de cadenas, puede:  
  
-   [Buscar una o más cadenas](../windows/finding-a-string.md).  
  
-   [Insertar entradas nuevas](../windows/adding-or-deleting-a-string.md) rápidamente en la tabla de cadenas.  
  
-   [Mover una cadena de un archivo de recursos a otro](../windows/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [Usar la edición en contexto para las propiedades ID, Value y Caption](../windows/changing-the-properties-of-a-string.md) y ver los cambios inmediatamente.  
  
-   [Cambiar la propiedad caption de varias cadenas](../windows/changing-the-caption-property-of-multiple-strings.md)  
  
-   [Agregar formato o caracteres especiales a una cadena](../windows/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows no permite la creación de tablas de cadenas vacías. Si crea una tabla de cadenas sin entradas, se elimina automáticamente al guardar el archivo de recursos.  
  
 Para obtener información sobre cómo agregar recursos a proyectos administrados (aquellos que tienen como destino common language runtime), vea [recursos en aplicaciones de escritorio](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework.* . Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, obtener acceso a recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [Tutorial: adaptar Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) y [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="requirements"></a>Requisitos  
 Win32  
  
## <a name="see-also"></a>Vea también  
 [Editores de recursos](../windows/resource-editors.md)   
 [Cadenas](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [Acerca de las cadenas](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)

