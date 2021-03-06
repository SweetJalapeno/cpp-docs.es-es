---
title: TypeDef, Enum, Union y Struct (atributos) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c14881afd000dc5fb4223a2ecfa9dcdc67e7b541
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union y Struct (Atributos)
Los siguientes atributos se aplican a la [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [struct](../cpp/struct-cpp.md), y [enum](../cpp/enumerations-cpp.md) palabras clave de C++.  
  
### <a name="typedef"></a>typedef  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|Usar con el [switch_type](../windows/switch-type.md) de atributo en un **union**.|  
|[Personalizada](../windows/custom-cpp.md)|Le permite definir su propio atributo.|  
|[export](../windows/export.md)|Hace que una estructura de datos que se colocarán en el archivo IDL.|  
|[first_is](../windows/first-is.md)|Especifica el índice del primer elemento de matriz que se transmitan.|  
|[helpcontext](../windows/helpcontext.md)|Especifica un identificador de contexto que permite al usuario ver información acerca de este elemento en el archivo de ayuda.|  
|[helpfile](../windows/helpfile.md)|Establece el nombre del archivo de ayuda para una biblioteca de tipos.|  
|[helpstring](../windows/helpstring.md)|Especifica una cadena de caracteres que se utiliza para describir el elemento al que se aplica.|  
|[library_block](../windows/library-block.md)|Coloca una construcción en bloque de biblioteca del archivo .idl.|  
|[ptr](../windows/ptr.md)|Designa un puntero como un puntero completo.|  
|[public](../windows/public-cpp-attributes.md)|Garantiza que una definición de tipo pasará a la biblioteca de tipos aunque no se hace referencia desde dentro del archivo .idl.|  
|[ref](../windows/ref-cpp.md)|Identifica un puntero de referencia.|  
|[switch_is](../windows/switch-is.md)|Especifica la expresión o el identificador que actúa como la unión discriminante que selecciona al miembro de unión.|  
|[switch_type](../windows/switch-type.md)|Identifica el tipo de la variable utilizada como la unión discriminante.|  
|[unique](../windows/unique-cpp.md)|Especifica un puntero único.|  
|[wire_marshal](../windows/wire-marshal.md)|Especifica un tipo de datos que se usará para la transmisión en lugar de un tipo de datos específicos de la aplicación.|  
  
### <a name="enum"></a>enum  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[Personalizada](../windows/custom-cpp.md)|Le permite definir su propio atributo.|  
|[export](../windows/export.md)|Hace que una estructura de datos que se colocarán en el archivo IDL.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Especifica el identificador único para una clase o interfaz.|  
|[v1_enum](../windows/v1-enum.md)|Indica que el tipo enumerado especificado se transmiten como una entidad de 32 bits, en lugar de con el valor predeterminado de 16 bits.|  
  
### <a name="union"></a>union  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[Personalizada](../windows/custom-cpp.md)|Le permite definir su propio atributo.|  
|[export](../windows/export.md)|Hace que una estructura de datos que se colocarán en el archivo IDL.|  
|[first_is](../windows/first-is.md)|Especifica el índice del primer elemento de matriz que se transmitan.|  
|[last_is](../windows/last-is.md)|Especifica el índice del último elemento de matriz que se transmitan.|  
|[length_is](../windows/length-is.md)|Especifica el número de elementos de la matriz que se transmitan.|  
|[max_is](../windows/max-is.md)|Designa el valor máximo para un índice de matriz válida.|  
|[size_is](../windows/size-is.md)|Especifica el tamaño de memoria asignada para los punteros de tamaño, tamaño de punteros a punteros de tamaño y solo o matrices multidimensionales.|  
|[unique](../windows/unique-cpp.md)|Especifica un puntero único.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Especifica el identificador único para una clase o interfaz.|  
  
### <a name="nonencapsulated-union"></a>Unión nonencapsulated  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Controla la alineación de representación de datos de red de uniones nonencapsulated.|  
|[no_injected_text](../windows/no-injected-text.md)|Evita que el compilador inserte código como resultado del uso de atributos.|  
  
### <a name="struct"></a>struct  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|Indica que la clase compatible con la agregación.|  
|[aggregates](../windows/aggregates.md)|Indica que un control agrega la clase de destino.|  
|[appobject](../windows/appobject.md)|Identifica la coclase como un objeto de aplicación, que está asociado a una aplicación .exe completa y se indican que las funciones y propiedades de la coclase que están disponibles globalmente en esta biblioteca de tipos.|  
|[coclass](../windows/coclass.md)|Crea un control ActiveX.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Agrega una entrada de la interfaz a un mapa COM.|  
|[control](../windows/control.md)|Especifica que el tipo definido por el usuario es un control.|  
|[Personalizada](../windows/custom-cpp.md)|Le permite definir su propio atributo.|  
|[db_column](../windows/db-column.md)|Enlaza una columna especificada en el conjunto de filas.|  
|[db_command](../windows/db-command.md)|Crea un comando OLE DB.|  
|[db_param](../windows/db-param.md)|La variable de miembro especificado se asocia con un parámetro de entrada o de salida y delimita la variable.|  
|[db_source](../windows/db-source.md)|Crea una conexión a un origen de datos.|  
|[db_table](../windows/db-table.md)|Se abre una tabla de OLE DB.|  
|[default](../windows/default-cpp.md)|Indica que la interfaz personalizada o dispinterface definida en una coclase representa la interfaz de programación predeterminada.|  
|[defaultvtable](../windows/defaultvtable.md)|Define una interfaz como la interfaz de vtable predeterminada para un control.|  
|[event_receiver](../windows/event-receiver.md)|Crea un receptor de eventos.|  
|[event_source](../windows/event-source.md)|Crea un origen de eventos.|  
|[export](../windows/export.md)|Hace que una estructura de datos que se colocarán en el archivo IDL.|  
|[first_is](../windows/first-is.md)|Especifica el índice del primer elemento de matriz que se transmitan.|  
|[hidden](../windows/hidden.md)|Indica que el elemento existe pero no se debe mostrar en un explorador orientado al usuario.|  
|[implements_category](../windows/implements-category.md)|Especifica las categorías de componentes implementados para la clase.|  
|[last_is](../windows/last-is.md)|Especifica el índice del último elemento de matriz que se transmitan.|  
|[length_is](../windows/length-is.md)|Especifica el número de elementos de la matriz que se transmitan.|  
|[max_is](../windows/max-is.md)|Designa el valor máximo para un índice de matriz válida.|  
|[requires_category](../windows/requires-category.md)|Especifica las categorías de los componentes necesarios de la clase de destino.|  
|[size_is](../windows/size-is.md)|Especifica el tamaño de memoria asignada para los punteros de tamaño, tamaño de punteros a punteros de tamaño y solo o matrices multidimensionales.|  
|[Origen](../windows/source-cpp.md)|En una clase, especifica las interfaces de origen del objeto COM para puntos de conexión. En una propiedad o método, indica que el miembro devuelve un objeto o una variante que consiste en un origen de eventos.|  
|[Subprocesamiento](../windows/threading-cpp.md)|Especifica el modelo de subprocesos de un objeto COM.|  
|[unique](../windows/unique-cpp.md)|Especifica un puntero único.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Especifica el identificador único para una clase o interfaz.|  
|[version](../windows/version-cpp.md)|Identifica una versión determinada entre varias versiones de una clase.|  
|[vi_progid](../windows/vi-progid.md)|Especifica una forma independiente de la versión de ProgID.|  
  
## <a name="see-also"></a>Vea también  
 [Atributos por uso](../windows/attributes-by-usage.md)