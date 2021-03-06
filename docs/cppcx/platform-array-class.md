---
title: 'Clase Platform:: Array | Documentos de Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6a326db5400d8dfb335f9c9e20867a26db59b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="platformarray-class"></a>Platform::Array (Clase)
Representa una matriz unidimensional modificable que se puede recibir y pasar a través de la interfaz binaria de aplicación (ABI).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp    
template <typename T>  
private ref class Array<TArg, 1> :   
    public WriteOnlyArray<TArg, 1>,  
    public IBoxArray<TArg>   
```  
  
### <a name="members"></a>Miembros  
 Platform:: Array hereda todos sus métodos de [writeonlyarray (clase)](../cppcx/platform-writeonlyarray-class.md) e implementa la `Value` propiedad de la [iboxarray (interfaz)](../cppcx/platform-iboxarray-interface.md).  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[Constructores de matriz](#ctor)|Inicializa una matriz unidimensional modificable de tipos especificados por el parámetro de plantilla de clase *T*.|  
  
### <a name="methods"></a>Métodos  
 Vea [writeonlyarray (clase)](../cppcx/platform-writeonlyarray-class.md).  
  
### <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|[Array](#value)|Recupera un identificador a la matriz actual.|  
  
### <a name="remarks"></a>Comentarios  
 La clase Array está sellada y no se puede heredar.  
  
 El sistema de tipos en tiempo de ejecución de Windows no admite el concepto de matrices escalonadas y, por tanto, no se puede pasar un IVector < platform:: Array\<T >> como un parámetro de método o valor devuelto. Para pasar una matriz escalonada o un grupo de secuencias a través de la ABI, usa `IVector<IVector<T>^>`.  
  
 Para obtener más información acerca de cuándo y cómo usar Platform:: Array, consulte [Array y WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
 El sistema de tipos en tiempo de ejecución de Windows no admite el concepto de matrices escalonadas y, por tanto, no se puede pasar un IVector < platform:: Array\<T >> como un parámetro de método o valor devuelto. Para pasar una matriz escalonada o un grupo de secuencias a través de la ABI, usa `IVector<IVector<T>^>`.  
  
 Esta clase se define en el encabezado de vccorlib.h, que se incluye automáticamente por el compilador. Es visible en IntelliSense pero no en el Examinador de objetos porque no es un tipo público definido en platform.winmd.  
  
### <a name="requirements"></a>Requisitos  
 Opción del compilador: **/ZW**  

 
## <a name="ctor"></a>  Constructores de matriz
Inicializa una matriz unidimensional modificable de tipos especificados por el parámetro de plantilla de clase *T*.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
Array(unsigned int size);  
Array(T* data, unsigned int size);    
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 Parámetro de plantilla de clase.  
  
 `size`  
 Número de elementos de la matriz.  
  
 `data`  
 Un puntero a una matriz de datos de tipo `T` que se usa para inicializar este objeto Array.  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información acerca de cómo crear instancias de Platform:: Array, consulte [Array y WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>  Array:: Get (método)
Recupera una referencia al elemento de matriz en la ubicación de índice especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp    
T& get(unsigned int index)  const;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `index`  
 Un índice basado en cero que identifica un elemento de la matriz. El índice mínimo es 0 y el índice máximo es el valor especificado por el `size` parámetro en el [constructor Array](#ctor).  
  
### <a name="return-value"></a>Valor devuelto  
 El elemento de matriz especificado por el parámetro `index`.  
  
## <a name="value"></a>  Propiedad Array
Recupera un identificador a la matriz actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp 
property Array^ Value;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un identificador a la matriz actual.  

## <a name="see-also"></a>Vea también  
 [Espacio de nombres de plataforma](../cppcx/platform-namespace-c-cx.md)   
 [Array y WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)