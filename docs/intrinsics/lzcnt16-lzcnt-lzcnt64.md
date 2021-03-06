---
title: __lzcnt16, __lzcnt, __lzcnt64 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e04182cf673674e1f1ba8c073b624760bc4809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64
**Específicos de Microsoft**  
  
 El número de la izquierda de recuentos de ceros finales en un 16, 32 o entero de 64 bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 [in] `value`  
 Los 16, 32 o entero sin signo de 64 bits para buscar los ceros iniciales.  
  
## <a name="return-value"></a>Valor devuelto  
 El número de iniciales bits cero en el `value` parámetro. Si `value` es cero, el valor devuelto es el tamaño de la entrada de los operandos (16, 32 o 64). Si la mayoría bit significativo de `value` es uno, el valor devuelto es cero.  
  
## <a name="requirements"></a>Requisitos  
  
|Función intrínseca|Arquitectura|  
|---------------|------------------|  
|`__lzcnt16`|AMD: Manipulación de bits avanzada (ABN)<br /><br /> Intel: Haswell|  
|`__lzcnt`|AMD: Manipulación de bits avanzada (ABN)<br /><br /> Intel: Haswell|  
|`__lzcnt64`|AMD: Opciones avanzadas manipulación de bits (ABN) en modo de 64 bits.<br /><br /> Intel: Haswell|  
  
 **Archivo de encabezado** \<intrin.h >  
  
## <a name="remarks"></a>Comentarios  
 Cada una de estas funciones intrínsecas genera el `lzcnt` instrucción.  El tamaño del valor que el `lzcnt` instrucción devuelve es el mismo que el tamaño de su argumento.  En modo de 32 bits no hay ningún 64-bit registros de propósito general, por lo tanto, no de 64 bits `lzcnt`.  
  
 Para determinar la compatibilidad de hardware con el `lzcnt` llamada la `__cpuid` intrínseco con `InfoType=0x80000001` y compruebe el bit 5 de `CPUInfo[2] (ECX)`. Este bit será 1 si se admite la instrucción y 0 en caso contrario. Si ejecuta el código que usa esta función intrínseca en hardware que no es compatible con la `lzcnt` instrucciones, los resultados son imprevisibles.  
  
 En procesadores Intel que no admiten la `lzcnt` la codificación de bytes de la instrucción se ejecuta la instrucción, como `bsr` (bit inversa de examen). Si la portabilidad del código es un problema, considere la posibilidad de uso de la `_BitScanReverse` intrínseco en su lugar. Para obtener más información, consulte [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).  
  
## <a name="example"></a>Ejemplo  
  
```  
// Compile this test with: /EHsc  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__lzcnt16(0x0) = 16  
__lzcnt16(0xff) = 8  
__lzcnt16(0xffff) = 0  
__lzcnt(0x0) = 32  
__lzcnt(0xff) = 24  
__lzcnt(0xffff) = 16  
__lzcnt(0xffffffff) = 0  
```  
  
**FIN de Específicos de Microsoft**  
 Algunas partes de este contenido son Copyright 2007 por Advanced Micro Devices, Inc. Todos los derechos reservados. Reprodujo con permiso de Advanced Micro Devices, Inc.  
  
## <a name="see-also"></a>Vea también  
 [Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)
