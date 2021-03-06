---
title: CArray (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
dev_langs:
- CPP
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4e4fd0106687927706b0ba303035258de7e651
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="carray-class"></a>CArray (clase)
Admite matrices que son como las matrices de C, pero pueden reducir y crecer según sea necesario dinámicamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Parámetros  
 `TYPE`  
 Parámetro de plantilla que especifica el tipo de los objetos almacenados en la matriz. `TYPE` es un parámetro que es devuelto por `CArray`.  
  
 `ARG` *_* `TYPE`  
 Parámetro de plantilla que especifica el tipo de argumento que se usa para tener acceso a objetos almacenados en la matriz. A menudo una referencia a `TYPE`. `ARG_TYPE` es un parámetro que se pasa a `CArray`.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Construye una matriz vacía.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CArray::Add](#add)|Agrega un elemento al final de la matriz; aumenta el tamaño de la matriz si es necesario.|  
|[CArray::Append](#append)|Anexa otra matriz a la matriz; aumenta la matriz si es necesario|  
|[CArray::Copy](#copy)|Copia otra matriz a la matriz; aumenta el tamaño de la matriz si es necesario.|  
|[CArray::ElementAt](#elementat)|Devuelve una referencia temporal al puntero del elemento dentro de la matriz.|  
|[CArray::FreeExtra](#freeextra)|Libera toda la memoria no usada por encima del límite superior actual.|  
|[CArray::GetAt](#getat)|Devuelve el valor en un índice dado.|  
|[CArray::GetCount](#getcount)|Obtiene el número de elementos de esta matriz.|  
|[CArray::GetData](#getdata)|Permite el acceso a los elementos de la matriz. Puede ser **NULL**.|  
|[CArray::GetSize](#getsize)|Obtiene el número de elementos de esta matriz.|  
|[CArray::GetUpperBound](#getupperbound)|Devuelve el índice válido de mayor tamaño.|  
|[CArray::InsertAt](#insertat)|Inserta un elemento (o todos los elementos de otra matriz) en un índice especificado.|  
|[CArray::IsEmpty](#isempty)|Determina si la matriz está vacía.|  
|[CArray::RemoveAll](#removeall)|Quita todos los elementos de esta matriz.|  
|[CArray::RemoveAt](#removeat)|Quita un elemento en un índice específico.|  
|[CArray::SetAt](#setat)|Establece el valor de un índice dado; la matriz no puede aumentar de tamaño.|  
|[CArray::SetAtGrow](#setatgrow)|Establece el valor de un índice dado; aumenta el tamaño de la matriz si es necesario.|  
|[CArray](#setsize)|Establece el número de elementos que contendrá esta matriz.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|Establece u obtiene el elemento en el índice especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Los índices de matriz siempre se inician en la posición 0. Puede decidir si desea corregir el límite superior o habilitar la matriz expandir cuando se agregan elementos más allá de la actual enlazado. Memoria se asigna de forma contigua al límite superior, aunque algunos elementos son nulos.  
  
> [!NOTE]
>  Mayoría de los métodos que cambiar el tamaño de un `CArray` de un objeto o agregar elementos a él usan [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) a mover elementos. Esto supone un problema porque `memcpy_s` no es compatible con los objetos que requieren que se llame el constructor. Si los elementos de la `CArray` no son compatibles con `memcpy_s`, debe crear un nuevo `CArray` del tamaño adecuado. A continuación, debe usar [CArray::Copy](#copy) y [CArray::SetAt](#setat) para rellenar la nueva matriz, ya que estos métodos usan un operador de asignación en lugar de `memcpy_s`.  
  
 Al igual que con una matriz de C, la hora de acceso de un `CArray` elemento indizado es constante y es independiente del tamaño de matriz.  
  
> [!TIP]
>  Antes de usar una matriz, use [SetSize](#setsize) para establecer su tamaño y asignarle memoria. Si no usa `SetSize`, al agregar elementos a la matriz, esta se reasigna y se copia con frecuencia. La reasignación y copia frecuentes son ineficaces y pueden fragmentar la memoria.  
  
 Si se necesita un volcado de los elementos individuales de una matriz, se debe establecer la profundidad de la [CDumpContext](../../mfc/reference/cdumpcontext-class.md) objeto a 1 o mayor.  
  
 Algunas funciones de miembro de esta llamada de clase auxiliar global, las funciones que deben personalizarse para la mayoría de los usos de la `CArray` clase. Vea el tema [aplicaciones auxiliares de clase de colección](../../mfc/reference/collection-class-helpers.md) en la sección globales y Macros de MFC.  
  
 Derivación de la clase de matriz es similar a la derivación de lista.  
  
 Para obtener más información sobre cómo usar `CArray`, vea el artículo [colecciones](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Requisitos  
 `Header:` afxtempl.h  
  
##  <a name="add"></a>  CArray::Add  
 Agrega un nuevo elemento al final de una matriz, aumentando la matriz en 1.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parámetros  
 `ARG_TYPE`  
 Parámetro de plantilla que especifica el tipo de argumentos que hacen referencia a elementos de esta matriz.  
  
 `newElement`  
 El elemento que se va a agregar a esta matriz.  
  
### <a name="return-value"></a>Valor devuelto  
 El índice del elemento agregado.  
  
### <a name="remarks"></a>Comentarios  
 Si [SetSize](#setsize) se ha utilizado con un `nGrowBy` puede asignarse valor mayor que 1, memoria adicional. Sin embargo, el límite superior aumentarán en 1 solo.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 Llame a esta función miembro para agregar el contenido de una matriz al final de la otra.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Parámetros  
 *src*  
 Origen de los elementos que se debe anexar a una matriz.  
  
### <a name="return-value"></a>Valor devuelto  
 El índice del primer elemento anexado.  
  
### <a name="remarks"></a>Comentarios  
 Las matrices deben ser del mismo tipo.  
  
 Si es necesario, **anexado** puede asignar memoria adicional para dar cabida a los elementos que se anexa a la matriz.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 Construye una matriz vacía.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Comentarios  
 La matriz aumenta de tamaño un elemento a la vez.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 Utilice esta función miembro para copiar los elementos de una matriz a otra.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Parámetros  
 *src*  
 Origen de los elementos que se copian en una matriz.  
  
### <a name="remarks"></a>Comentarios  
 Llame a esta función miembro para sobrescribir los elementos de una matriz con los elementos de otra matriz.  
  
 **Copia** no libera memoria; sin embargo, si es necesario, **copia** puede asignar memoria adicional para dar cabida a los elementos que se copian en la matriz.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 Devuelve una referencia temporal en el elemento especificado de la matriz.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Un índice de entero que es mayor o igual que 0 y menor o igual que el valor devuelto por [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Valor devuelto  
 Una referencia a un elemento de matriz.  
  
### <a name="remarks"></a>Comentarios  
 Se utiliza para implementar el operador de asignación de la izquierda para matrices.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 Libera la memoria adicional que se asignó mientras se ha aumentado la matriz.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Comentarios  
 Esta función no influye en el tamaño o el límite superior de la matriz.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [GetData](#getdata).  
  
##  <a name="getat"></a>  CArray::GetAt  
 Devuelve el elemento de matriz en el índice especificado.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 *TIPO DE*  
 Parámetro de plantilla que especifica el tipo de los elementos de matriz.  
  
 `nIndex`  
 Un índice de entero que es mayor o igual que 0 y menor o igual que el valor devuelto por [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Valor devuelto  
 El elemento de matriz actualmente en este índice.  
  
### <a name="remarks"></a>Comentarios  
 Pasar un valor negativo o un valor mayor que el valor devuelto por `GetUpperBound` dará como resultado un error de aserción.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CArray::GetCount  
 Devuelve el número de elementos de matriz.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Número de elementos de la matriz.  
  
### <a name="remarks"></a>Comentarios  
 Llame a este método para recuperar el número de elementos de la matriz. Dado que los índices son de base cero, el tamaño es mayor que el índice más grande de 1. Llamar a este método genera el mismo resultado que la [CArray::GetSize](#getsize) método.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 Utilice esta función miembro para tener acceso directo a los elementos de una matriz.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Parámetros  
 *TIPO DE*  
 Parámetro de plantilla que especifica el tipo de los elementos de matriz.  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a un elemento de matriz.  
  
### <a name="remarks"></a>Comentarios  
 Si no hay elementos disponibles, `GetData` devuelve un valor null.  
  
 Aunque el acceso directo a los elementos de una matriz puede ayudarle a trabajar más rápidamente, tenga cuidado al llamar a `GetData`; los errores que se realiza directamente afectan a los elementos de la matriz.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CArray::GetSize  
 Devuelve el tamaño de la matriz.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Comentarios  
 Dado que los índices son de base cero, el tamaño es mayor que el índice más grande de 1. Llamar a este método genera el mismo resultado que la [CArray::GetCount](#getcount) método.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 Devuelve el límite superior actual de esta matriz.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Comentarios  
 Dado que los índices de matriz son de base cero, esta función devuelve un valor de 1 menor que `GetSize`.  
  
 La condición **() GetUpperBound** = -1 indica que la matriz no contiene elementos.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>  CArray::InsertAt  
 La primera versión de `InsertAt` inserta un elemento (o varias copias de un elemento) en el índice especificado en una matriz.  
  
```  
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,  
    INT_PTR nCount = 1);
 
void InsertAt(
    INT_PTR nStartIndex,  
    CArray* pNewArray);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Un índice de entero que puede ser mayor que el valor devuelto por `GetUpperBound`.  
  
 `ARG_TYPE`  
 Parámetro de plantilla que especifica el tipo de elementos de esta matriz.  
  
 `newElement`  
 El elemento que se colocarán en esta matriz.  
  
 `nCount`  
 El número de veces que este elemento debe estar insertado (el valor predeterminado es 1).  
  
 `nStartIndex`  
 Un índice de entero que puede ser mayor que el valor devuelto por [GetUpperBound](#getupperbound).  
  
 `pNewArray`  
 Otra matriz que contiene elementos que se va a agregar a esta matriz.  
  
### <a name="remarks"></a>Comentarios  
 En el proceso, desplaza (al incrementar el índice) el elemento existente en este índice y lo pasa todos los elementos por encima de él.  
  
 La segunda versión inserta todos los elementos de otro `CArray` colección, comenzando por la `nStartIndex` posición.  
  
 El `SetAt` función, en cambio, reemplaza un elemento de la matriz especificada y desplazar los elementos.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 Determina si la matriz está vacía.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la matriz no contiene elementos; en caso contrario es 0.  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 Estos operadores de subíndice son un sustituto adecuado para la [SetAt](#setat) y [GetAt](#getat) funciones.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 *TIPO DE*  
 Parámetro de plantilla que especifica el tipo de elementos de esta matriz.  
  
 `nIndex`  
 Índice del elemento para tener acceso.  
  
### <a name="remarks"></a>Comentarios  
 El primer operador llama para las matrices que no son **const**, puede utilizarse en el (valor r) de la derecha o la izquierda (valor l) de una instrucción de asignación. El segundo, se llama para **const** arreglos de discos, puede utilizarse solo a la derecha.  
  
 La versión de la biblioteca de depuración valida si el subíndice (ya sea en el lado izquierdo o derecho de una instrucción de asignación) está fuera de límites.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 Reubica los datos a un nuevo búfer cuando se debe aumentar o reducir la matriz.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Parámetros  
 `pNewData`  
 Un nuevo búfer de la matriz de elementos.  
  
 `pData`  
 La antigua matriz de elementos.  
  
 `nCount`  
 Número de elementos de la matriz anterior.  
  
### <a name="remarks"></a>Comentarios  
 `pNewData` siempre es lo suficientemente grande como para contener todos los `pData` elementos.  
  
 El [CArray](../../mfc/reference/carray-class.md) implementación utiliza este método para copiar los datos antiguos a un nuevo búfer cuando la matriz debe aumentar o reducir (cuando [SetSize](#setsize) o [FreeExtra](#freeextra) se denominan). La implementación predeterminada sólo copia los datos.  
  
 Para las matrices en el que un elemento no contiene un puntero a uno de sus miembros u otra estructura contiene un puntero a uno de los elementos de matriz, los punteros no se actualizan en copia sin formato. En este caso, puede corregir punteros mediante la implementación de una especialización de `RelocateElements` con los tipos pertinentes. También son responsables de copiar los datos.  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 Quita todos los elementos de esta matriz.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Comentarios  
 Si la matriz está vacía, la función sigue funcionando.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>  CArray::RemoveAt  
 Quita uno o más elementos, empezando por un índice especificado en una matriz.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Un índice de entero que es mayor o igual que 0 y menor o igual que el valor devuelto por [GetUpperBound](#getupperbound).  
  
 `nCount`  
 Número de elementos que se va a quitar.  
  
### <a name="remarks"></a>Comentarios  
 En el proceso, desplaza hacia abajo todos los elementos por encima de los elementos quitados. Se reduce la esquina superior límite de la matriz, pero no libera memoria.  
  
 Si intenta quitar más elementos de los que se encuentran en la matriz por encima del punto de eliminación, se valida la versión de la biblioteca de depuración.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 Establece el elemento de matriz en el índice especificado.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Un índice de entero que es mayor o igual que 0 y menor o igual que el valor devuelto por [GetUpperBound](#getupperbound).  
  
 `ARG_TYPE`  
 Parámetro de plantilla que especifica el tipo de argumentos que se usan para hacer referencia a elementos de la matriz.  
  
 `newElement`  
 El nuevo valor del elemento que se almacenará en la posición especificada.  
  
### <a name="remarks"></a>Comentarios  
 `SetAt` no se hará que la matriz crezca. Use [SetAtGrow](#setatgrow) si desea que la matriz para crecer automáticamente.  
  
 Debe asegurarse de que el valor de índice representa una posición válida en la matriz. Si no fuera de los límites, se valida la versión de la biblioteca de depuración.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [GetAt](#getat).  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 Establece el elemento de matriz en el índice especificado.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Un índice de entero que es mayor o igual que 0.  
  
 `ARG_TYPE`  
 Parámetro de plantilla que especifica el tipo de elementos de la matriz.  
  
 `newElement`  
 El elemento que se va a agregar a esta matriz. A **NULL** se permite el valor.  
  
### <a name="remarks"></a>Comentarios  
 La matriz crece automáticamente si es necesario (es decir, el límite superior se ajusta para alojar el nuevo elemento).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  CArray  
 Establece el tamaño de una matriz vacía o existente; asigna memoria si es necesario.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parámetros  
 `nNewSize`  
 El nuevo tamaño de la matriz (número de elementos). Debe ser mayor o igual que 0.  
  
 `nGrowBy`  
 El número mínimo de ranuras de elemento para asignar si es necesario un aumento de tamaño.  
  
### <a name="remarks"></a>Comentarios  
 Si el nuevo tamaño es menor que el tamaño anterior, la matriz se trunca y se libera toda la memoria sin usar.  
  
 Utilice esta función para establecer el tamaño de la matriz antes de empezar a usar la matriz. Si no usa `SetSize`, al agregar elementos a la matriz, esta se reasigna y se copia con frecuencia. La reasignación y copia frecuentes son ineficaces y pueden fragmentar la memoria.  
  
 El `nGrowBy` parámetro afecta a la asignación de memoria interna mientras está aumentando la matriz. Su uso nunca afecta al tamaño de matriz devuelto por [GetSize](#getsize) y [GetUpperBound](#getupperbound). Si se utiliza el valor predeterminado, MFC asigna memoria de forma que se calcula para evitar la fragmentación de memoria y optimizar la eficacia de la mayoría de los casos.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [GetData](#getdata).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de MFC COLLECT](../../visual-cpp-samples.md)   
 [CObject (clase)](../../mfc/reference/cobject-class.md)   
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [CObArray (clase)](../../mfc/reference/cobarray-class.md)   
 [Aplicaciones auxiliares de clase de colección](../../mfc/reference/collection-class-helpers.md)
