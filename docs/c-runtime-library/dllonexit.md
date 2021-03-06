---
title: __dllonexit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- __dllonexit
dev_langs:
- C++
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68de7c3ab3b823c1e3d08a13a9d7363232e9712e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="dllonexit"></a>__dllonexit
Registra una rutina que se llama a la hora de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
_onexit_t __dllonexit(   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### <a name="parameters"></a>Parámetros  
 `func`  
 Puntero a una función que se ejecuta al salir.  
  
 `pbegin`  
 Puntero a una variable que señala al comienzo de una lista de funciones que se ejecutan al desasociar.  
  
 `pend`  
 Puntero a una variable que señala al final de una lista de funciones que se ejecutan al desasociar.  
  
## <a name="return-value"></a>Valor devuelto  
 Si se realiza correctamente, un puntero a la función del usuario. De lo contrario, un puntero nulo.  
  
## <a name="remarks"></a>Comentarios  
 La función `__dllonexit` es análoga a la función [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) excepto en que esta rutina no puede ver las variables globales que usa esa función. En lugar de variables globales, esta función usa los parámetros `pbegin` y `pend`.  
  
 Las funciones `_onexit` y `atexit` en un archivo DLL vinculado con MSVCRT.LIB deben mantener su propia lista atexit/_onexit. Esta rutina es el proceso de trabajo al que llaman estos archivos DLL.  
  
 El tipo `_PVFV` se define como `typedef void (__cdecl *_PVFV)(void)`.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Archivo necesario|  
|-------------|-------------------|  
|__dllonexit|onexit.c|  
  
## <a name="see-also"></a>Vea también  
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)