---
title: Enumeraciones (C++ / CX) | Documentos de Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c96fa4e7194e262eec0be4cf5f7467c163530bd2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="enums-ccx"></a>Enumeraciones (C++/CX)
C++ / CX admite la `public enum class` palabra clave, que es análoga a un estándar de C++ `scoped  enum`. Cuando utilices un enumerador que se declara mediante la palabra clave `public enum class` , debes usar el identificador de enumeración para determinar el ámbito de cada valor de enumerador.  
  
### <a name="remarks"></a>Comentarios  
 Una `public enum class` que no tiene un especificador de acceso, como `public`, se trata como una [enumeración con ámbito](../cpp/enumerations-cpp.md)de C++ estándar.  
  
 A `public enum class` o `public enum struct` declaración puede tener un tipo subyacente de cualquier tipo entero aunque el tiempo de ejecución de Windows requiere que el tipo sea int32, o uint32 para una enumeración de marcas. La sintaxis siguiente describe las partes de un objeto `public enum class` o `public enum struct`.  
  
 En este ejemplo se muestra cómo definir una clase de enumeración pública:  
  
 [!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]  
  
 En este ejemplo siguiente se muestra cómo usarla:  
  
 [!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]  
  
### <a name="examples"></a>Ejemplos  
 En los ejemplos siguientes se muestra cómo declarar una enumeración:  
  
 [!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]  
  
 En el ejemplo siguiente se muestra cómo convertirla a equivalentes numéricos y realizar comparaciones. Observa que el ámbito del uso del enumerador `One` lo determina el identificador de la enumeración `Enum1` , y el ámbito del enumerador `First` lo determina `Enum2`.  
  
 [!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]  
  
## <a name="see-also"></a>Vea también  
 [Sistema de tipos](../cppcx/type-system-c-cx.md)   
 [Referencia del lenguaje de Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Referencia de espacios de nombres](../cppcx/namespaces-reference-c-cx.md)