---
title: Error del compilador C3459 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3459
dev_langs:
- C++
helpviewer_keywords:
- C3459
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eec65ba8acf231a15c6cab15449cc306cdfad4fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3459"></a>Error del compilador C3459
'attribute': el atributo solamente se permite en el indizador de clase (propiedad indexada predeterminada)  
  
Un atributo que se ha diseñado para aplicarse a una propiedad de indizador de clase se usó de forma incorrecta.  
  
Para obtener más información, consulte [Cómo: utilizar propiedades en C++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).  
  
## <a name="example"></a>Ejemplo  
El ejemplo siguiente genera la advertencia C3459.  
  
```  
// C3459.cpp  
// compile with: /clr /c  
public ref class MyString {  
public:  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459  
   property int Prop;  
};  
  
// OK  
public ref class MyString2 {  
   array<int>^ MyArr;  
public:  
   MyString2() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
```