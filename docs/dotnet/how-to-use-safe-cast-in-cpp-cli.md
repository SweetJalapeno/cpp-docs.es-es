---
title: 'Cómo: usar safe_cast en C++ / CLI | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f695c45d5202f376a4ce4daf14c37a7fd9a1904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-safecast-in-ccli"></a>Cómo: Usar safe_cast en C++/CLI
Este artículo muestra cómo usar safe_cast en C++ / aplicaciones de CLI. Para obtener información acerca de safe_cast en [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], consulte [safe_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
## <a name="upcasting"></a>Conversión hacia arriba  
 Una conversión hacia arriba es una conversión de un tipo derivado a una de sus clases base. Esta conversión es segura y no requiere una notación de conversión explícita. El ejemplo siguiente muestra cómo realizar una conversión hacia arriba, con `safe_cast` y sin ella.  
  
```cpp  
// safe_upcast.cpp  
// compile with: /clr  
using namespace System;  
interface class A {  
   void Test();  
};  
  
ref struct B : public A {  
   virtual void Test() {  
      Console::WriteLine("in B::Test");  
   }  
  
   void Test2() {  
      Console::WriteLine("in B::Test2");  
   }  
};  
  
ref struct C : public B {  
   virtual void Test() override {  
      Console::WriteLine("in C::Test");  
   };  
};  
  
int main() {  
   C ^ c = gcnew C;  
  
   // implicit upcast  
   B ^ b = c;  
   b->Test();  
   b->Test2();  
  
   // upcast with safe_cast  
   b = nullptr;  
   b = safe_cast<B^>(c);  
   b->Test();  
   b->Test2();  
}  
```  
  
```Output  
in C::Test  
in B::Test2  
in C::Test  
in B::Test2  
```  
  
## <a name="downcasting"></a>Convertir a tipo heredado  
 Una conversión en tipos inferiores es una conversión de una clase base para una clase que se deriva de la clase base.  Una conversión en tipos inferiores es segura sólo si el objeto que se dirige en tiempo de ejecución está solucionando realmente un objeto de clase derivada.  A diferencia de `static_cast`, `safe_cast` realiza una comprobación dinámica y produce <xref:System.InvalidCastException> si se produce un error en la conversión.  
  
```cpp  
// safe_downcast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class A { void Test(); };  
  
ref struct B : public A {  
   virtual void Test() {   
      Console::WriteLine("in B::Test()");  
   }  
  
   void Test2() {   
      Console::WriteLine("in B::Test2()");  
   }  
};  
  
ref struct C : public B {  
   virtual void Test() override {   
      Console::WriteLine("in C::Test()");  
   }  
};  
  
interface class I {};  
  
value struct V : public I {};  
  
int main() {  
   A^ a = gcnew C();  
   a->Test();  
   B^ b = safe_cast<B^>(a);  
   b->Test();  
   b->Test2();  
  
   V v;   
   I^ i = v;   // i boxes V  
   V^ refv = safe_cast<V^>(i);   
  
   Object^ o = gcnew B;  
   A^ a2= safe_cast<A^>(o);  
}  
```  
  
```Output  
in C::Test()  
in C::Test()  
in B::Test2()  
```  
  
## <a name="safecast-with-user-defined-conversions"></a>safe_cast con conversiones definidas por el usuario  
 El ejemplo siguiente muestra cómo se puede utilizar `safe_cast` para invocar conversiones definidas por el usuario.  
  
```cpp  
// safe_cast_udc.cpp  
// compile with: /clr  
using namespace System;  
value struct V;  
  
ref struct R {  
   int x;  
   R() {  
      x = 1;  
   }  
  
   R(int argx) {  
      x = argx;  
   }  
  
   static operator R::V^(R^ r);  
};  
  
value struct V {  
   int x;  
   static operator R^(V& v) {  
      Console::WriteLine("in operator R^(V& v)");  
      R^ r = gcnew R();  
      r->x = v.x;    
      return r;  
   }  
  
   V(int argx) {  
      x = argx;  
   }  
};  
  
   R::operator V^(R^ r) {  
      Console::WriteLine("in operator V^(R^ r)");  
      return gcnew V(r->x);  
   }  
  
int main() {  
   bool fReturnVal = false;  
   V v(2);  
   R^ r = safe_cast<R^>(v);   // should invoke UDC  
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC  
}  
```  
  
```Output  
in operator R^(V& v  
in operator V^(R^ r)  
```  
  
## <a name="safecast-and-boxing-operations"></a>operaciones de safe_cast y conversiones boxing  
  
### <a name="boxing"></a>Boxing  
  
 Conversión boxing se define como una conversión definida por el usuario, insertado por el compilador.  Por lo tanto, puede usar `safe_cast` que realizar una conversión de un valor en el montón CLR.  
  
 El ejemplo siguiente muestra la conversión boxing con tipos de valor simple y definido por el usuario.  Un `safe_cast` cuadros de una variable de tipo de valor que se encuentra en la pila nativa para que se puedan asignar a una variable en el montón de recolección.  
  
```cpp  
// safe_cast_boxing.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct I {};  
  
value struct V : public I {   
   int m_x;  
  
   V(int i) : m_x(i) {}  
};  
  
int main() {  
   // box a value type  
   V v(100);  
   I^ i = safe_cast<I^>(v);  
  
   int x = 100;  
   V^ refv = safe_cast<V^>(v);  
   int^ refi = safe_cast<int^>(x);  
}  
```  
  
 El ejemplo siguiente se muestra que la conversión boxing tiene prioridad sobre una conversión definida por el usuario en un `safe_cast` operación.  
  
```cpp  
// safe_cast_boxing_2.cpp  
// compile with: /clr  
static bool fRetval = true;  
  
interface struct I {};  
value struct V : public I {  
   int x;  
  
   V(int argx) {  
      x = argx;  
   }  
  
   static operator I^(V v) {  
      fRetval = false;  
      I^ pi = v;  
      return pi;  
   }  
};  
  
ref struct R {  
   R() {}  
   R(V^ pv) {}  
};  
  
int main() {  
   V v(10);  
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"  
}  
```  
  
### <a name="unboxing"></a>Conversión unboxing  
  
 Unboxing (conversión) se define como una conversión definida por el usuario, insertado por el compilador.  Por lo tanto, puede usar `safe_cast` para aplicar la conversión unboxing un valor en el montón CLR.  
  
 Conversión unboxing es una conversión definida por el usuario, pero a diferencia de la conversión boxing, unboxing (conversión) debe ser explícitas: es decir, se debe realizar un `static_cast`, estilo de C cast, o `safe_cast`; conversión unboxing no se puede realizar implícitamente.  
  
```cpp  
// safe_cast_unboxing.cpp  
// compile with: /clr  
int main() {  
   System::Object ^ o = 42;  
   int x = safe_cast<int>(o);  
}  
```  
  
 El ejemplo siguiente se muestra unboxing con tipos de valor y los tipos primitivos.  
  
```cpp  
// safe_cast_unboxing_2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct I {};  
  
value struct VI : public I {};  
  
void test1() {  
   Object^ o = 5;  
   int x = safe_cast<Int32>(o);  
}  
  
value struct V {  
   int x;  
   String^ s;  
};  
  
void test2() {  
   V localv;  
   Object^ o = localv;  
   V unboxv = safe_cast<V>(o);  
}  
  
void test3() {  
   V localv;  
   V^ o2 = localv;  
   V unboxv2 = safe_cast<V>(o2);  
}  
  
void test4() {  
   I^ refi = VI();  
   VI vi  = safe_cast<VI>(refi);  
}  
  
int main() {  
   test1();  
   test2();  
   test3();  
   test4();  
}  
```  
  
## <a name="safecast-and-generic-types"></a>safe_cast y tipos genéricos  
 El ejemplo siguiente muestra cómo se puede utilizar `safe_cast` para realizar una conversión a un tipo genérico.  
  
```cpp  
// safe_cast_generic_types.cpp  
// compile with: /clr  
interface struct I {};  
  
generic<class T> where T:I  
ref struct Base {  
   T t;  
   void test1() {}  
};  
  
generic<class T> where T:I  
ref struct Derived:public Base <T> {};  
  
ref struct R:public I {};  
  
typedef Base<R^> GBase_R;  
typedef Derived<R^> GDerived_R;  
  
int main() {  
   GBase_R^ br = gcnew GDerived_R();  
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)