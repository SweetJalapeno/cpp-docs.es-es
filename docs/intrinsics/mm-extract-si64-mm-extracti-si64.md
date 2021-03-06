---
title: _mm_extract_si64, _mm_extracti_si64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
dev_langs:
- C++
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8ba4986abf097a5827d3db7f93dbbd0a9640862
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64
**Específicos de Microsoft**  
  
 Genera el `extrq` instrucciones para extraer los bits especificados de los 64 bits inferiores del primer argumento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 [in] `Source`  
 Un campo de 128 bits con datos de entrada en sus 64 bits inferiores.  
  
 [in]  `Descriptor`  
 Un campo de 128 bits que describe el campo de bits para extraer.  
  
 [in]  `Length`  
 Un entero que especifica la longitud del campo que desea extraer.  
  
 [in]  `Index`  
 Un entero que especifica el índice del campo que se va a extraer  
  
## <a name="return-value"></a>Valor devuelto  
 Un campo de 128 bits con el campo extraído en sus bits menos significativos.  
  
## <a name="requirements"></a>Requisitos  
  
|Función intrínseca|Arquitectura|  
|---------------|------------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **Archivo de encabezado** \<intrin.h >  
  
## <a name="remarks"></a>Comentarios  
 Esta función intrínseca genera el `extrq` instrucciones para extraer los bits de `Source`. Hay dos versiones de este intrínsecas: `_mm_extracti_si64` es la versión inmediata, y `_mm_extract_si64` es el que no es inmediato.  Cada versión se extrae de `Source` un campo de bits definido por su longitud y el índice de su bit menos significativo. Los valores de la longitud y el índice se toman mod 64, lo que -1 y 127 se interpretan como 63. Si la suma de los índices (reducidos) y la longitud de campo (reducida) es mayor que 64, los resultados son indefinidos. Un valor de cero para la longitud de campo se interpreta como 64. Si el índice de bits y de longitud de campo es ambos cero, 63:0 de bits de `Source` se extraen. Si la longitud de campo es cero, pero el índice de bits es distinto de cero, los resultados son indefinidos.  
  
 En una llamada a _mm_extract_si64, el `Descriptor` contiene el índice en bits 13:8 y la longitud de campo de los datos que deben extraerse en bits 5:0..  
  
 Si se llama a `_mm_extracti_si64` con argumentos que el compilador no puede determinar como constantes de tipo entero, el compilador genera código para empaquetar esos valores en un registro de registros de XMM (`Descriptor`) y llamar a `_mm_extract_si64`.  
  
 Para determinar la compatibilidad de hardware con el `extrq` instrucción, llame a la `__cpuid` intrínseco con `InfoType=0x80000001` y comprobar bit 6 de `CPUInfo[2] (ECX)`. Este bit será 1 si se admite la instrucción y 0 en caso contrario. Si ejecuta el código que usa este hardware intrínseco que no admite la `extrq` instrucciones, los resultados son imprevisibles.  
  
## <a name="example"></a>Ejemplo  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
```Output  
result1 = 0x30eca86  
result2 = 0x30eca86  
result3 = 0x30eca86  
```  
  
**FIN de Específicos de Microsoft**  
 Copyright 2007 por Advanced Micro Devices, Inc. Todos los derechos reservados. Reprodujo con permiso de Advanced Micro Devices, Inc.  
  
## <a name="see-also"></a>Vea también  
 [_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)