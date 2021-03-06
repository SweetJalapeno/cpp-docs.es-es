---
title: para cada uno, en | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
dev_langs:
- C++
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6ab5f7309da1a037f7066d44815cafc934b162cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="for-each-in"></a>for each, in
Procesa una iteración a través de una matriz o colección. Esta palabra clave no estándar está disponible en C++/CLI y proyectos nativos de C++. Sin embargo, no se recomienda su uso. Considere el uso de un estándar [basados en intervalos de instrucción (C++)](../cpp/range-based-for-statement-cpp.md) en su lugar.  
  
## <a name="all-runtimes"></a>Todos los runtimes  
 **Sintaxis**  
  
```  
  
      for each (typeidentifierinexpression) {  
   statements  
}  
  
```  
  
 **Parámetros**  
  
 `type`  
 Tipo de `identifier`.  
  
 `identifier`  
 Variable de iteración que representa el elemento de la colección.  Cuando `identifier` es un [operador de referencia de seguimiento](../windows/tracking-reference-operator-cpp-component-extensions.md), puede modificar el elemento.  
  
 `expression`  
 Colección o expresión de matriz. El elemento de la colección debe ser de un tipo que el compilador pueda convertir en el tipo `identifier`.  
  
 `statements`  
 Instrucción o instrucciones que se van a ejecutar.  
  
 **Comentarios**  
  
 La instrucción `for each` se utiliza para procesar una iteración en una colección. Puede modificar los elementos de una colección, pero no puede agregar ni eliminar elementos.  
  
 El *instrucciones* se ejecutan para cada elemento de la matriz o colección. Cuando la iteración se ha completado en todos los elementos de la colección, el control se transfiere a la instrucción que sigue al bloque `for each`.  
  
 `for each` y `in` son [palabras clave contextuales](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Para obtener más información:  
  
-   [Recorrer en iteración la colección de biblioteca estándar de C++ mediante for each](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [Cómo: Iterar por matrices con for each](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [Cómo: Iterar por una colección genérica con for each](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [Cómo: Iterar por una colección definida por el usuario con for each](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)  
  
## <a name="windows-runtime"></a>Windows en tiempo de ejecución  
  
### <a name="requirements"></a>Requisitos  
 Opción del compilador: **/ZW**  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo se usa `for each` para procesar una iteración en una cadena.  
  
```  
// for_each_string1.cpp  
// compile with: /ZW  
#include <stdio.h>  
using namespace Platform;  
  
ref struct MyClass {  
   property String^ MyStringProperty;  
};  
  
int main() {  
   String^ MyString = ref new String("abcd");  
  
   for each ( char c in MyString )  
      wprintf("%c", c);  
  
   wprintf("/n");  
  
   MyClass^ x = ref new MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( char c in x->MyStringProperty )  
      wprintf("%c", c);  
}  
```  
  
 **Salida**  
  
```Output  
abcd  
  
Testing  
```  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Comentarios**  
  
 La sintaxis CLR es el mismo que el **todos los Runtimes** sintaxis, excepto como se indica a continuación.  
  
 *Expresión*  
 Expresión o colección de matriz administrada. El elemento de la colección debe ser de tipo que el compilador puede convertir desde <xref:System.Object> a la *identificador* tipo.  
  
 *expresión* se evalúa como un tipo que implementa <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, o un tipo que define un `GetEnumerator` método que devuelve un tipo que implementa <xref:System.Collections.IEnumerator> o declara todos los métodos que se definen en `IEnumerator`.  
  
### <a name="requirements"></a>Requisitos  
 Opción del compilador: **/clr**  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo se usa `for each` para procesar una iteración en una cadena.  
  
```  
// for_each_string2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct MyClass {  
   property String ^ MyStringProperty;  
};  
  
int main() {  
   String ^ MyString = gcnew String("abcd");  
  
   for each ( Char c in MyString )  
      Console::Write(c);  
  
   Console::WriteLine();  
  
   MyClass ^ x = gcnew MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( Char c in x->MyStringProperty )  
      Console::Write(c);  
}  
```  
  
 **Salida**  
  
```Output  
abcd  
  
Testing   
```  
  
## <a name="see-also"></a>Vea también  
 [Extensiones de componentes para plataformas de tiempo de ejecución](../windows/component-extensions-for-runtime-platforms.md)