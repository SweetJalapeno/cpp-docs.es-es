---
title: unsupported_feature (clase) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
dev_langs:
- C++
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ccc811e3459fe668b6a8dbd255007cb60bf0cf1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="unsupportedfeature-class"></a>unsupported_feature (Clase)
La excepción que se produce cuando se usa una característica no compatible.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[unsupported_feature Constructor](#ctor)|Crea una nueva instancia de la `unsupported_feature` excepción.|  

  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## <a name="unsupported_feature__ctor"></a> unsupported_feature 

  Crea una nueva instancia de la excepción unsupported_feature.  
  
### <a name="syntax"></a>Sintaxis  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Parámetros  
 `_Message`  
 Descripción del error.  
  
### <a name="return-value"></a>Valor devuelto  
 Objeto `unsupported_feature`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** amprt.h  
  
 **Espacio de nombres:** Concurrency  
  
## <a name="see-also"></a>Vea también  
 [Espacio de nombres de simultaneidad (C++ AMP)](concurrency-namespace-cpp-amp.md)
