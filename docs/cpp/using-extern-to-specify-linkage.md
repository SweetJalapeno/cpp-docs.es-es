---
title: Uso de extern para especificar vinculación | Documentos de Microsoft
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68bb5f35044a02b64c0475c7c94bc7a0b025cd3e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="using-extern-to-specify-linkage"></a>Usar extern para especificar la vinculación
## <a name="syntax"></a>Sintaxis  
  
```  
extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave `extern` declara una variable o función, y especifica que tiene una vinculación externa (su nombre está visible desde archivos distintos del que la define). Al modificar una variable, `extern` especifica que la variable tiene duración estática (se asigna cuando se inicia el programa y se desasigna cuando finaliza el programa). La variable o función se puede definir en otro archivo de código fuente, o más adelante en el mismo archivo. Las declaraciones de variables y funciones en el ámbito de archivo son externas de forma predeterminada.  
  
## <a name="example"></a>Ejemplo  
  
```  
// specifying_linkage1.cpp  
int i = 1;  
void other();  
  
int main() {  
   // Reference to i, defined above:  
   extern int i;  
}  
  
void other() {  
   // Address of global i assigned to pointer variable:  
   static int *external_i = &i;  
  
   // i will be redefined; global i no longer visible:  
   // int i = 16;  
}  
```  
  
 En C++, cuando se usa con una cadena, `extern` especifica el uso de las convenciones de vinculación de otro lenguaje para los declaradores. Las funciones y datos de C solo están accesibles si se declaran previamente con vinculación de C. Sin embargo, se deben definir en una unidad de traducción compilada por separado.  
  
 Microsoft C++ admite las cadenas **"C"** y **"C++"** en el *literal de cadena* campo. Todos los archivos de inclusión estándar utilizan la sintaxis de `extern` de “C” para permitir que las funciones de la biblioteca en tiempo de ejecución se usen en programas de C++.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran maneras alternativas de declarar los nombres que tienen vinculación de C:  
  
```  
// specifying_linkage2.cpp  
// compile with: /c  
// Declare printf with C linkage.  
extern "C" int printf( const char *fmt, ... );  
  
//  Cause everything in the specified header files  
//   to have C linkage.  
extern "C" {  
   // add your #include statements here  
   #include <stdio.h>  
}  
  
//  Declare the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" {  
   char ShowChar( char ch );  
   char GetChar( void );  
}  
  
//  Define the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" char ShowChar( char ch ) {  
   putchar( ch );  
   return ch;  
}  
  
extern "C" char GetChar( void ) {  
   char ch;  
  
   ch = getchar();  
   return ch;  
}  
  
// Declare a global variable, errno, with C linkage.  
extern "C" int errno;  
```  
  
 Si una función tiene más de una especificación de vinculación, deben coincidir; es un error declarar funciones que tengan tanto vinculación de C como de C++. Además, si en un programa aparecen dos declaraciones para una función (una con una especificación de vinculación y otra sin ella), la declaración con especificación de vinculación debe ser la primera. Cualquier declaración redundante de funciones que ya tengan especificación de vinculación recibe la vinculación especificada en la primera declaración. Por ejemplo:  
  
```  
extern "C" int CFunc1();  
...  
int CFunc1();            // Redeclaration is benign; C linkage is  
                         //  retained.  
  
int CFunc2();  
...  
extern "C" int CFunc2(); // Error: not the first declaration of  
                         //  CFunc2;  cannot contain linkage  
                         //  specifier.  
```  
  
 Funciones y objetos declarados explícitamente como **estático** dentro del cuerpo de un especificador de vinculación compuesto (**{}**) se tratan como funciones estáticas u objetos; se omite el especificador de vinculación. Otras funciones y objetos se comportan como si se hubieran declarado mediante la palabra clave `extern`. (Consulte [usar extern para especificar vinculación](../cpp/using-extern-to-specify-linkage.md) para obtener más información acerca de la `extern` (palabra clave).)  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave](../cpp/keywords-cpp.md)   
 [Especificador de clase de almacenamiento extern](../c-language/extern-storage-class-specifier.md)   
 [Comportamiento de los identificadores](../c-language/behavior-of-identifiers.md)   
 [Vinculación](../c-language/linkage.md)