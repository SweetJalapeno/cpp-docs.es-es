---
title: OPCIÓN (MASM) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80291c805cad3ef041fffc58983ff399da07c9d9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="option-masm"></a>OPTION (MASM)
Habilita y deshabilita las características del ensamblador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Comentarios  
 Las opciones disponibles incluyen:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULADOR**|  
|**NOEMULATOR**|**EPÍLOGO**|**EXPR16**|**EXPR32**|  
|**IDIOMA**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**PRÓLOGO**|**SOLO LECTURA**|**NOREADONLY**|  
|**EL ÁMBITO**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 La sintaxis de LENGUAJE es **opción idioma: *** x*, donde *x* es uno de C, SYSCALL, STDCALL, PASCAL, FORTRAN o BASIC.  SYSCALL, PASCAL, FORTRAN y BASIC no son compatibles con utiliza con [. MODELO](../../assembler/masm/dot-model.md) sin formato.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de directivas](../../assembler/masm/directives-reference.md)