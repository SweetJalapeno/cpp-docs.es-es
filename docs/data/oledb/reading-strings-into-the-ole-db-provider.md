---
title: Leer cadenas desde el proveedor OLE DB | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 073ddbea18e728ffb6777ff16c86bfa4695e05cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Leer cadenas desde el proveedor OLE DB
El `RMyProviderRowset::Execute` función abre un archivo y lee las cadenas. El consumidor pasa el nombre de archivo para el proveedor mediante una llamada a [ICommandText:: SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx). El proveedor recibe el nombre de archivo y lo almacena en la variable miembro `m_szCommandText`. `Execute` lee el nombre del archivo de `m_szCommandText`. Si el nombre de archivo no es válido o no está disponible, el archivo `Execute` devuelve un error. En caso contrario, se abren el archivo y llama `fgets` para recuperar las cadenas. Para cada conjunto de cadenas lee, `Execute` crea una instancia del registro de usuario (`CAgentMan`) y lo coloca en una matriz.  
  
 Si no se puede abrir el archivo, `Execute` debe devolver **DB_E_NOTABLE**. Si devuelve **E_FAIL** en su lugar, el proveedor no funcionará con muchos consumidores y no pasará OLE DB [las pruebas de conformidad](../../data/oledb/testing-your-provider.md).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El texto editado `Execute` función tiene el siguiente aspecto:  
  
### <a name="code"></a>Código  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
class RMyProviderRowset : public CRowsetImpl< RMyProviderRowset, CAgentMan, CRMyProviderCommand>  
{  
public:  
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
    {  
        enum {  
            sizeOfBuffer = 256,  
            sizeOfFile = MAX_PATH  
        };  
        USES_CONVERSION;  
        FILE* pFile = NULL;  
        TCHAR szString[sizeOfBuffer];  
        TCHAR szFile[sizeOfFile];  
        size_t nLength;        errcodeerr;  
  
        ObjectLock lock(this);  
  
        // From a filename, passed in as a command text, scan the file  
        // placing data in the data array.  
        if (!m_szCommandText)  
        {  
            ATLTRACE("No filename specified");  
            return E_FAIL;  
        }  
  
        // Open the file  
        _tcscpy_s(szFile, sizeOfFile, m_szCommandText);  
        if (szFile[0] == _T('\0') ||   
            ((err = fopen_s(&pFile, &szFile[0], "r")) == 0))  
        {  
            ATLTRACE("Could not open file");  
            return DB_E_NOTABLE;  
        }  
  
        // Scan and parse the file.  
        // The file should contain two strings per record  
        LONG cFiles = 0;  
        while (fgets(szString, sizeOfBuffer, pFile) != NULL)  
        {  
            nLength = strnlen(szString, sizeOfBuffer);  
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF  
            CAgentMan am;  
            _tcscpy_s(am.szCommand, am.sizeOfCommand, szString);  
            _tcscpy_s(am.szCommand2, am.sizeOfCommand2, szString);  
  
            if (fgets(szString, sizeOfBuffer, pFile) != NULL)  
            {  
                nLength = strnlen(szString, sizeOfBuffer);  
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF  
                _tcscpy_s(am.szText, am.sizeOfText, szString);  
                _tcscpy_s(am.szText2, am.sizeOfText2, szString);  
            }  
  
            am.dwBookmark = ++cFiles;  
            if (!m_rgRowData.Add(am))  
            {  
                ATLTRACE("Couldn't add data to array");  
                fclose(pFile);  
                return E_FAIL;  
            }  
        }  
  
        if (pcRowsAffected != NULL)  
            *pcRowsAffected = cFiles;  
        return S_OK;  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Implementar un proveedor sencillo de solo lectura](../../data/oledb/implementing-the-simple-read-only-provider.md)