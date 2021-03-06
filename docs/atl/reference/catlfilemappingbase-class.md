---
title: Clase CAtlFileMappingBase | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e315a29f72c887b5bff2e8177e7a47aed18c3fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="catlfilemappingbase-class"></a>Clase CAtlFileMappingBase
Esta clase representa un archivo asignado a memoria.  
  
> [!IMPORTANT]
>  Esta clase y sus miembros no se pueden usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|El constructor.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Destructor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Llamar a este método para copiar desde un objeto de asignación de archivos.|  
|[CAtlFileMappingBase::GetData](#getdata)|Llame a este método para obtener los datos de un objeto de asignación de archivos.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Llame a este método para devolver el identificador de archivo.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Llamar a este método para obtener el tamaño de asignación de un objeto de asignación de archivos.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Llamar a este método para crear un objeto de asignación de archivos.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Llamar a este método para crear un objeto de asignación de archivos que permite el acceso completo a todos los procesos.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Llamar a este método para devolver un identificador para el objeto de asignación de archivos.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Llame a este método para anular la asignación de un objeto de asignación de archivos.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Establece el objeto de asignación de archivos actual a otro objeto de asignación de archivos.|  
  
## <a name="remarks"></a>Comentarios  
 Asignación de archivos es la asociación del contenido de un archivo con una parte del espacio de direcciones virtuales de un proceso. Esta clase proporciona métodos para crear objetos de asignación de archivos que permiten a los programas para obtener acceso fácilmente a y compartir datos.  
  
 Para obtener más información, consulte [asignación de archivo](http://msdn.microsoft.com/library/windows/desktop/aa366556) en el SDK de Windows.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase  
 El constructor.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `orig`  
 El objeto de asignación de archivo original para copiar para crear el nuevo objeto.  
  
### <a name="remarks"></a>Comentarios  
 Crea un nuevo objeto de asignación de archivos, utilizando opcionalmente un objeto existente. Sigue siendo necesario llamar a [CAtlFileMappingBase::MapFile](#mapfile) abrir o crear el objeto de asignación de archivo para un archivo determinado.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 Destructor.  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Comentarios  
 Libera todos los recursos asignados por la clase y llama el [CAtlFileMappingBase::Unmap](#unmap) método.  
  
##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom  
 Llamar a este método para copiar desde un objeto de asignación de archivos.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `orig`  
 El objeto de asignación de archivo original que lo copien.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `S_OK` resultado correcto o error `HRESULT` en caso de error.  
  
##  <a name="getdata"></a>  CAtlFileMappingBase::GetData  
 Llame a este método para obtener los datos de un objeto de asignación de archivos.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un puntero a los datos.  
  
##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle  
 Llamar a este método para devolver un identificador para el objeto de asignación de archivos.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un identificador para el objeto de asignación de archivos.  
  
##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize  
 Llamar a este método para obtener el tamaño de asignación de un objeto de asignación de archivos.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el tamaño de asignación.  
  
### <a name="example"></a>Ejemplo  
 Vea el ejemplo de [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile  
 Llame a este método para abrir o crear un objeto de asignación de archivo para el archivo especificado.  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `hFile`  
 Identificador para el archivo desde el que se va a crear un objeto de asignación. `hFile` debe ser válido y no puede establecerse en INVALID_HANDLE_VALUE.  
  
 `nMappingSize`  
 El tamaño de asignación. Si es 0, el tamaño máximo del objeto de asignación de archivo es igual que el tamaño actual del archivo identificado por *hFile.*  
  
 `nOffset`  
 El desplazamiento del archivo donde asignación se va a comenzar. El valor de desplazamiento debe ser un múltiplo de granularidad de asignación de memoria del sistema.  
  
 `dwMappingProtection`  
 La protección que desea para la vista de archivo cuando se asigna el archivo. Vea `flProtect` en [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) en el SDK de Windows.  
  
 `dwViewDesiredAccess`  
 Especifica el tipo de acceso a la vista de archivo y, por lo tanto, la protección de las páginas asignadas por el archivo. Vea `dwDesiredAccess` en [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) en el SDK de Windows.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `S_OK` resultado correcto o error `HRESULT` en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Después de crear un objeto de asignación de archivos, el tamaño del archivo no debe superar el tamaño del objeto de asignación de archivos; Si lo hace, no todos el contenido del archivo estará disponibles para su uso compartido. Para obtener más información, consulte [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) y [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) del SDK de Windows.  
  
### <a name="example"></a>Ejemplo  
 Vea el ejemplo de [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem  
 Llamar a este método para crear un objeto de asignación de archivos que permite el acceso completo a todos los procesos.  
  
```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `nMappingSize`  
 El tamaño de asignación. Si es 0, el tamaño máximo del objeto de asignación de archivo es igual que el tamaño actual del objeto de asignación del archivo identificado por `szName.`  
  
 `szName`  
 El nombre del objeto de asignación.  
  
 *pbAlreadyExisted*  
 Señala a un valor booleano que se establece en TRUE si el objeto de asignación ya existe.  
  
 `lpsa`  
 El puntero a un **SECURITY_ATTRIBUTES** estructura que determina si los procesos secundarios puede heredar el identificador devuelto. Vea *lpAttributes* en [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) del SDK de Windows.  
  
 `dwMappingProtection`  
 La protección que desea para la vista de archivo, cuando se asigna el archivo. Vea `flProtect` en **CreateFileMapping** en el SDK de Windows.  
  
 `dwViewDesiredAccess`  
 Especifica el tipo de acceso a la vista de archivo y, por lo tanto, la protección de las páginas asignadas por el archivo. Vea `dwDesiredAccess` en [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) en el SDK de Windows.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `S_OK` resultado correcto o error `HRESULT` en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 **MapShareMem** permite que un objeto de asignación de archivos existente, creado por [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), compartir entre procesos.  
  
##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping  
 Llamar a este método para abrir un objeto de asignación de archivos con nombre para el archivo especificado.  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `szName`  
 El nombre del objeto de asignación. Si hay un identificador abierto para un objeto de asignación de archivo con este nombre y el descriptor de seguridad en el objeto de asignación no entra en conflicto con el `dwViewDesiredAccess` la operación de apertura de parámetro, se realiza correctamente.  
  
 `nMappingSize`  
 El tamaño de asignación. Si es 0, el tamaño máximo del objeto de asignación de archivo es igual que el tamaño actual del objeto de asignación del archivo identificado por `szName.`  
  
 `nOffset`  
 El desplazamiento del archivo donde asignación se va a comenzar. El valor de desplazamiento debe ser un múltiplo de granularidad de asignación de memoria del sistema.  
  
 `dwViewDesiredAccess`  
 Especifica el tipo de acceso a la vista de archivo y, por lo tanto, la protección de las páginas asignadas por el archivo. Vea `dwDesiredAccess` en [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) en el SDK de Windows.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `S_OK` resultado correcto o error `HRESULT` en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 En las compilaciones de depuración, se producirá un error de aserción si los parámetros de entrada no son válidos.  
  
##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =  
 Establece el objeto de asignación de archivos actual a otro objeto de asignación de archivos.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Parámetros  
 `orig`  
 El objeto de asignación de archivo actual.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve una referencia al objeto actual.  
  
##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap  
 Llame a este método para anular la asignación de un objeto de asignación de archivos.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `S_OK` resultado correcto o error `HRESULT` en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Vea [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) en el SDK de Windows para obtener más detalles.  
  
## <a name="see-also"></a>Vea también  
 [Clase CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)   
 [Información general de clases](../../atl/atl-class-overview.md)
