---
title: Restricciones de los nombres de símbolos | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.name
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ee6ce257609c4761e43630a66de9cb9b996269
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="symbol-name-restrictions"></a>Restricciones de los nombres de símbolo
Las restricciones en los nombres de símbolos son las siguientes:  
  
-   Todos los [símbolos](../windows/symbols-resource-identifiers.md) debe ser único dentro del ámbito de la aplicación. Esto evita conflictos de definiciones de símbolos en los archivos de encabezado.  
  
-   Los caracteres válidos en un nombre de símbolo son A-z, a-z, 0-9 y caracteres de subrayado (_).  
  
-   Los nombres de símbolo no pueden empezar por un número y se limitan a 247 caracteres.  
  
-   Los nombres de símbolo no pueden contener espacios.  
  
-   Los nombres de símbolo no distinguen entre mayúsculas y minúsculas, pero se conservan las mayúsculas o minúsculas de la primera definición de símbolos. El compilador/editor de recursos y los programas de C++  usan el archivo de encabezado que define los símbolos para hacer referencia a los recursos definidos en un archivo de recursos. Cuando dos nombres de símbolo difieren únicamente en sus mayúsculas o minúsculas, el programa de C++ verá dos símbolos distintos, mientras que el compilador/editor de recursos verá dos nombres se remiten al mismo símbolo.  
  
    > [!NOTE]
    >  Si no respeta el esquema de nombre de símbolo estándar (ID*_[palabra clave]) descrito aquí y el nombre del símbolo resulta ser el mismo que una palabra clave conocida por el compilador de script de recursos, cuando trate de generar el archivo de script de recursos, se producirá un error aparentemente aleatorio difícil de diagnosticar. Para evitar esto, aténgase al esquema de nomenclatura estándar.  
  
 Los nombres de símbolo tienen prefijos descriptivos que indican el tipo de recurso u objeto que representan. Estos prefijos descriptivos comienzan por el identificador de combinación de texto. La biblioteca MFC (Microsoft Foundation Class) usa las convenciones de nomenclatura de símbolo recogidas en la siguiente tabla.  
  
|Categoría|Prefijo|Usar|  
|--------------|------------|---------|  
|Recursos|IDR_ IDD_ IDC_ IDI_ IDB_|Acelerador o menú (y recursos asociados o personalizados) Cuadro de diálogo Cursor Icono Mapa de bits|  
|Elementos de menú|ID_|Elemento de menú|  
|Comandos|ID_|Comando|  
|Controles y ventanas secundarias|IDC_|Control|  
|Cadenas|IDS_|Cadena en la tabla de cadenas|  
|MFC|AFX_|Reservado para símbolos de MFC predefinidos|  
  

  
## <a name="requirements"></a>Requisitos  
 Win32  
  
## <a name="see-also"></a>Vea también  
 [Cambiar un símbolo o el nombre de símbolo (Id.)](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [Restricciones de valores de símbolos](../windows/symbol-value-restrictions.md)   
 [Identificadores de símbolo predefinidos](../windows/predefined-symbol-ids.md)