---
title: and | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- And
- std.and
- std::and
dev_langs:
- C++
helpviewer_keywords:
- and macro
ms.assetid: 2644ab57-8e1b-48f0-9021-cafe3e26bdc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f32aba356acade280d86da685024c68f63e9968e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="and"></a>y

Alternativa al operador &&.

## <a name="syntax"></a>Sintaxis

```C

#define and &&

```

## <a name="remarks"></a>Comentarios

La macro produce el operador &&.

## <a name="example"></a>Ejemplo

```cpp
// iso646_and.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   bool a = true, b = false, result;

   boolalpha(cout);

   result= a && b;
   cout << result << endl;

   result= a and b;
   cout << result << endl;
}
```

```Output
false
false
```

## <a name="requirements"></a>Requisitos

**Encabezado:** \<iso646.h>