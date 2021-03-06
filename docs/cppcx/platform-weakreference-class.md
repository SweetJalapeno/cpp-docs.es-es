---
title: WeakReference (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8db5c855b6a377a0202183d48b8fd34e93b6072
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="platformweakreference-class"></a>Platform::WeakReference (Clase)
Representa una referencia débil a una instancia de una clase ref.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp 
class WeakReference  
```  
  
#### <a name="parameters"></a>Parámetros  
  
### <a name="members"></a>Miembros  
  
### <a name="constructors"></a>Constructores  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[WeakReference](#ctor)|Inicializa una nueva instancia de la clase WeakReference.|  
  
### <a name="methods"></a>Métodos  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[WeakReference:: Resolve](#resolve)|Devuelve un identificador a la clase ref subyacente o nullptr si el objeto ya no existe.|  
  
### <a name="operators"></a>Operadores  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[WeakReference::operator=](#operator-assign)|Asigna un nuevo valor al objeto WeakReference.|  
|[WeakReference::operator BoolType](#booltype)|Implementa el patrón bool seguro.|  
  
### <a name="remarks"></a>Comentarios  
 La clase WeakReference no es una clase ref y, por tanto, no hereda de Platform::Object^ y no se puede usar en la firma de un método público.  

## <a name="operator-assign"></a> WeakReference::operator =
Asigna un valor a WeakReference.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));    
WeakReference& operator=(const WeakReference& otherArg);   
WeakReference& operator=(WeakReference&& otherArg);    
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg); 
```  
  
### <a name="remarks"></a>Comentarios  
 La última sobrecarga de la lista permite asignar una clase ref a una variable WeakReference. En este caso es convierte en la clase ref [Platform:: Object](../cppcx/platform-object-class.md)^. Restablecer el tipo original más adelante especificándolo como argumento para el parámetro de tipo en la [WeakReference\<T >](#resolve) función miembro.  
  
## <a name="booltype"></a> WeakReference::operator BoolType
Implementa el patrón bool seguro para la clase WeakReference. No debes llamarlo explícitamente en el código.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
BoolType BoolType()  
```  

## <a name="resolve"></a> WeakReference:: Resolve (método) (espacio de nombres de plataforma)
Devuelve un identificador a la clase ref original o `nullptr` si el objeto ya no existe.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### <a name="parameters"></a>Parámetros  
  
### <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 Identificador de la clase ref a la que se asoció previamente el objeto WeakReference o nullptr.  
  
### <a name="example"></a>Ejemplo  
 Esta es la descripción para un ejemplo de código.  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 Ten en cuenta que el parámetro de tipo es T, no T^.  
  
 
## <a name="ctor"></a> Constructor de WeakReference
Proporciona distintas formas de crear un objeto WeakReference.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& otherArg);  
WeakReference(WeakReference&& otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);  
```  
### <a name="example"></a>Ejemplo  
  
```cpp    
MyClass^ mc = ref new MyClass();  
WeakReference wr(mc);  
MyClass^ copy2 = wr.Resolve<MyClass>();    
```  
  
## <a name="see-also"></a>Vea también  
 [Espacio de nombres de plataforma](../cppcx/platform-namespace-c-cx.md)