---
title: __movsw | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __movsw
dev_langs:
- C++
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1b1bb1b877c0816650b78d5c6132e526afd5586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="movsw"></a>__movsw
**Específicos de Microsoft**  
  
 Genera una cadena mover (`rep movsw`) instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __movsw(   
   unsigned short* Dest,   
   unsigned short* Source,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 [out] `Dest`  
 El destino de la operación.  
  
 [in] `Source`  
 El origen de la operación.  
  
 [in] `Count`  
 El número de palabras que se va a copiar.  
  
## <a name="requirements"></a>Requisitos  
  
|Función intrínseca|Arquitectura|  
|---------------|------------------|  
|`__movsw`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Archivo de encabezado** \<intrin.h >  
  
## <a name="remarks"></a>Comentarios  
 El resultado es que la primera `Count` palabras que señala `Source` se copian en el `Dest` cadena.  
  
 Esta rutina solo está disponible como función intrínseca.  
  
## <a name="example"></a>Ejemplo  
  
```  
// movsw.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsw)  
  
int main()  
{  
    unsigned short s1[10];  
    unsigned short s2[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
    __movsw(s1, s2, 10);  
  
    for (int i = 0; i < 10; i++)  
        printf_s("%d ", s1[i]);  
    printf_s("\n");  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
**FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)