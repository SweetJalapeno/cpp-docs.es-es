---
title: Expresiones lambda en C++ | Documentos de Microsoft
ms.custom: ''
ms.date: 07/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1cfcb210d3de7ce818d39ecf1703299defedc5d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lambda-expressions-in-c"></a>Expresiones lambda en C++
En C ++ 11 y versiones posteriores, una expresión lambda, a menudo denominado un *lambda*: es una forma cómoda de definir un objeto de función anónima (un *cierre*) en la ubicación donde se invoca o se pasa como un argumento para una función. Normalmente, las lambdas se usan para encapsular unas líneas de código que se pasan a algoritmos o métodos asincrónicos. En este artículo se define qué son las expresiones lambda, se comparan con otras técnicas de programación, se describen sus ventajas y se proporciona un ejemplo básico.  

## <a name="related-topics"></a>Temas relacionados
- [Expresiones lambda frente a objetos de función](lambda-expression-syntax.md)
- [Trabajar con expresiones lambda](examples-of-lambda-expressions.md)
- [expresiones lambda constexpr](lambda-expressions-constexpr.md)

## <a name="parts-of-a-lambda-expression"></a>Partes de una expresión lambda  
 La norma ISO de C++ muestra una expresión lambda sencilla que se pasa como tercer argumento a la función `std::sort()`:  
  
```cpp  
#include <algorithm>  
#include <cmath>  
  
void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
            return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
}  
  
```  
  
 En esta ilustración se muestran las partes de una expresión lambda:  
  
 ![Elementos estructurales de una expresión lambda](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *cláusula de captura* (también conocido como el *iniciador de expresión lambda* en la especificación de C++.)  
  
2.  *lista de parámetros* opcional. (También conocido como el *declarador de expresión lambda*)  
  
3.  *especificación mutable* opcional.  
  
4.  *especificación de excepción* opcional.  
  
5.  *tipo de valor devuelto finales* opcional.  
  
6.  *parte del cuerpo lambda*)  
  
### <a name="capture-clause"></a>Cláusula capture  
 Una expresión lambda puede introducir variables nuevas en el cuerpo (en **C ++ 14**) y también puede tener acceso, o *capturar*, las variables del ámbito circundante. Una expresión lambda comienza con la cláusula de captura (*iniciador de expresión lambda* en la sintaxis estándar), que especifica las variables que se capturan y si la captura por valor o por referencia. A las variables que tienen como prefijo una y comercial (`&`) se accede mediante referencia y a las variables que no tienen el prefijo se accede por valor.  
  
 Una cláusula de captura vacía, `[ ]`, indica que el cuerpo de la expresión lambda no tiene acceso a ninguna variable en el ámbito de inclusión.  
  
 Puede usar el modo de captura predeterminado (*captura predeterminado* en la sintaxis estándar) para indicar cómo capturar cualquier variable que se hace referencia en la expresión lambda exterior: `[&]` significa capturan todas las variables que se hace referencia a referencia, y `[=]` significa que se capturan por valor. Puede usar un modo de captura predeterminado y, después, especificar el modo opuesto de forma explícita para unas variables específicas. Por ejemplo, si el cuerpo de una expresión lambda accede a la variable externa `total` por referencia y a la variable externa `factor` por valor, las siguientes cláusulas capture serán equivalentes:  
  
```cpp  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 Solo las variables que se mencionan en la expresión lambda se capturan cuando se utiliza el valor predeterminado captura.  
  
 Si una cláusula de captura incluye el valor predeterminado captura `&`, ningún `identifier` en un `capture` de captura cláusula puede tener el formato `& identifier`. Del mismo modo, si la cláusula de captura incluye el valor predeterminado captura `=`, ningún `capture` de captura cláusula puede tener el formato `= identifier`. Un identificador o `this` no puede aparecer más de una vez en una cláusula capture. En el fragmento de código siguiente se muestran algunos ejemplos.  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};      // OK  
    [&, &i]{};     // ERROR: i preceded by & when & is the default  
    [=, this]{};   // ERROR: this when = is the default  
    [=, *this]{ }; // OK: captures this by value. See below.
    [i, i]{};      // ERROR: i repeated  
}  
```  
  
 Una captura seguida de puntos suspensivos es una expansión del paquete, como se muestra en este [plantilla variádica](../cpp/ellipses-and-variadic-templates.md) ejemplo:  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 Para usar expresiones lambda en el cuerpo de un método de clase, pase el puntero `this` a la cláusula de captura para proporcionar acceso a los métodos y miembros de datos de la clase contenedora. 
 
