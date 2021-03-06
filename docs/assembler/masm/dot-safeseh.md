---
title: . SAFESEH | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea34448b4dae0525e7feb2fd7cca310a95a6e3c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="safeseh"></a>.SAFESEH
Registra una función como un controlador de excepciones estructurado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>Comentarios  
 *identificador* debe ser el identificador para definida localmente [PROC](../../assembler/masm/proc.md) o [EXTRN](../../assembler/masm/extrn.md) un proceso. A [etiqueta](../../assembler/masm/label-masm.md) no está permitido. El archivo. SAFESEH (directiva) requiere la [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) la opción de línea de comandos de ml.exe.  
  
 Para obtener más información acerca de los controladores de excepciones estructurado, consulte [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Por ejemplo, para registrar un controlador de excepciones seguros, cree un nuevo archivo MASM (como se indica a continuación), ensamblar con/SAFESEH y agregarlo a los objetos vinculados.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de directivas](../../assembler/masm/directives-reference.md)