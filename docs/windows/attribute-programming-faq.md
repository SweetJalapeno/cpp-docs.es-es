---
title: Preguntas más frecuentes de programación de atributo | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributed programming
- attributes [C++], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35b57c8813778cf0bbf8efbfcbee8466074b87f0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="attribute-programming-faq"></a>Preguntas más frecuentes de programación con atributos
En este tema responde a las siguientes preguntas más frecuentes:  
  
-   [¿Qué es un valor HRESULT?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Si es necesario especificar el nombre del parámetro de un atributo](#vcconattributeprogrammmingfaqanchor2)  
  
-   [¿Puedo utilizar comentarios en un bloque de atributos?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [¿Cómo interactúan los atributos con la herencia?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [¿Cómo se puede usar atributos en un proyecto ATL sin atributos?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [¿Cómo se puede usar un archivo .idl en un proyecto con atributos?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [¿Puedo modificar código insertado por un atributo?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [¿Cómo declarar al día una interfaz con atributos?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [¿Puedo usar atributos en una clase derivada de una clase que también utiliza atributos?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> ¿Qué es un valor HRESULT?  
 Un `HRESULT` es un tipo de datos simple que suele usarse como un valor devuelto por los atributos y ATL en general. En la tabla siguiente se describe los distintos valores. Más valores se encuentran en el archivo winerror.h archivo de encabezado.  
  
|nombre|Descripción|Valor|  
|----------|-----------------|-----------|  
|S_OK|Operación correcta|0x00000000|  
|E_UNEXPECTED|Error inesperado|0x8000FFFF|  
|E_NOTIMPL|No implementado|0 x 80004001|  
|E_OUTOFMEMORY|No se pudo asignar la memoria necesaria|0x8007000E|  
|E_INVALIDARG|Uno o varios argumentos no son válidos|0 x 80070057|  
|E_NOINTERFACE|No se admite dicha interfaz|0 x 80004002|  
|E_POINTER|Puntero no válido|0 x 80004003|  
|E_HANDLE|Identificador no válido|0x80070006|  
|E_ABORT|Operación anulada|0x80004004|  
|E_FAIL|Error no especificado|0 x 80004005|  
|E_ACCESSDENIED|Error de denegación de acceso general|0 x 80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Si es necesario especificar el nombre del parámetro de un atributo  
 En la mayoría de los casos, si el atributo tiene un único parámetro, ese parámetro se denomina. Este nombre no es necesario cuando se inserta el atributo en el código. Por ejemplo, el siguiente uso de la [agregable](../windows/aggregatable.md) atributo:  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 es exactamente igual que:  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 Sin embargo, los siguientes atributos tienen parámetros únicos sin nombre:  
  
||||  
|-|-|-|  
|[call_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[entry](../windows/entry.md)|[first_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[identificador](../windows/id.md)|  
|[iid_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[include](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last_is](../windows/last-is.md)|  
|[length_is](../windows/length-is.md)|[max_is](../windows/max-is.md)|[no_injected_text](../windows/no-injected-text.md)|  
|[pointer_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size_is](../windows/size-is.md)|[Origen](../windows/source-cpp.md)|[switch_is](../windows/switch-is.md)|  
|[switch_type](../windows/switch-type.md)|[transmit_as](../windows/transmit-as.md)|[wire_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> ¿Puedo utilizar comentarios en un bloque de atributos?  
 Puede utilizar comentarios de línea y varias líneas dentro de un bloque de atributos. Sin embargo, no se puede usar cualquier estilo de comentario dentro de los paréntesis que contienen los parámetros a un atributo.  
  
 Se permite lo siguiente:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Se permite lo siguiente:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> ¿Cómo interactúan los atributos con la herencia?  
 Clases con atributos y sin atributos se pueden heredar de otras clases, que pueden a sí mismos tener atributos o no. El resultado de derivar de una clase con atributos es el mismo que deriven de esa clase después de que el proveedor de atributos haya transformado el código. Atributos no se transmiten a derivar clases a través de la herencia de C++. Un proveedor de atributos sólo transforma el código en la proximidad de sus atributos.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> ¿Cómo se puede usar atributos en un proyecto ATL sin atributos?  
 Puede que tenga un proyecto ATL sin atributos, que tiene un archivo .idl, y desea empezar a agregar objetos con atributos. En este caso, utilice al Asistente para agregar clases para proporcionar el código.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> ¿Cómo se puede usar un archivo .idl en un proyecto con atributos?  
 Puede tener un archivo .idl que desea usar en un proyecto ATL con atributos. En este caso, usaría el [importidl](../windows/importidl.md) atributo, compile el archivo .idl en un archivo .h (vea la [páginas de propiedades MIDL](../ide/midl-property-pages.md) en el cuadro de diálogo páginas de propiedades del proyecto) y, a continuación, incluya el archivo .h del proyecto .  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> ¿Puedo modificar código insertado por un atributo?  
 Algunos atributos insertan código en el proyecto. También puede ver el código insertado utilizando el [/Fx](../build/reference/fx-merge-injected-code.md) opción del compilador. También es posible copiar código del archivo insertado y péguelo en el código fuente. Esto le permite modificar el comportamiento del atributo. Sin embargo, tendrá que modificar otras partes del código también.  
  
 El ejemplo siguiente es el resultado de copiar código insertado en un archivo de código fuente:  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
]  
  
class ATL_NO_VTABLE CTestTest : public ITestTest,  
// the following base classes support added injected code  
public IConnectionPointContainerImpl<CTestTest>,  
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>  
{  
public:  
   CTestTest() {  
   }  
   // this line would be commented out from original file  
   // __event __interface _ITestTestEvents;  
   DECLARE_PROTECT_FINAL_CONSTRUCT()  
   HRESULT FinalConstruct() {  
      return S_OK;  
   }  
  
void FinalRelease() {}  
  
public:  
   CComBSTR m_value;  
   STDMETHOD(DoTest)(BSTR str) {  
      VARIANT_BOOL bCancel = FALSE;  
      BeforeChange(str,&bCancel);  
      if (bCancel) {  
          return Error("Error : Someone don't want us to change the value");  
      }  
  
     m_value =str;  
     return S_OK;  
    }  
// the following was copied in from the injected code.  
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {  
   HRESULT hr = S_OK;  
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;  
   VARIANT rgvars[2];  
   Lock();  
   IUnknown** pp = p->m_vec.begin();  
   Unlock();  
   while (pp < p->m_vec.end()) {  
      if (*pp != NULL) {  
         IDispatch* pDispatch = (IDispatch*) *pp;  
         ::VariantInit(&rgvars[1]);  
         rgvars[1].vt = VT_BSTR;  
         V_BSTR(&rgvars[1])= (BSTR) i1;  
         ::VariantInit(&rgvars[0]);  
         rgvars[0].vt = (VT_BOOL | VT_BYREF);  
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;  
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };  
         VARIANT ret_val;  
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);  
         if (FAILED(hr))  
            break;  
      }  
      pp++;  
   }  
   return hr;  
}  
  
BEGIN_CONNECTION_POINT_MAP(CTestTest)  
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))  
END_CONNECTION_POINT_MAP()  
// end added code section  
  
// _ITestCtrlEvents Methods  
public:  
};  
  
int main() {}  
```  
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> ¿Cómo declarar al día una interfaz con atributos?  
 Si va a realizar una declaración adelantada de una interfaz con atributos, debe aplicar los mismos atributos a la declaración adelantada que se aplican a la declaración de interfaz reales. También debe aplicar la [exportar](../windows/export.md) atribuir a la declaración adelantada.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> ¿Puedo usar atributos en una clase derivada de una clase que también utiliza atributos?  
 No, no se admite el uso de atributos en una clase derivada de una clase que también utiliza atributos.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos](../windows/attributed-programming-concepts.md)