**Visual Studio 2017 15,3 y versiones posteriores** (disponible con [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): el `this` puntero quede capturado por valor especificando `*this` en la cláusula de captura. Captura por valor significa que toda la *cierre*, que es el objeto de función anónima que encapulates la expresión lambda, se copia en cada sitio de llamada que se invoca la expresión lambda. Captura por valor es útil cuando la expresión lambda se ejecutará en paralelo o asincrónicas operaciones, especialmente en ciertas arquitecturas de hardware como NUMA. 

Para obtener un ejemplo que muestra cómo usar expresiones lambda con métodos de clase, vea "Ejemplo: usar una expresión Lambda en un método" en [ejemplos de expresiones Lambda](../cpp/examples-of-lambda-expressions.md).  
  
 Al usar la cláusula de captura, se recomienda tener en cuenta estos aspectos importantes, especialmente cuando se usan expresiones lambda con multithreading:  
  
-   Se pueden usar capturas por referencia para modificar variables externas, pero no se pueden usar capturas por valor. (`mutable` permite modificar las copias, pero no los originales).  
  
-   Las capturas por referencia reflejan actualizaciones en variables externas, pero las capturas por valor no.  
  
-   Las capturas por referencia presentan una dependencia de la duración, pero las capturas por valor no tienen ninguna dependencia de la duración. Esto es muy importante cuando la expresión lambda se inicia de forma asincrónica. Si captura una variable local por referencia en una expresión lambda asincrónica, es muy probable que dicha variable desaparezca en cuanto se inicie la expresión lambda, lo que provocará una infracción de acceso en tiempo de ejecución.  
  
### <a name="generalized-capture-c-14"></a>Captura generalizada (C++ 14)  
  
 En C++14 puede introducir e inicializar nuevas variables en la cláusula de captura sin necesidad de que dichas variables existan en el ámbito de inclusión de la función lambda. La inicialización se puede expresar como cualquier expresión arbitraria; el tipo de la variable nueva se deduce del tipo producido por la expresión. Una ventaja de esta característica es que en C++14 puede capturar variables solo de movimiento (por ejemplo, std::unique_ptr) del ámbito circundante y usarlas en una expresión lambda.  
  
```cpp  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### <a name="parameter-list"></a>Lista de parámetros  
 Además de capturar variables, una expresión lambda puede aceptar parámetros de entrada. Una lista de parámetros (*declarador de expresión lambda* en la sintaxis estándar) es opcional y en la mayoría de los aspectos es similar a la lista de parámetros para una función.  
  
```cpp  
auto y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 En **C++ 14**, si el tipo de parámetro es genérico, puede utilizar la palabra clave auto como el especificador de tipo. Esto indica al compilador que debe crear el operador de llamada de función como plantilla. Cada instancia de "auto" en una lista de parámetros es equivalente a un parámetro de tipo distinto.  
  
```cpp  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 Una expresión lambda puede tomar otra expresión lambda como argumento. Para obtener más información, vea "Expresiones Lambda de orden superior" en el tema [ejemplos de expresiones Lambda](../cpp/examples-of-lambda-expressions.md).  
  
 Dado que una lista de parámetros es opcional, puede omitir los paréntesis vacíos si no se pasan argumentos a la expresión lambda y su declarador de expresión lambda no contiene *especificación de excepción*,  *tipo de valor devuelto finales*, o `mutable`.  
  
### <a name="mutable-specification"></a>Especificación mutable  
 Normalmente, el operador de llamada a función de una expresión lambda es const-by-value, pero `mutable` lo cancela. No genera miembros de datos mutable. La especificación mutable permite al cuerpo de una expresión lambda modificar las variables que se capturan por valor. Algunos de los ejemplos que se incluyen más adelante en este artículo muestran el uso de la palabra clave `mutable`.  
  
### <a name="exception-specification"></a>Especificación de la excepción  
 Puede utilizar la especificación de excepción `noexcept` para indicar que la expresión lambda no produce ninguna excepción. Como con las funciones normales, el compilador de Visual C++ genera la advertencia [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) si una expresión lambda declara la `noexcept` una especificación de excepción y el cuerpo de la expresión lambda produce una excepción, como se muestra aquí:  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() noexcept { throw 5; }();  
}  
```  
  
 Para obtener más información, consulte [especificaciones de excepciones (throw)](../cpp/exception-specifications-throw-cpp.md).  
  
### <a name="return-type"></a>Tipo devuelto  
 El tipo de valor devuelto de una expresión lambda se deduce automáticamente. No tiene que usar el [automática](../cpp/auto-cpp.md) palabra clave a menos que especifique una *trailing-return-type*. El *trailing-return-type* es similar a la parte de tipo de valor devuelto de un método o función normal. Pero el tipo de valor devuelto debe seguir la lista de parámetros y debe incluir la palabra clave trailing-return-type `->` antes del tipo de valor devuelto.  
  
 Puede omitir la parte return-type de una expresión lambda si el cuerpo de la expresión lambda contiene una sola instrucción return o si la expresión lambda no devuelve un valor. Si el cuerpo de la expresión lambda contiene una instrucción return, el compilador deduce el tipo de valor devuelto del tipo de expresión return. En caso contrario, el compilador deduce que el tipo de valor devuelto es `void`. Vea los fragmentos de código de ejemplo siguientes que muestran este principio.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
```  
  
 Una expresión lambda puede generar otra expresión lambda como valor devuelto. Para obtener más información, vea "Expresiones Lambda de orden superior" en [ejemplos de expresiones Lambda](../cpp/examples-of-lambda-expressions.md).  
  
### <a name="lambda-body"></a>Cuerpo lambda  
 El cuerpo de la lambda (*compound-statement* en la sintaxis estándar) de una expresión lambda expresión puede contener todo lo que puede contener el cuerpo de un método o función normal. El cuerpo de una función normal y de una expresión lambda puede tener acceso a estos tipos de variables:  
  
-   variables capturadas en el ámbito de inclusión, tal como se describió anteriormente.  
  
-   Parámetros  
  
-   Variables declaradas localmente  
  
-   Miembros de datos de la clase (cuando se declara dentro de una clase y se captura `this`)  
  
-   Cualquier variable que tenga duración de almacenamiento estática (por ejemplo, las variables globales)  
  
 El ejemplo siguiente contiene una expresión lambda que captura explícitamente la variable `n` por valor y captura implícitamente la variable `m` por referencia:  
  
```cpp  
// captures_lambda_expression.cpp  
// compile with: /W4 /EHsc   
#include <iostream>  
using namespace std;  
  
int main()  
{  
   int m = 0;  
   int n = 0;  
   [&, n] (int a) mutable { m = ++n + a; }(4);  
   cout << m << endl << n << endl;  
}  
```  
  
```Output  
5  
0  
```  
  
 Como la variable `n` se captura por valor, el valor sigue siendo `0` después de la llamada a la expresión lambda. La especificación `mutable` permite modificar `n` dentro de la expresión lambda.  
  
 Aunque una expresión lambda solo puede capturar variables que tengan duración de almacenamiento automática, puede utilizar variables que tengan duración de almacenamiento estática en el cuerpo de una expresión lambda. En el ejemplo siguiente se utiliza la función `generate` y una expresión lambda para asignar un valor a cada elemento de un objeto `vector`. La expresión lambda modifica la variable estática para generar el valor del elemento siguiente.  
  
```cpp  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });   
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
```  
  
 Para obtener más información, consulte [generar](../standard-library/algorithm-functions.md#generate).  
  
 En el ejemplo de código siguiente se usa la función del ejemplo anterior y se agrega un ejemplo de una expresión lambda que usa el algoritmo de la biblioteca estándar de C++ `generate_n`. Esta expresión lambda asigna un elemento de un objeto `vector` a la suma de los dos elementos anteriores. Se usa la palabra clave `mutable` de modo que el cuerpo de la expresión lambda pueda modificar sus copias de las variables externas `x` e `y`, que la expresión lambda captura por valor. Como la expresión lambda captura las variables originales `x` e `y` por valor, sus valores siguen siendo `1` después de la ejecución de la expresión.  
  
```cpp  
// compile with: /W4 /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });  
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
  
