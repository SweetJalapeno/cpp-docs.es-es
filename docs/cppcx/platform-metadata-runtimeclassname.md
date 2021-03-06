---
title: Platform::Metadata::RuntimeClassName | Documentos de Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 297a5089af7db43d837934e864e0925cd7b34a3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName
Cuando se aplica a una definición de clase, garantiza que una clase privada devuelva un nombre válido de la función GetRuntimeClassName.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### <a name="parameters"></a>Parámetros  
 name  
  
 El nombre de un tipo público existente visible en Windows en tiempo de ejecución.  
  
### <a name="remarks"></a>Comentarios  
 Usa este atributo en clases ref privadas para especificar un nombre de tipo en tiempo de ejecución personalizado o cuando el nombre existente no cumpla los requisitos. Especifica como nombre una interfaz pública que la clase implementa.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el atributo. En este ejemplo, el nombre del tipo en tiempo de ejecución de HellowWorldImpl es Test::Native::MyComponent::IHelloWorld  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Platform::Metadata (Espacio de nombres)](../cppcx/platform-metadata-namespace.md)