---
title: Usar exit o devolver | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45885cc6dbac50a693bb84abb797469d8aff93a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="using-exit-or-return"></a>Usar exit o return
Cuando se llama a **salir** o ejecutar un `return` instrucción desde **principal**, objetos estáticos se destruyen en el orden inverso de la inicialización. En el ejemplo siguiente se muestra cómo funcionan esa inicialización y limpieza.  
  
## <a name="example"></a>Ejemplo  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 En el ejemplo anterior, los objetos estáticos `sd1` y `sd2` se crean e inicializan antes de la entrada a `main`. Después de que finalice este programa mediante la instrucción `return`, primero se destruye `sd2` y después `sd1`. El destructor para la clase de `ShowData` cierra los archivos asociados a estos objetos estáticos.   
  
 Otra forma de escribir este código es declarar los objetos `ShowData` con ámbito de bloque, lo que permite destruirlos cuando salen del ámbito:  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de finalización adicionales](../cpp/additional-termination-considerations.md)