int main()  
{  
    // The number of elements in the vector.  
    const int elementCount = 9;  
  
    // Create a vector object with each element set to 1.  
    vector<int> v(elementCount, 1);  
  
    // These variables hold the previous two elements of the vector.  
    int x = 1;  
    int y = 1;  
  
    // Sets each element in the vector to the sum of the   
    // previous two elements.  
    generate_n(v.begin() + 2,  
        elementCount - 2,  
        [=]() mutable throw() -> int { // lambda is the 3rd parameter  
        // Generate current value.  
        int n = x + y;  
        // Update previous two values.  
        x = y;  
        y = n;  
        return n;  
    });  
    print("vector v after call to generate_n() with lambda: ", v);  
  
    // Print the local variables x and y.  
    // The values of x and y hold their initial values because   
    // they are captured by value.  
    cout << "x: " << x << " y: " << y << endl;  
  
    // Fill the vector with a sequence of numbers  
    fillVector(v);  
    print("vector v after 1st call to fillVector(): ", v);  
    // Fill the vector with the next sequence of numbers  
    fillVector(v);  
    print("vector v after 2nd call to fillVector(): ", v);  
}  
```  
  
```Output  
vector v after call to generate_n() with lambda: 1 1 2 3 5 8 13 21 34  
x: 1 y: 1  
vector v after 1st call to fillVector(): 1 2 3 4 5 6 7 8 9  
vector v after 2nd call to fillVector(): 10 11 12 13 14 15 16 17 18  
```  
  
 Para obtener más información, consulte [generate_n](../standard-library/algorithm-functions.md#generate_n).  

## <a name="constexpr-lambda-expressions"></a>expresiones lambda constexpr
**Visual Studio 2017 15,3 y versiones posteriores** (disponible con [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): una expresión lambda se puede declarar como `constexpr` o se usa en una expresión constante cuando la inicialización de cada miembro de datos que TI captura o presenta se permite dentro de una expresión constante.  

```cpp
    int y = 32;
    auto answer = [y]() constexpr 
    {
        int x = 10;
        return y + x; 
    };

    constexpr int Increment(int n) 
    {
        return [n] { return n + 1; }();
    }

