---
title: "espacio de nombres predeterminado | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default_CPP"
dev_langs: 
  - "C++"
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# espacio de nombres predeterminado
El espacio de nombres `default` abarca los tipos integrados que son compatibles con [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\).  
  
## Sintaxis  
  
```  
namespace default;  
```  
  
## Miembros  
 Todos los tipos integrados heredan los miembros siguientes.  
  
|||  
|-|-|  
|[default::\(type\_name\)::Equals \(Método\)](../cppcx/default-type-name-equals-method.md)|Determina si el objeto especificado es igual al objeto actual.|  
|[default::\(type\_name\)::GetHashCode \(Método\)](../cppcx/default-type-name-gethashcode-method.md)|Devuelve el código hash de esta instancia.|  
|[default::\(type\_name\)::GetType \(Método\)](../cppcx/default-type-name-gettype-method.md)|Devuelve una cadena que representa el tipo actual.|  
|[default::\(type\_name\)::ToString \(Método\)](../cppcx/default-type-name-tostring-method.md)|Devuelve una cadena que representa el tipo actual.|  
  
### Tipos integrados  
  
|Nombre|Descripción|  
|------------|-----------------|  
|`char16`|Un valor no numérico de 16 bits que representa un punto de código Unicode \(UTF\-16\).|  
|`float32`|Número de punto flotante de 32 bits conforme a IEEE 754.|  
|`float64`|Número de punto flotante de 64 bits conforme a IEEE 754.|  
|`int16`|Entero de 16 bits con signo.|  
|`int32`|Entero de 32 bits con signo.|  
|`int64`|Entero de 64 bits con signo.|  
|`int8`|Valor numérico con signo de 8 bits.|  
|`uint16`|Entero de 16 bits sin signo.|  
|`uint32`|Entero de 32 bits sin signo.|  
|`uint64`|Entero de 64 bits sin signo.|  
|`uint8`|Valor numérico sin signo de 8 bits.|  
  
## Requisitos  
 **Encabezado:** vccorlib.h  
  
## Vea también  
 [Referencia del lenguaje Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)