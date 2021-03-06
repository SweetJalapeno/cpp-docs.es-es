---
title: _com_ptr_t::CreateInstance | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70ccd73980295bdda67a4c49d034b6d185d2d93c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Específicos de Microsoft**  
  
 Crea una nueva instancia de un objeto, dado un **CLSID** o **ProgID**.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `rclsid`  
 El **CLSID** de un objeto.  
  
 `clsidString`  
 Una cadena Unicode que contiene un **CLSID** (a partir de "**{**") o un **ProgID**.  
  
 `clsidStringA`  
 Cadena multibyte, en la página de códigos ANSI, que contiene un **CLSID** (a partir de "**{**") o un **ProgID**.  
  
 `dwClsContext`  
 Contexto para el código ejecutable.  
  
 `pOuter`  
 El desconocido externo para [agregaciones](../atl/aggregation.md).  
  
## <a name="remarks"></a>Comentarios  
 Estas funciones de miembro llaman a `CoCreateInstance` para crear un nuevo objeto CM y, a continuación, consultas para el tipo de interfaz de este puntero inteligente. El puntero resultante se encapsula dentro de este objeto `_com_ptr_t`. **Versión** se llama para disminuir el recuento de referencias para el puntero previamente encapsulado. Esta rutina devuelve `HRESULT` para indicar si la operación se ha realizado de forma correcta o no.  
  
-   **CreateInstance (** `rclsid` **,**`dwClsContext`**)** crea una nueva instancia de ejecución de un objeto, dado un **CLSID**.        
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** crea una nueva instancia de ejecución de un objeto que proporciona una cadena Unicode que contiene un **CLSID**(a partir de "**{**") o un **ProgID**.        
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** crea una nueva instancia de ejecución de un objeto que proporciona una cadena de caracteres multibyte que contiene un **CLSID**  (a partir de "**{**") o un **ProgID**.       Llamadas [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), lo que supone que la cadena está en la página de códigos ANSI en lugar de una página de códigos OEM.  
  
 **FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [_com_ptr_t (Clase)](../cpp/com-ptr-t-class.md)