``` 
Una expresión lambda es implícitamente `constexpr` si su resultado satisface los requisitos de un `constexpr` función:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Si una expresión lambda es implícita o explícitamente `constexpr`, conversión a un puntero a función genera un `constexpr` función:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="microsoft-specific"></a>Específico de Microsoft  
 Las expresiones lambda no se admite en las entidades administradas siguientes de Common Language Runtime (CLR): `ref class`, `ref struct`, `value class` o `value struct`.  
  
 Si está utilizando un modificador específico de Microsoft como [__declspec](../cpp/declspec.md), puede insertarlo en una expresión lambda inmediatamente después de la `parameter-declaration-clause`, por ejemplo:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Para determinar si un modificador es compatible con las expresiones lambda, vea el artículo sobre él en el [modificadores específicos de Microsoft](../cpp/microsoft-specific-modifiers.md) sección de la documentación.  
  
 Además de C ++ 11 funcionalidad de expresiones lambda del estándar, Visual Studio es compatible con expresiones lambda sin estado, que se pueden convertir a punteros de función que usan convenciones de llamada arbitrarias.  
  
## <a name="see-also"></a>Vea también  
 [Referencia del lenguaje C++](../cpp/cpp-language-reference.md)   
 [Objetos de función en la biblioteca estándar de C++](../standard-library/function-objects-in-the-stl.md)   
 [Llamada de función](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
