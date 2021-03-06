---
title: Funciones globales de seguridad | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad9ad170706b72c9d236e095db0e2b6df00031ff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="security-global-functions"></a>Funciones globales de seguridad
Estas funciones proporcionan compatibilidad para modificar objetos de SID y ACL.  
  
> [!IMPORTANT]
>  Las funciones se enumeran en la tabla siguiente no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
|||  
|-|-|  
|[AtlGetDacl](#atlgetdacl)|Llame a esta función para recuperar la información de la lista de control de acceso discrecional (DACL) de un objeto especificado.|  
|[AtlSetDacl](#atlsetdacl)|Llame a esta función para definir la información de la lista de control de acceso discrecional (DACL) de un objeto especificado.|  
|[AtlGetGroupSid](#atlgetgroupsid)|Llame a esta función para recuperar el identificador de seguridad (SID) de grupo de un objeto.|  
|[AtlSetGroupSid](#atlsetgroupsid)|Llame a esta función para definir el identificador de seguridad (SID) de grupo de un objeto.|  
|[AtlGetOwnerSid](#atlgetownersid)|Llame a esta función para recuperar el identificador de seguridad (SID) del propietario de un objeto.|  
|[AtlSetOwnerSid](#atlsetownersid)|Llame a esta función para definir el identificador de seguridad (SID) del propietario de un objeto.|  
|[AtlGetSacl](#atlgetsacl)|Llame a esta función para recuperar la información de la lista de control de acceso del sistema (SACL) de un objeto especificado.|  
|[AtlSetSacl](#atlsetsacl)|Llame a esta función para definir la información de la lista de control de acceso del sistema (SACL) de un objeto especificado.|  
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|Llame a esta función para recuperar el descriptor de seguridad de un objeto especificado.|  

## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlgetdacl"></a>  AtlGetDacl  
 Llame a esta función para recuperar la información de la lista de control de acceso discrecional (DACL) de un objeto especificado.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto para el que se va a recuperar la información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `pDacl`  
 Puntero a un objeto DACL que contendrá la información de seguridad recuperados.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  
  
### <a name="remarks"></a>Comentarios  
 En las compilaciones de depuración, se producirá un error de aserción si `hObject` o `pDacl` no es válido.  
  
##  <a name="atlsetdacl"></a>  AtlSetDacl  
 Llame a esta función para definir la información de la lista de control de acceso discrecional (DACL) de un objeto especificado.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto para el que se va a establecer información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `rDacl`  
 La DACL que contiene la nueva información de seguridad.  
  
 `dwInheritanceFlowControl`  
 El control de flujo de herencia. Este valor puede ser 0 (valor predeterminado), PROTECTED_DACL_SECURITY_INFORMATION o UNPROTECTED_DACL_SECURITY_INFORMATION.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  
  
### <a name="remarks"></a>Comentarios  
 En las compilaciones de depuración, se producirá un error de aserción si `hObject` no es válida, o si `dwInheritanceFlowControl` no es uno de los tres valores permitidos.  
### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlgetgroupsid"></a>  AtlGetGroupSid  
 Llame a esta función para recuperar el identificador de seguridad (SID) de grupo de un objeto.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto del que se va a recuperar la información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `pSid`  
 Puntero a un `CSid` objeto que va a contener la nueva información de seguridad.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlsetgroupsid"></a>  AtlSetGroupSid  
 Llame a esta función para definir el identificador de seguridad (SID) de grupo de un objeto.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto para el que se va a establecer información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `rSid`  
 La `CSid` objeto que contiene la nueva información de seguridad.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlgetownersid"></a>  AtlGetOwnerSid  
 Llame a esta función para recuperar el identificador de seguridad (SID) del propietario de un objeto.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto del que se va a recuperar la información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `pSid`  
 Puntero a un `CSid` objeto que va a contener la nueva información de seguridad.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlsetownersid"></a>  AtlSetOwnerSid  
 Llame a esta función para definir el identificador de seguridad (SID) del propietario de un objeto.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto para el que se va a establecer información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `rSid`  
 La `CSid` objeto que contiene la nueva información de seguridad.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlgetsacl"></a>  AtlGetSacl  
 Llame a esta función para recuperar la información de la lista de control de acceso del sistema (SACL) de un objeto especificado.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto del que se va a recuperar la información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 `pSacl`  
 Puntero a un objeto SACL que contendrá la información de seguridad recuperados.  
  
 `bRequestNeededPrivileges`  
 Si es true, la función intentará habilitar el privilegio SE_SECURITY_NAME y restaurarla en la realización.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  
  
### <a name="remarks"></a>Comentarios  
 Si `AtlGetSacl` va a ser llamado muchas veces muchos objetos diferentes, resultará más eficiente para habilitar el privilegio SE_SECURITY_NAME una vez antes de llamar a la función, con `bRequestNeededPrivileges` establecido en false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlsetsacl"></a>  AtlSetSacl  
 Llame a esta función para definir la información de la lista de control de acceso del sistema (SACL) de un objeto especificado.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 `hObject`  
 Identificador de objeto para el que se va a establecer información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la `hObject` parámetro.  
  
 *rSacl*  
 La SACL que contiene la nueva información de seguridad.  
  
 `dwInheritanceFlowControl`  
 El control de flujo de herencia. Este valor puede ser 0 (valor predeterminado), PROTECTED_SACL_SECURITY_INFORMATION o UNPROTECTED_SACL_SECURITY_INFORMATION.  
  
 `bRequestNeededPrivileges`  
 Si es true, la función intentará habilitar el privilegio SE_SECURITY_NAME y restaurarla en la realización.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  
  
### <a name="remarks"></a>Comentarios  
 En las compilaciones de depuración, se producirá un error de aserción si `hObject` no es válida, o si `dwInheritanceFlowControl` no es uno de los tres valores permitidos.  
  
 Si `AtlSetSacl` va a ser llamado muchas veces muchos objetos diferentes, resultará más eficiente para habilitar el privilegio SE_SECURITY_NAME una vez antes de llamar a la función, con `bRequestNeededPrivileges` establecido en false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 

##  <a name="atlgetsecuritydescriptor"></a>  AtlGetSecurityDescriptor  
 Llame a esta función para recuperar el descriptor de seguridad de un objeto especificado.  
  
> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
 bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>Parámetros  
 *pszObjectName*  
 Puntero a una cadena terminada en null que especifica el nombre del objeto que se va a recuperar la información de seguridad.  
  
 `ObjectType`  
 Especifica un valor de la [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) enumeración que indica el tipo de objeto identificado por la *pszObjectName* parámetro.  
  
 *pSecurityDescriptor*  
 El objeto que recibe el descriptor de seguridad solicitado.  
  
 *requestedInfo*  
 Un conjunto de [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) marcas que indican el tipo de información de seguridad para recuperar de bits. Este parámetro puede ser una combinación de los valores siguientes.  
  
 `bRequestNeededPrivileges`  
 Si es true, la función intentará habilitar el privilegio SE_SECURITY_NAME y restaurarla en la realización.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve true si la operación se realiza correctamente; de lo contrario, devuelve false.  
  
### <a name="remarks"></a>Comentarios  
 Si `AtlGetSecurityDescriptor` va a ser llamado muchas veces muchos objetos diferentes, resultará más eficiente para habilitar el privilegio SE_SECURITY_NAME una vez antes de llamar a la función, con `bRequestNeededPrivileges` establecido en false.  

### <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsecurity.h 
   
## <a name="see-also"></a>Vea también  
 [Funciones](../../atl/reference/atl-functions.md)
