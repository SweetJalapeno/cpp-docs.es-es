---
title: 'auto_gcroot:: ~ auto_gcroot | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_gcroot::~auto_gcroot
- ~auto_gcroot
- auto_gcroot.~auto_gcroot
- msclr::auto_gcroot::~auto_gcroot
- msclr.auto_gcroot.~auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot::~auto_gcroot
ms.assetid: 3c970d43-0cb1-4b27-8bee-0394d91b4739
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f0e99c7e99e8c6c68996ceea4d4a8120f6e048ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="autogcrootautogcroot"></a>auto_gcroot::~auto_gcroot
El `auto_gcroot` destructor.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
~auto_gcroot();  
```  
  
## <a name="remarks"></a>Comentarios  
 El destructor también destruye el objeto en propiedad.  
  
## <a name="example"></a>Ejemplo  
  
```  
// msl_auto_gcroot_dtor.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
public:  
   ClassA() { Console::WriteLine( "ClassA constructor" ); }  
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }  
};  
  
int main()  
{  
   // create a new scope for a:  
   {  
      auto_gcroot<ClassA^> a = gcnew ClassA;  
   }  
   // a goes out of scope here, invoking its destructor  
   // which in turns destructs the ClassA object.  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor  
ClassA destructor  
done  
```  
  
## <a name="requirements"></a>Requisitos  
 **Archivo de encabezado** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Vea también  
 [auto_gcroot (miembros)](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::Release](../dotnet/auto-gcroot-release.md)   
 [auto_gcroot::auto_gcroot](../dotnet/auto-gcroot-auto-gcroot.md)