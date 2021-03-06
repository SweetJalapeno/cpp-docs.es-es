---
title: '&lt;consulte&gt; (Visual C++) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a03dd56320b948d47c765f253bf3e6b706ed2b56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ltseegt-visual-c"></a>&lt;consulte&gt; (Visual C++)
La etiqueta \<see> permite especificar un vínculo desde el texto. Use [ \<seealso >](../ide/seealso-visual-cpp.md) para indicar el texto que desea que aparezca en una sección Vea también.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.  Ponga el nombre entre comillas simples o dobles.  
  
 El compilador comprueba si el elemento de código dado existe y resuelve `member` al nombre de elemento en el resultado XML.  El compilador emite una advertencia si no encuentra `member`.  
  
## <a name="remarks"></a>Comentarios  
 Compile con [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) para procesar los comentarios de documentación a un archivo.  
  
 Vea [ \<resumen >](../ide/summary-visual-cpp.md) para obtener un ejemplo del uso de \<vea >.  
  
 El compilador de Visual C++ intentará resolver referencias cref en un paso por los comentarios de documentación.  Por tanto, si usa las reglas de búsqueda de C++, un símbolo que no encuentra el compilador se marcará como no resuelto. Vea [ \<seealso >](../ide/seealso-visual-cpp.md) para obtener más información.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo puede hacer referencia de tipo cref a un tipo genérico, que el compilador resuelve la referencia.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## <a name="see-also"></a>Vea también  
 [Documentación de XML](../ide/xml-documentation-visual-cpp.md)