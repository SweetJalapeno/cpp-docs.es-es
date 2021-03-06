---
title: 'Cómo: utilizar expresiones regulares para buscar y reemplazar (C++ / CLI) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search and replace
- Replace method
- regular expressions [C++], search and replace
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: feb64670accef1cdcc5eedf9aa2b081dc41615b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-regular-expressions-to-search-and-replace-ccli"></a>Cómo: Utilizar expresiones regulares para buscar y reemplazar (C++/CLI)
En el ejemplo de código siguiente se muestra cómo la clase de expresión regular <xref:System.Text.RegularExpressions.Regex> puede utilizarse para realizar la búsqueda y reemplazo. Esto se realiza con el <xref:System.Text.RegularExpressions.Regex.Replace%2A> método. La versión empleada toma dos cadenas como entrada: la cadena que deba modificarse y la cadena que se va a insertar en lugar de las secciones (si existe) que coinciden con el patrón proporcionado para el <xref:System.Text.RegularExpressions.Regex> objeto.  
  
 Este código reemplaza todos los dígitos de una cadena con caracteres de subrayado (_) y, a continuación, reemplaza aquéllos por una cadena vacía, con lo que quitaría ellos. El mismo efecto puede realizarse en un solo paso, pero se utilizan dos pasos a continuación para fines de demostración.  
  
## <a name="example"></a>Ejemplo  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Expresiones regulares de .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [Programación de .NET con C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)