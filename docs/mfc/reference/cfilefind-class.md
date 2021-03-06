---
title: Clase CFileFind | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf77a5581dd9e8c9181c61287b6032f700d7d64b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cfilefind-class"></a>Clase CFileFind
Realiza búsquedas de archivos locales y es la clase base para [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) y [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), que realizan búsquedas de archivos de Internet.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Construye un objeto `CFileFind`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Cierra la solicitud de búsqueda.|  
|[CFileFind::FindFile](#findfile)|Busca un directorio para un nombre de archivo especificado.|  
|[CFileFind::FindNextFile](#findnextfile)|Continúa una búsqueda de archivos de una llamada anterior a [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Obtiene la hora en que se creó el archivo.|  
|[CFileFind::GetFileName](#getfilename)|Obtiene el nombre, incluida la extensión del archivo se encuentra|  
|[CFileFind::GetFilePath](#getfilepath)|Obtiene la ruta de acceso completa del archivo se encuentra.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Obtiene el título del archivo se encuentra. El título no incluye la extensión.|  
|[CFileFind::GetFileURL](#getfileurl)|Obtiene la dirección URL, incluida la ruta de acceso de archivo, del archivo se encuentra.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Obtiene el tiempo de último acceso al archivo.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Obtiene la hora de última se cambia y se guardó el archivo.|  
|[CFileFind::GetLength](#getlength)|Obtiene la longitud del archivo se encuentra, en bytes.|  
|[CFileFind::GetRoot](#getroot)|Obtiene el directorio raíz del archivo se encuentra.|  
|[CFileFind::IsArchived](#isarchived)|Determina si el archivo se encuentra se archiva.|  
|[CFileFind::IsCompressed](#iscompressed)|Determina si el archivo se encuentra está comprimido.|  
|[CFileFind::IsDirectory](#isdirectory)|Determina si el archivo se encuentra es un directorio.|  
|[CFileFind::IsDots](#isdots)|Determina si el nombre del archivo se encuentra con el nombre "."o"..", lo que indica que es realmente un directorio.|  
|[CFileFind::IsHidden](#ishidden)|Determina si el archivo se encuentra está oculto.|  
|[CFileFind::IsNormal](#isnormal)|Determina si el archivo se encuentra es normal (es decir, no tiene otros atributos).|  
|[CFileFind::IsReadOnly](#isreadonly)|Determina si el archivo se encuentra es de solo lectura.|  
|[CFileFind::IsSystem](#issystem)|Determina si el archivo se encuentra es un archivo del sistema.|  
|[CFileFind::IsTemporary](#istemporary)|Determina si el archivo se encuentra es temporal.|  
|[CFileFind::MatchesMask](#matchesmask)|Indica los atributos de archivo que desee del archivo que se encuentra.|  
  
### <a name="protected-methods"></a>Métodos protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Cierra el archivo especificado por el identificador de búsqueda actual.|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|nombre|Descripción|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|Puntero a un `CAtlTransactionManager` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 `CFileFind` incluye funciones miembro que iniciar una búsqueda, busque un archivo y devuelvan el título, el nombre o la ruta de acceso del archivo. Para las búsquedas de Internet, la función miembro [GetFileURL](#getfileurl) devuelve la dirección URL del archivo.  
  
 `CFileFind` es la clase base para otras dos clases MFC diseñada para buscar tipos de servidor determinado: `CGopherFileFind` funciona específicamente con servidores gopher, y `CFtpFileFind` funciona específicamente con servidores FTP. Juntas, estas tres clases proporcionan un mecanismo sin problemas para el cliente buscar archivos, sin tener en cuenta el protocolo del servidor, el tipo de archivo o ubicación, en un equipo local o en un servidor remoto.  
  
 El código siguiente enumerará todos los archivos en el directorio actual, imprimiendo el nombre de cada archivo:  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Para simplificar el ejemplo, este código usa la biblioteca estándar de C++ `cout` clase. El `cout` línea se podría reemplazar con una llamada a `CListBox::AddString`, por ejemplo, en un programa con una interfaz gráfica de usuario.  
  
 Para obtener más información sobre cómo usar `CFileFind` y las demás clases WinInet, vea el artículo [programación para Internet con WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 Esta función miembro se llama cuando un `CFileFind` se haya construido.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Parámetros  
 `pTM`  
 Puntero al objeto CAtlTransactionManager  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>  CFileFind::Close  
 Llame a esta función miembro para finalizar la búsqueda, restablecer el contexto y liberar todos los recursos.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Comentarios  
 Después de llamar a **cerrar**, no es necesario que crear un nuevo `CFileFind` instancia antes de llamar a [FindFile](#findfile) para comenzar una nueva búsqueda.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 Cierra el archivo especificado por el identificador de búsqueda actual.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Comentarios  
 Cierra el archivo especificado por el valor actual del identificador de búsqueda. Reemplace esta función para cambiar el comportamiento predeterminado.  
  
 Debe llamar a la [FindFile](#findfile) o [FindNextFile](#findnextfile) funciones al menos una vez para recuperar un identificador de búsqueda válido. El **FindFile** y `FindNextFile` funciones utilizan el identificador de búsqueda para buscar archivos cuyos nombres coincidan con un nombre determinado.  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 Llame a esta función miembro para abrir una búsqueda de archivos.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Parámetros  
 `pstrName`  
 Un puntero a una cadena que contiene el nombre del archivo que desea buscar. Si se pasa **NULL** para `pstrName`, **FindFile** un carácter comodín (\*.\*) búsqueda.  
  
 *dwUnused*  
 Reservado para realizar **FindFile** polimórfico con las clases derivadas. Debe ser 0.  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero. Para obtener información de error extendida, llame a la función de Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Comentarios  
 Después de llamar a **FindFile** para comenzar la búsqueda de archivo, llame a [FindNextFile](#findnextfile) para recuperar los archivos subsiguientes. Debe llamar a `FindNextFile` al menos una vez antes de llamar a cualquiera de los atributos siguientes funciones miembro:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [isHidden](#ishidden)  
  
- [Isnormal)](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="findnextfile"></a>  CFileFind::FindNextFile  
 Llame a esta función miembro para continuar una búsqueda de archivos de una llamada anterior a [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si no hay más archivos; Devuelve cero si se encuentra el archivo es la última de ellas en el directorio o si se produjo un error. Para obtener información de error extendida, llame a la función de Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Si se encuentra el archivo es el último archivo en el directorio, o si no hay coincidencia de archivos pueden encontrarse los `GetLastError` función devuelve ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a `FindNextFile` al menos una vez antes de llamar a cualquiera de los atributos siguientes funciones miembro:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [isHidden](#ishidden)  
  
- [Isnormal)](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile` ajusta la función de Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime  
 Llame a esta función miembro para obtener la hora en que se creó el archivo especificado.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `pTimeStamp`  
 Un puntero a un [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) estructura que contiene la hora en que se creó el archivo.  
  
 `refTime`  
 Una referencia a un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objeto.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se realiza correctamente; 0 si no lo consigue. `GetCreationTime` Devuelve 0 si [FindNextFile](#findnextfile) nunca se ha llamado en el objeto `CFileFind` objeto.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetCreationTime`.  
  
> [!NOTE]
>  No todos los sistemas de archivos usan la misma semántica para implementar la marca de tiempo devuelta por esta función. Esta función puede devolver el mismo valor devuelto por otras funciones de marca de tiempo si el sistema de archivos o servidor subyacente no admite mantener el atributo de tiempo. Consulte la [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura para obtener información sobre formatos de hora. En algunos sistemas operativos, la hora devuelta está en la hora local de la zona a la máquina estaban se encuentra el archivo. Vea el Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API para obtener más información.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="getfilename"></a>  CFileFind::GetFileName  
 Llame a esta función miembro para obtener el nombre del archivo se encuentra.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El nombre del archivo encontrado más recientemente.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a GetFileName.  
  
 `GetFileName` es uno de los tres `CFileFind` funciones miembro que devuelven algún tipo del nombre de archivo. En la lista siguiente se describe los tres y cómo varían:  
  
- `GetFileName` Devuelve el nombre de archivo, incluida la extensión. Por ejemplo, al llamar a `GetFileName` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve el nombre de archivo `myfile.txt`.  
  
- [GetFilePath](#getfilepath) devuelve la ruta de acceso completa del archivo. Por ejemplo, al llamar a `GetFilePath` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve la ruta de acceso de archivo `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) devuelve el nombre de archivo, sin incluir la extensión de archivo. Por ejemplo, al llamar a `GetFileTitle` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve el título del archivo `myfile`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 Llame a esta función miembro para obtener la ruta de acceso completa del archivo especificado.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 La ruta de acceso del archivo especificado.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetFilePath`.  
  
 `GetFilePath` es uno de los tres `CFileFind` funciones miembro que devuelven algún tipo del nombre de archivo. En la lista siguiente se describe los tres y cómo varían:  
  
- [GetFileName](#getfilename) devuelve el nombre de archivo, incluida la extensión. Por ejemplo, al llamar a `GetFileName` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve el nombre de archivo `myfile.txt`.  
  
- `GetFilePath` Devuelve la ruta de acceso completa del archivo. Por ejemplo, al llamar a `GetFilePath` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve la ruta de acceso de archivo `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) devuelve el nombre de archivo, sin incluir la extensión de archivo. Por ejemplo, al llamar a `GetFileTitle` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve el título del archivo `myfile`.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle  
 Llame a esta función miembro para obtener el título del archivo se encuentra.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El título del archivo.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetFileTitle`.  
  
 `GetFileTitle` es uno de los tres `CFileFind` funciones miembro que devuelven algún tipo del nombre de archivo. En la lista siguiente se describe los tres y cómo varían:  
  
- [GetFileName](#getfilename) devuelve el nombre de archivo, incluida la extensión. Por ejemplo, al llamar a `GetFileName` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve el nombre de archivo `myfile.txt`.  
  
- [GetFilePath](#getfilepath) devuelve la ruta de acceso completa del archivo. Por ejemplo, al llamar a `GetFilePath` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve la ruta de acceso de archivo `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle` Devuelve el nombre de archivo, sin incluir la extensión de archivo. Por ejemplo, al llamar a `GetFileTitle` para generar un mensaje de usuario acerca del archivo `c:\myhtml\myfile.txt` devuelve el título del archivo `myfile`.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfileurl"></a>  CFileFind::GetFileURL  
 Llame a esta función miembro para recuperar la dirección URL especificada.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 La dirección URL completa.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetFileURL`.  
  
 `GetFileURL` es similar a la función miembro [GetFilePath](#getfilepath), excepto en que devuelve la dirección URL en el formulario `file://path`. Por ejemplo, al llamar a `GetFileURL` para obtener la dirección URL completa para `myfile.txt` devuelve la dirección URL `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 Llame a esta función miembro para obtener la hora de último acceso al archivo especificado.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `refTime`  
 Una referencia a un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objeto.  
  
 `pTimeStamp`  
 Un puntero a un [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) estructura que contiene la hora de último acceso al archivo.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se realiza correctamente; 0 si no lo consigue. `GetLastAccessTime` Devuelve 0 si [FindNextFile](#findnextfile) nunca se ha llamado en el objeto `CFileFind` objeto.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetLastAccessTime`.  
  
> [!NOTE]
>  No todos los sistemas de archivos usan la misma semántica para implementar la marca de tiempo devuelta por esta función. Esta función puede devolver el mismo valor devuelto por otras funciones de marca de tiempo si el sistema de archivos o servidor subyacente no admite mantener el atributo de tiempo. Consulte la [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura para obtener información sobre formatos de hora. En algunos sistemas operativos, la hora devuelta está en la hora local de la zona a la máquina estaban se encuentra el archivo. Vea el Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API para obtener más información.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 Llame a esta función miembro para obtener la última vez que se modificó el archivo.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `pTimeStamp`  
 Un puntero a un [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) estructura que contiene la hora en que se escribió el archivo por última.  
  
 `refTime`  
 Una referencia a un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objeto.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se realiza correctamente; 0 si no lo consigue. `GetLastWriteTime` Devuelve 0 si [FindNextFile](#findnextfile) nunca se ha llamado en el objeto `CFileFind` objeto.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetLastWriteTime`.  
  
> [!NOTE]
>  No todos los sistemas de archivos usan la misma semántica para implementar la marca de tiempo devuelta por esta función. Esta función puede devolver el mismo valor devuelto por otras funciones de marca de tiempo si el sistema de archivos o servidor subyacente no admite mantener el atributo de tiempo. Consulte la [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura para obtener información sobre formatos de hora. En algunos sistemas operativos, la hora devuelta está en la hora local de la zona a la máquina estaban se encuentra el archivo. Vea el Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API para obtener más información.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 Llame a esta función miembro para obtener la longitud del archivo se encuentra, en bytes.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 La longitud del archivo se encuentra, en bytes.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetLength`.  
  
 `GetLength` utiliza la estructura de Win32 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) para obtener y devolver el valor del tamaño del archivo, en bytes.  
  
> [!NOTE]
>  A partir de MFC 7.0, `GetLength` admite tipos enteros de 64 bits. Previamente compilada con esta versión más reciente de la biblioteca de código existente puede producir advertencias de truncamiento.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 Llame a esta función miembro para obtener la raíz del archivo se encuentra.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 La raíz de la búsqueda activa.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `GetRoot`.  
  
 Esta función miembro devuelve el especificador de unidad y el nombre de ruta de acceso utilizada para iniciar una búsqueda. Por ejemplo, al llamar a [FindFile](#findfile) con `*.dat` da como resultado `GetRoot` devuelve una cadena vacía. Pasar una ruta de acceso, como `c:\windows\system\*.dll`a **FindFile** resultados `GetRoot` devolver `c:\windows\system\`.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="isarchived"></a>  CFileFind::IsArchived  
 Llame a esta función miembro para determinar si el archivo se encuentra se archiva.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Aplicaciones de marcar un archivo de almacenamiento, que es copia de seguridad o quitarse con FILE_ATTRIBUTE_ARCHIVE, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsArchived`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="iscompressed"></a>  CFileFind::IsCompressed  
 Llame a esta función miembro para determinar si se comprime el archivo encontrado.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Un archivo comprimido está marcado con FILE_ATTRIBUTE_COMPRESSED, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura. Para un archivo, este atributo indica que todos los datos en el archivo está comprimido. Para un directorio, este atributo indica que la compresión es el valor predeterminado para los archivos recién creados y subdirectorios.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsCompressed`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 Llame a esta función miembro para determinar si el archivo se encuentra es un directorio.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Un archivo que es un directorio se marca con FILE_ATTRIBUTE_DIRECTORY un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsDirectory`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
 Este pequeño programa recorre de forma recursiva todos los directorios de la unidad C:\ e imprime el nombre del directorio.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 Llame a esta función miembro para comprobar los marcadores de directorio principal y el directorio actuales que se va iterando a través de archivos.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el archivo se encuentra con el nombre "."o"..", lo que indica que el archivo se encuentra es realmente un directorio. En caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsDots`.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="ishidden"></a>  CFileFind::IsHidden  
 Llame a esta función miembro para determinar si el archivo se encuentra está oculto.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Los archivos ocultos, que están marcados con FILE_ATTRIBUTE_HIDDEN, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura. Un archivo oculto que no se incluye en un listado de directorios normal.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsHidden`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="isnormal"></a>  CFileFind::IsNormal  
 Llame a esta función miembro para determinar si el archivo se encuentra es un archivo normal.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Los archivos marcados con FILE_ATTRIBUTE_NORMAL, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura. Un archivo normal no tiene otros atributos establecido. Todos los demás atributos de archivo invalidan este atributo.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsNormal`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 Llame a esta función miembro para determinar si el archivo se encuentra es de solo lectura.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Un archivo de solo lectura está marcado con FILE_ATTRIBUTE_READONLY, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura. Las aplicaciones pueden leer un archivo, pero no se pueden escribir en él o eliminarla.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsReadOnly`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="issystem"></a>  CFileFind::IsSystem  
 Llame a esta función miembro para determinar si el archivo se encuentra un archivo del sistema.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Un archivo del sistema está marcado con atributo FILE_ATTRIBUTE_SYSTEM, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura. Un archivo de sistema forma parte de, o se utiliza exclusivamente por el sistema operativo.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsSystem`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 Llame a esta función miembro para determinar si el archivo se encuentra un archivo temporal.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Un archivo temporal se marca con FILE_ATTRIBUTE_TEMPORARY, un atributo de archivo identificado en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura. Un archivo temporal se usa para el almacenamiento temporal. Las aplicaciones deben escribir en el archivo sólo cuando sea absolutamente necesario. La mayoría de los datos del archivo permanece en memoria y no se vuelca en el medio porque pronto se eliminará el archivo.  
  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `IsTemporary`.  
  
 Vea la función miembro [MatchesMask](#matchesmask) para obtener una lista completa de los atributos de archivo.  
  
### <a name="example"></a>Ejemplo  
  Vea el ejemplo de [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 Puntero a un `CAtlTransactionManager` objeto.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Comentarios  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 Llame a esta función miembro para probar los atributos de archivo en el archivo encontrado.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `dwMask`  
 Especifica uno o más atributos de archivo, identificados en el [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) estructura, para el archivo se encuentra. Para buscar varios atributos, utilice el operador OR bit a bit (&#124;) operador. Es aceptable cualquier combinación de los siguientes atributos:  
  
-   FILE_ATTRIBUTE_ARCHIVE el archivo es un archivo de almacenamiento. Las aplicaciones utilizan este atributo para marcar los archivos de copia de seguridad o eliminación.  
  
-   FILE_ATTRIBUTE_COMPRESSED el archivo o directorio se comprime. Para un archivo, esto significa que todos los datos en el archivo se comprime. Para un directorio, esto significa que la compresión es el valor predeterminado para los archivos recién creados y subdirectorios.  
  
-   FILE_ATTRIBUTE_DIRECTORY el archivo es un directorio.  
  
-   FILE_ATTRIBUTE_NORMAL el archivo no tiene otros atributos establecido. Este atributo solo es válido si se utiliza solo. Todos los demás atributos de archivo invalidan este atributo.  
  
-   FILE_ATTRIBUTE_HIDDEN el archivo está oculto. No es va a incluir en un listado de directorios normal.  
  
-   FILE_ATTRIBUTE_READONLY el archivo es de solo lectura. Las aplicaciones pueden leer el archivo pero no se puede escribir en él o eliminarlo.  
  
-   FILE_ATTRIBUTE_SYSTEM el archivo forma parte de o se usa exclusivamente por el sistema operativo.  
  
-   FILE_ATTRIBUTE_TEMPORARY el archivo se está usando para el almacenamiento temporal. Las aplicaciones deben escribir en el archivo sólo cuando sea absolutamente necesario. La mayoría de los datos del archivo permanece en memoria y no se vuelca en el medio porque pronto se eliminará el archivo.  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero. Para obtener información de error extendida, llame a la función de Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Comentarios  
 Debe llamar a [FindNextFile](#findnextfile) al menos una vez antes de llamar a `MatchesMask`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [CObject (clase)](../../mfc/reference/cobject-class.md)   
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind (clase)](../../mfc/reference/cftpfilefind-class.md)   
 [Clase CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile (clase)](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile (clase)](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile (clase)](../../mfc/reference/chttpfile-class.md)
