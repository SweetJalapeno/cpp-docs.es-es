---
title: Inicialización de clases y structs sin constructores (C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a547dbe4d5668439ea3002249568962a50a0036
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>Inicialización de clases y structs sin constructores (C++)
No siempre es necesario definir un constructor para una clase, especialmente si son relativamente sencillas. Los usuarios pueden inicializar objetos de una clase o struct usando la inicialización uniforme, tal y como se muestra en el siguiente ejemplo:  
  
```  
#include "stdafx.h"  
#include <Windows.h>  
  
// No constructor  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
// Has a constructor  
struct TempData2  
{  
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :  
       minTemp(minimum), maxTemp(maximum), current(cur), stationId(id), time(t) {}  
    int stationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
int main()  
{  
    // Member initialization (in order of declaration):  
    TempData td{ 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default{};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;  
  
    // Member declaration (in order of ctor parameters)  
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, GetCurrentTime() };  
  
    return 0;  
}  
  
```  
  
 Tenga en cuenta que, cuando una clase o estructura no tiene ningún constructor, se proporcionan los elementos de lista en el orden en que los miembros se declaran en la clase. Si la clase tiene un constructor, proporcione los elementos en el orden de los parámetros.  
  
## <a name="see-also"></a>Vea también  
 [Clases y estructuras](../cpp/classes-and-structs-cpp.md)   
 [Constructores](../cpp/constructors-cpp.md)