---
title: 'Cómo: escribir datos en el registro de Windows (C++ / CLI) | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 304bc224be8776c9793af07283c6a5697a4e49eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-data-to-the-windows-registry-ccli"></a>Cómo: Escribir datos en el Registro de Windows (C++/CLI)
El siguiente ejemplo de código utiliza el <xref:Microsoft.Win32.Registry.CurrentUser> clave para crear una instancia editable de la <xref:Microsoft.Win32.RegistryKey> clase correspondiente a la **Software** clave. El método <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> se utiliza después para crear una nueva clave y agregarla a pares clave/valor.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="code"></a>Código  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede usar .NET Framework para tener acceso al registro con el <xref:Microsoft.Win32.Registry> y [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) las clases, que están definen en el <xref:Microsoft.Win32> espacio de nombres. El **registro** clase es un contenedor para instancias estáticas de la <xref:Microsoft.Win32.RegistryKey> clase. Cada instancia representa un nodo de Registro raíz. Las instancias son <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> y <xref:Microsoft.Win32.Registry.Users>.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: leer datos del registro de Windows (C++ / CLI)](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [Programación de .NET con C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)