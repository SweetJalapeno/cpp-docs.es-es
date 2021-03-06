---
title: directory_entry (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.workload:
- cplusplus
ms.openlocfilehash: 9a55109683a18415638cacd9cd15dbcaa3164fc8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="directoryentry-class"></a>directory_entry (Clase)

Describe un objeto devuelto por `*X`, donde *X* es un [directory_iterator](../standard-library/directory-iterator-class.md) o un [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).

## <a name="syntax"></a>Sintaxis

```cpp
class directory_entry;
```

## <a name="remarks"></a>Comentarios

La clase almacena un objeto de tipo [path](../standard-library/path-class.md). La `path` almacenada puede ser una instancia de la [path (Clase)](../standard-library/path-class.md) o de un tipo que se deriva de `path`. También almacena dos valores [file_type](../standard-library/filesystem-enumerations.md#file_type): uno que representa lo que se conoce sobre el estado del nombre de archivo almacenado y otra que representa lo que se conoce sobre el estado del vínculo simbólico del nombre de archivo.

Para obtener más información y ejemplos de código, vea [Exploración del sistema de archivos (C++)](../standard-library/file-system-navigation.md).

## <a name="assign"></a>assign

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

La función miembro asigna pval a mypath, stat a mystat y symstat a mysymstat.

## <a name="directoryentry"></a>directory_entry

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Los constructores predeterminados se comportan según lo previsto. El cuarto constructor inicializa mypath para pval, mystat para stat_arg y mysymstat para symstat_arg.

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

La función miembro devuelve !(*this == right).

## <a name="operator"></a>operator=

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

Los operadores predeterminados de asignación de miembros se comportan según lo previsto.

## <a name="operator"></a>operator==

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

La función miembro devuelve mypath == right.mypath.

## <a name="operatorlt"></a>Operador&lt;

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

La función miembro devuelve mypath &lt; right.mypath.

## <a name="operatorlt"></a>operator&lt;=

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

La función miembro devuelve !(right \< *this).

## <a name="operatorgt"></a>Operador&gt;

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

La función miembro devuelve right \< *this.

## <a name="operatorgt"></a>operator&gt;=

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

¡La función miembro devuelve! (* Esto \< derecho).

## <a name="operator-const-pathtype"></a>operator const path_type&

```cpp
operator const std::experimental::filesystem::path&() const;
```

El operador miembro devuelve mypath.

## <a name="path"></a>ruta de acceso

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

La función miembro devuelve mypath.

## <a name="replacefilename"></a>replace_filename

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

La función miembro reemplaza mypath con mypath.parent_path() / pval, mystat con stat_arg y mysymstat con symstat_arg

## <a name="status"></a>status

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

Ambas funciones miembro devuelven mystat que posiblemente primero se modifica según se muestra a continuación:

1. Si status_known(mystat), no es necesario hacer nada.

1. De lo contrario, si !status_known(mysymstat) && !is_symlink(mysymstat), entonces mystat = mysymstat.

## <a name="symlinkstatus"></a>symlink_status

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

Ambas funciones miembro devuelven mysymstat que posiblemente primero se modifica según se muestra a continuación: si status_known(mysymstat), no es necesario hacer nada. En caso contrario, mysymstat = symlink_status(mypval).

## <a name="requirements"></a>Requisitos

**Encabezado:** \<experimental/filesystem&gt;

**Espacio de nombres:** std::experimental::filesystem

## <a name="see-also"></a>Vea también

[Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Sistema de archivos&gt;](../standard-library/filesystem.md)<br/>
