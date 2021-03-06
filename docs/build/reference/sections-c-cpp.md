---
title: SECCIONES) (C/C ++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c433bf49ee4c56833ac7291bcc4a0f90e32f4e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="sections-cc"></a>SECTIONS (C/C++)
Presenta una sección de uno o varios `definitions` que son especificadores de acceso en secciones en el archivo de salida del proyecto.  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>Comentarios  
 Cada definición debe estar en una línea independiente. El `SECTIONS` palabra clave puede estar en la misma línea que la primera definición o en una línea anterior. El archivo .def puede contener uno o más `SECTIONS` las instrucciones.  
  
 Esto `SECTIONS` instrucción establece los atributos de una o varias secciones en el archivo de imagen y puede utilizarse para reemplazar los atributos predeterminados para cada tipo de sección.  
  
 El formato de `definitions` es:  
  
 `.section_name specifier`  
  
 donde `.section_name` es el nombre de una sección en la imagen del programa y `specifier` es uno o varios de los siguientes modificadores de acceso:  
  
|Modificador|Descripción|  
|--------------|-----------------|  
|`EXECUTE`|La sección es ejecutable|  
|`READ`|Permite operaciones de lectura en datos|  
|`SHARED`|Comparte la sección entre todos los procesos que cargan la imagen|  
|`WRITE`|Permite operaciones de escritura en los datos|  
  
 Separe los nombres de especificadores con un espacio. Por ejemplo:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS` marca el principio de una lista de sección `definitions`. Cada `definition` debe estar en una línea independiente. El `SECTIONS` palabra clave puede estar en la misma línea que la primera `definition` o en una línea anterior. El archivo .def puede contener uno o más `SECTIONS` las instrucciones. El `SEGMENTS` (palabra clave) se admite como sinónimo de `SECTIONS`.  
  
 Se admiten las versiones anteriores de Visual C++:  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 El `CLASS` palabra clave se admite por compatibilidad, pero se omite.  
  
 Es una manera equivalente para especificar atributos de la sección con la [/SECTION](../../build/reference/section-specify-section-attributes.md) opción.  
  
## <a name="see-also"></a>Vea también  
 [Reglas para instrucciones de definición de módulos](../../build/reference/rules-for-module-definition-statements.md)