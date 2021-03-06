---
title: _BitScanReverse, _BitScanReverse64 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
dev_langs:
- C++
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35d51f3e7eaf0daeca006ff669398c9a3727a098
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="bitscanreverse-bitscanreverse64"></a>_BitScanReverse, _BitScanReverse64
**Específicos de Microsoft**  
  
 Buscar los datos de máscara de bit más significativo (MSB) a bit menos significativo (LSB) para un bit establecido (1).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
unsigned char _BitScanReverse(  
   unsigned long * Index,  
   unsigned long Mask  
);  
unsigned char _BitScanReverse64(  
   unsigned long * Index,  
   unsigned __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 [out] `Index`  
 Cargado con la posición de bit del primer bit establecido (1) que se encontró.  
  
 [in] `Mask`  
 El valor de 32  bits o 64 bits que se va a buscar.  
  
## <a name="return-value"></a>Valor devuelto  
 Distinto de cero si se estableció `Index`, o 0 si no se encuentra ningún bit establecido.  
  
## <a name="requirements"></a>Requisitos  
  
|Función intrínseca|Arquitectura|Header|  
|---------------|------------------|------------|  
|`_BitScanReverse`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<INTRIN.h >|  
|`_BitScanReverse64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]||  
  
## <a name="example"></a>Ejemplo  
  
```  
// BitScanReverse.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanReverse)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanReverse(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## <a name="input"></a>Entrada  
  
```  
12  
```  
  
## <a name="sample-output"></a>Resultados del ejemplo  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 3  
```  
  
**FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)