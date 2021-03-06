---
title: Location (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
dev_langs:
- C++
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fdfb555375df4b9f791db25fa2dee47222f79063
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="location-class"></a>location (Clase)
Una abstracción de una ubicación física en el hardware.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class location;
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[Ubicación](#ctor)|Sobrecargado. Construye un objeto `location`.|  
|[~ location (destructor)](#dtor)|Destruye un objeto `location`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[Actual](#current)|Devuelve un `location` objeto que representa el lugar más específico que se está ejecutando el subproceso que realiza la llamada.|  
|[from_numa_node](#from_numa_node)|Devuelve un `location` el objeto que representa un nodo NUMA.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[operator!=](#operator_neq)|Determina si dos `location` objetos representan otra ubicación.|  
|[operator=](#operator_eq)|Asigna el contenido de otra matriz `location` objeto a este.|  
|[operator==](#operator_eq_eq)|Determina si dos `location` objetos representan la misma ubicación.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `location`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** concrt.h  
  
 **Espacio de nombres:** simultaneidad  
  
##  <a name="dtor"></a> ~ ubicación 

 Destruye un objeto `location`.  
  
```
~location();
```  
  
##  <a name="current"></a> Actual 

 Devuelve un `location` objeto que representa el lugar más específico que se está ejecutando el subproceso que realiza la llamada.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Una ubicación que representa la ubicación más específica en la que está ejecutando el subproceso que realiza la llamada.  
  
##  <a name="from_numa_node"></a> from_numa_node 

 Devuelve un `location` el objeto que representa un nodo NUMA.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>Parámetros  
 `_NumaNodeNumber`  
 El número de nodo NUMA para construir una ubicación para.  
  
### <a name="return-value"></a>Valor devuelto  
 Una ubicación que representa el nodo NUMA especificado por el `_NumaNodeNumber` parámetro.  
  
##  <a name="ctor"></a> Ubicación 

 Construye un objeto `location`.  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>Comentarios  
 Una ubicación construido de forma predeterminada representa el sistema como un todo.  
  
##  <a name="operator_neq"></a> operador! = 

 Determina si dos `location` objetos representan otra ubicación.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parámetros  
 `_Rhs`  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si son diferentes, las dos ubicaciones `false` en caso contrario.  
  
##  <a name="operator_eq"></a> operator= 

 Asigna el contenido de otra matriz `location` objeto a este.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Rhs`  
 Objeto `location` de origen.  
  
### <a name="return-value"></a>Valor devuelto  
  
##  <a name="operator_eq_eq"></a> operador == 

 Determina si dos `location` objetos representan la misma ubicación.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parámetros  
 `_Rhs`  
  
### <a name="return-value"></a>Valor devuelto  
 `true` Si las dos ubicaciones son idénticas, y `false` en caso contrario.  
  
## <a name="see-also"></a>Vea también  
 [concurrency (espacio de nombres)](concurrency-namespace.md)
