---
title: Compilador advertencia (nivel 1) C4407 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4407
dev_langs:
- C++
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbc02c32463703f658cef1d5756926311d89b193
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4407"></a>Advertencia del compilador (nivel 1) C4407
convertir entre distintas representaciones de puntero a miembro, el compilador puede generar código incorrecto  
  
 Se detectó una conversión incorrecta.  
  
 La advertencia C4407 pueden generarse debido a trabajo de conformidad del compilador efectuado en Visual C++ 2005. Puntero a miembro ahora requiere un nombre completo y el operador address-of (&).  
  
 La advertencia C4407 puede producirse si convierte entre un varios herencia puntero a miembro a un herencia única de puntero a miembro. A veces esto puede funcionar, pero a veces no es posible porque la representación de puntero a miembro de herencia simple no contiene información suficiente. Compilar con la **/VMM** podría ayudar a solucionar (para obtener más información, consulte [/VMM, / VMs, /vmv (representación de propósito General)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). También puede intentar reorganizar las clases base; el compilador detecta una pérdida de información en la conversión porque es una clase base con un desplazamiento distinto de cero de la clase derivada.  
  
 El ejemplo siguiente genera la advertencia C4407:  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```