---
title: Backinsertiterator (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
dev_langs:
- C++
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0be32b550cd0e19facb127ca6a052b03ef1eaf5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Collections::BackInsertIterator (Clase)
Representa un iterador que inserta, en lugar de sobrescribir, elementos en el back-end de una colección secuencial.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <typename T>  
class BackInsertIterator : 
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 El tipo de elemento de la colección actual.  
  
### <a name="remarks"></a>Comentarios  
 La clase BackInsertIterator implementa las reglas requeridas por [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md).  
  
### <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[Backinsertiterator](#ctor)|Inicializa una nueva instancia de la clase BackInsertIterator.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[BackInsertIterator::operator* (Operador)](#operator-dereference)|Recupera una referencia al objeto BackInsertIterator actual.|  
|[BackInsertIterator::operator++ (Operador)](#operator-increment)|Devuelve una referencia al objeto BackInsertIterator actual. El iterador no se modifica.|  
|[BackInsertIterator::operator= (Operador)](#operator-assign)|Anexa el objeto especificado al final de la colección secuencial actual.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `BackInsertIterator`  
  
### <a name="requirements"></a>Requisitos  
 **Encabezado:** collection.h  
  
 **Espacio de nombres:** Platform::Collections  
  
---
## <a name="ctor"></a>  Constructor Backinsertiterator
Inicializa una nueva instancia de la clase `BackInsertIterator`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `v`  
 Un IVector\<T > objeto.  
  
### <a name="remarks"></a>Comentarios  
 Un objeto `BackInsertIterator` inserta elementos a continuación del último elemento del objeto especificado por el parámetro `v`.  
 
## <a name="operator-assign"></a>  Backinsertiterator:: operator = (operador)
Anexa el objeto especificado al final de la colección secuencial actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```    
BackInsertIterator& operator=( const T& t);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `t`  
 El objeto que se va a anexar a la colección actual.  
  
### <a name="return-value"></a>Valor devuelto  
 Referencia al objeto BackInsertIterator actual.  

## <a name="operator-dereference"></a>  Operador de backinsertiterator:: operator
Recupera una referencia al objeto BackInsertIterator actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BackInsertIterator& operator*();  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Referencia al objeto BackInsertIterator actual.  
  
### <a name="remarks"></a>Comentarios  
 Este operador devuelve una referencia al objeto BackInsertIterator actual, no así a ningún elemento de la colección actual.  
 
## <a name="operator-increment"></a>  Backinsertiterator:: operator ++ (operador)
Devuelve una referencia al objeto BackInsertIterator actual. El iterador no se modifica.  
  
## <a name="syntax"></a>Sintaxis  
  
``` 
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(int);  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Referencia al objeto BackInsertIterator actual.  
  
### <a name="remarks"></a>Comentarios  
 Por diseño, el primero ejemplo de sintaxis incrementa previamente el objeto BackInsertIterator actual y el segundo lo incrementa posteriormente. El tipo `int` de la segunda sintaxis indica una operación de incremento posterior, no un operando entero real.  
  
 Sin embargo, este operador no modifica realmente el objeto BackInsertIterator. En su lugar, este operador devuelve una referencia al iterador actual sin modificar. Este es el mismo comportamiento que [operador *](#dereference-operator).  
  
  
## <a name="see-also"></a>Vea también  
 [Namespace de plataforma](platform-namespace-c-cx.md)