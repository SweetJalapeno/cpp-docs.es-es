---
title: Identificador a un operador de objeto (^) (extensiones de componentes de C++) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb322f83163a9faf3314990baabbd0a34f1a67ae
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="handle-to-object-operator---c-component-extensions"></a>Operador de identificador de objeto (^) (Extensiones de componentes de C++)
El *declarador del identificador* (`^`, pronunciado "sombrero"), modifica el tipo [especificador](../cpp/overview-of-declarators.md) para indicar que el objeto declarado debe eliminarse automáticamente cuando el sistema determina que el objeto es ya no es accesible.  
  
## <a name="accessing-the-declared-object"></a>Acceso al objeto declarado  
 Una variable que se declara con el declarador de identificador se comporta como un puntero al objeto. Sin embargo, la variable apunta al objeto completo, no puede apuntar a un miembro del objeto y no admite la aritmética con punteros. Utilice el operador de direccionamiento indirecto (`*`) para tener acceso al objeto y el operador de acceso de miembro de flecha (`->`) para tener acceso a un miembro del objeto.  
  
## <a name="windows-runtime"></a>Windows en tiempo de ejecución  
 El compilador utiliza el COM *recuento de referencias* mecanismo para determinar si el objeto ya no se está usando y se puede eliminar. Esto es posible debido a que un objeto que se deriva de una interfaz de Windows Runtime es, en realidad, un objeto COM. El recuento de referencias se incrementa cuando se crea o se copia el objeto y se reduce cuando el objeto se establece en null o queda fuera de ámbito. Si el recuento de referencias llega a cero, el objeto se elimina de inmediato y de manera automática.  
  
 La ventaja del declarador del identificador es que, en COM, debe administrar de manera explícita el recuento de referencias para un objeto, lo cual es un proceso tedioso que puede dar lugar a errores. Es decir, para aumentar y disminuir el recuento de referencias, debe invocar los métodos AddRef() y Release() del objeto. Sin embargo, si declara un objeto con el declarador de identificador, el compilador de Visual C++ genera código que ajusta de manera automática el recuento de referencias.  
  
 Para obtener información sobre cómo crear una instancia de un objeto, vea [referencia nuevos](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
## <a name="requirements"></a>Requisitos  
 Opción del compilador: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 El sistema utiliza el CLR *recolector de elementos no utilizados* mecanismo para determinar si el objeto ya no se está usando y se puede eliminar. Common Language Runtime mantiene un montón donde asigna objetos y usa las referencias administradas (variables) del programa para indicar la ubicación de objetos en el montón. Cuando un objeto ya no se usa, se libera la memoria que ocupaba en el montón. De manera periódica, el recolector de elementos no utilizados compacta el montón para mejorar el uso de la memoria liberada. Al compactar el montón, se pueden mover sus objetos, lo que invalida las ubicaciones que usan las referencias administradas. Sin embargo, el recolector de elementos no utilizados reconoce la ubicación de todas las referencias administradas y las actualiza automáticamente para indicar la ubicación actual de los objetos en el montón.  
  
 Dado que los punteros de C++ nativo (`*`) y las referencias (`&`) no son referencias administradas, el recolector de elementos no utilizados no puede actualizar de manera automática las direcciones a las que apuntan. Para solucionar este problema, utilice el declarador de identificador para especificar una variable que el recolector de elementos no utilizados reconozca y pueda actualizar automáticamente.  
  
 En Visual C++ 2002 y Visual C++ 2003, se utiliza `__gc *` para declarar un objeto del montón administrado.  `^` reemplaza a `__gc *` en la nueva sintaxis.  
  
 Para obtener más información, consulte [Cómo: declarar controla en tipos nativos](../dotnet/how-to-declare-handles-in-native-types.md).  
  
### <a name="examples"></a>Ejemplos  
 **Ejemplo**  
  
 En este ejemplo se muestra cómo crear una instancia de un tipo de referencia en el montón administrado.  En este ejemplo se muestra también que puede inicializar un identificador con otro, lo que da a lugar a dos referencias al mismo objeto en el montón de recolección de elementos no utilizados administrado. Tenga en cuenta que asignar [nullptr](../windows/nullptr-cpp-component-extensions.md) a un identificador no marca el objeto de colección de elementos no utilizados.  
  
```  
// mcppv2_handle.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   MyClass() : i(){}  
   int i;  
   void Test() {  
      i++;  
      System::Console::WriteLine(i);  
   }  
};  
  
int main() {  
   MyClass ^ p_MyClass = gcnew MyClass;  
   p_MyClass->Test();  
  
   MyClass ^ p_MyClass2;  
   p_MyClass2 = p_MyClass;  
  
   p_MyClass = nullptr;  
   p_MyClass2->Test();     
}  
```  
  
 **Salida**  
  
```Output  
1  
2  
```  
  
 **Ejemplo**  
  
 En el ejemplo siguiente se muestra cómo declarar un identificador para un objeto del montón administrado, donde el tipo de objeto es un tipo de valor de conversión boxing. En el ejemplo también se muestra cómo obtener el tipo de valor del objeto al que se ha aplicado la conversión boxing.  
  
```  
// mcppv2_handle_2.cpp  
// compile with: /clr  
using namespace System;  
  
void Test(Object^ o) {  
   Int32^ i = dynamic_cast<Int32^>(o);  
  
   if(i)  
      Console::WriteLine(i);  
   else  
      Console::WriteLine("Not a boxed int");  
}  
  
int main() {  
   String^ str = "test";  
   Test(str);  
  
   int n = 100;  
   Test(n);  
}  
```  
  
 **Salida**  
  
```Output  
Not a boxed int  
100  
```  
  
 **Ejemplo**  
  
 En este ejemplo se muestra que la expresión común de C++ de usar un puntero void* para apuntar a un objeto arbitrario se reemplaza por Object^, que puede contener un identificador para cualquier clase de referencia. También se muestra que todos los tipos, como matrices y delegados, pueden convertirse en un identificador de objeto.  
  
```  
// mcppv2_handle_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
public delegate void MyDel();  
ref class MyClass {  
public:  
   void Test() {}  
};  
  
void Test(Object ^ x) {  
   Console::WriteLine("Type is {0}", x->GetType());  
}  
  
int main() {  
   // handle to Object can hold any ref type  
   Object ^ h_MyClass = gcnew MyClass;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(gcnew MyClass);  
  
   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);  
   Test(arr);  
  
   Int32 ^ bi = 1;  
   Test(bi);  
  
   MyClass ^ h_MyClass2 = gcnew MyClass;  
  
   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);  
   Test(DelInst);  
}  
```  
  
 **Salida**  
  
```Output  
Type is System.Collections.ArrayList  
  
Type is System.Int32  
  
Type is MyDel  
```  
  
 **Ejemplo**  
  
 En este ejemplo se muestra que se puede deshacer la referencia de un identificador y se puede tener acceso a un miembro mediante un identificador sin referencia.  
  
```  
// mcppv2_handle_4.cpp  
// compile with: /clr  
using namespace System;  
value struct DataCollection {  
private:  
   int Size;  
   array<String^>^ x;  
  
public:  
   DataCollection(int i) : Size(i) {  
      x = gcnew array<String^>(Size);  
      for (int i = 0 ; i < Size ; i++)  
         x[i] = i.ToString();  
   }  
  
   void f(int Item) {  
      if (Item >= Size)  
      {  
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);  
         return;  
      }  
      else  
         System::Console::WriteLine("Array value: {0}", x[Item]);  
   }  
};  
  
void f(DataCollection y, int Item) {  
   y.f(Item);  
}  
  
int main() {  
   DataCollection ^ a = gcnew DataCollection(10);  
   f(*a, 7);   // dereference a handle, return handle's object  
   (*a).f(11);   // access member via dereferenced handle  
}  
```  
  
 **Salida**  
  
```Output  
Array value: 7  
  
Cannot access array element 11, size is 10  
```  
  
 **Ejemplo**  
  
 En este ejemplo se muestra que no se puede enlazar una referencia nativa (`&`) a un miembro `int` de un tipo administrado, ya que `int` se podría almacenar en el montón de recolección de elementos no utilizados y las referencias nativas no realizan un seguimiento del movimiento de objetos en el montón administrado. La solución es utilizar una variable local o cambiar `&` a `%`, convirtiéndola en una referencia de seguimiento.  
  
```  
// mcppv2_handle_5.cpp  
// compile with: /clr  
ref struct A {  
   void Test(unsigned int &){}  
   void Test2(unsigned int %){}  
   unsigned int i;  
};  
  
int main() {  
   A a;  
   a.i = 9;  
   a.Test(a.i);   // C2664  
   a.Test2(a.i);   // OK  
  
   unsigned int j = 0;  
   a.Test(j);   // OK  
}  
```  
  
### <a name="requirements"></a>Requisitos  
 Opción del compilador: **/clr**  
  
## <a name="see-also"></a>Vea también  
 [Extensiones de componentes para plataformas de tiempo de ejecución](../windows/component-extensions-for-runtime-platforms.md)   
 [Operador de referencia de seguimiento](../windows/tracking-reference-operator-cpp-component-extensions.md)