---
title: 'Cómo: escribir un archivo de texto (C++ / CLI) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [C++], text
- text files, writing in C++
ms.assetid: 39ecdba6-84e0-485c-a202-84cf6d7b8d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e0ce3839a5d0a0668d921a2d64cb0cf7bd1c775
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-a-text-file-ccli"></a>Cómo: Escribir un archivo de texto (C++/CLI)
En el ejemplo de código siguiente se muestra cómo crear un archivo de texto y escribir texto en él con el <xref:System.IO.StreamWriter> (clase), que se define en el <xref:System.IO> espacio de nombres. El <xref:System.IO.StreamWriter> constructor toma el nombre del archivo que se creará. Si el archivo existe, se sobrescribe (a menos que pase True como el segundo <xref:System.IO.StringWriter> argumento del constructor).  
  
 El archivo, a continuación, se archiva mediante la <xref:System.IO.StreamWriter.Write%2A> y <xref:System.IO.TextWriter.WriteLine%2A> funciones.  
  
## <a name="example"></a>Ejemplo  
  
```  
// text_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "textfile.txt";  
  
   StreamWriter^ sw = gcnew StreamWriter(fileName);  
   sw->WriteLine("A text file is born!");  
   sw->Write("You can use WriteLine");  
   sw->WriteLine("...or just Write");  
   sw->WriteLine("and do {0} output too.", "formatted");  
   sw->WriteLine("You can also send non-text objects:");  
   sw->WriteLine(DateTime::Now);  
   sw->Close();  
   Console::WriteLine("a new file ('{0}') has been written", fileName);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [E/S de archivos y secuencias](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [Programación de .NET con C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)