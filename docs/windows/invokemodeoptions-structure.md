---
title: Estructura de InvokeModeOptions | Documentos de Microsoft
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b1eb0e7f6cf49a7c6ac12a4810ae1622e263e2f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="invokemodeoptions-structure"></a>Estructura de InvokeModeOptions

Especifica si se activan todos los eventos en la cola de delegado, o para detener la activación después de que se produce un error. Los valores permitidos se especifican en el `InvokeMode` enum.

## <a name="syntax"></a>Sintaxis

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>Requisitos

**Encabezado:** event.h

**Espacio de nombres:** Microsoft::WRL

## <a name="see-also"></a>Vea también

[Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)
[Microsoft::WRL::AgileEventSource (clase)](../windows/agileeventsource-class.md)