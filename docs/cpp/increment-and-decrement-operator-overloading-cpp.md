---
title: Incremento y operador de decremento de sobrecarga (C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dee35098dbf78e04241f04687c74c40ded1a0010
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Sobrecarga de operadores de incremento y decremento (C++)
Los operadores de incremento y decremento pertenecen a una categoría especial porque hay dos variantes de cada uno de ellos:  
  
-   Preincremento y postincremento  
  
-   Predecremento y postdecremento  
  
 Cuando escriba funciones de operador sobrecargadas, puede resultarle útil implementar versiones distintas para las versiones de prefijo y de postfijo de estos operadores. Para distinguirlas, se aplica la regla siguiente: la forma de prefijo del operador se declara exactamente del mismo modo que cualquier otro operador unario; la forma de postfijo acepta un argumento adicional de tipo `int`.  
  
> [!NOTE]
>  Cuando se especifica un operador sobrecargado para la forma del operador de incremento o decremento, el argumento adicional debe ser de tipo `int`; la especificación de cualquier otro tipo genera un error.  
  
 En el ejemplo siguiente se muestra cómo definir operadores de incremento y decremento de prefijo y de postfijo para la clase `Point`:  
  
```  
// increment_and_decrement1.cpp  
class Point  
{  
public:  
   // Declare prefix and postfix increment operators.  
   Point& operator++();       // Prefix increment operator.  
   Point operator++(int);     // Postfix increment operator.  
  
   // Declare prefix and postfix decrement operators.  
   Point& operator--();       // Prefix decrement operator.  
   Point operator--(int);     // Postfix decrement operator.  
  
   // Define default constructor.  
   Point() { _x = _y = 0; }  
  
   // Define accessor functions.  
   int x() { return _x; }  
   int y() { return _y; }  
private:  
   int _x, _y;  
};  
  
// Define prefix increment operator.  
Point& Point::operator++()  
{  
   _x++;  
   _y++;  
   return *this;  
}  
  
// Define postfix increment operator.  
Point Point::operator++(int)  
{  
   Point temp = *this;  
   ++*this;  
   return temp;  
}  
  
// Define prefix decrement operator.  
Point& Point::operator--()  
{  
   _x--;  
   _y--;  
   return *this;  
}  
  
// Define postfix decrement operator.  
Point Point::operator--(int)  
{  
   Point temp = *this;  
   --*this;  
   return temp;  
}  
int main()  
{  
}  
```  
  
 Pueden definirse los mismos operadores en el ámbito de archivo (global) mediante los siguientes encabezados de función:  
  
```  
friend Point& operator++( Point& )      // Prefix increment  
friend Point& operator++( Point&, int ) // Postfix increment  
friend Point& operator--( Point& )      // Prefix decrement  
friend Point& operator--( Point&, int ) // Postfix decrement  
```  
  
 El argumento de tipo `int` que designa la forma de postfijo del operador de incremento o decremento no suele utilizarse para pasar argumentos. Normalmente contiene el valor 0. Sin embargo, se puede utilizar del modo siguiente:  
  
```  
// increment_and_decrement2.cpp  
class Int  
{  
public:  
    Int &operator++( int n );  
private:  
    int _i;  
};  
  
Int& Int::operator++( int n )  
{  
    if( n != 0 )    // Handle case where an argument is passed.  
        _i += n;  
    else  
        _i++;       // Handle case where no argument is passed.  
    return *this;  
}  
int main()  
{  
   Int i;  
   i.operator++( 25 ); // Increment by 25.  
}  
```  
  
 No hay ninguna sintaxis para usar los operadores de incremento y decremento para pasar estos valores que no sea la invocación explícita, como se muestra en el código anterior. Una manera más sencilla de implementar esta funcionalidad es sobrecargar el operador de suma/asignación (`+=`).  
  
## <a name="see-also"></a>Vea también  
 [Sobrecarga de operadores](../cpp/operator-overloading.md)