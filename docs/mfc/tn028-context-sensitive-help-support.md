---
title: 'TN028: Compatibilidad con la Ayuda contextual | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.help
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58caed14e6b7080405cceb30cfb90623d28dc83e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Compatibilidad con la ayuda contextual
Esta nota describe las reglas para asignar identificadores de contextos de ayuda y otros temas de ayuda en MFC. Compatibilidad con la Ayuda contextual requiere que el compilador de ayuda que está disponible en Visual C++.  
  
> [!NOTE]
>  Además de implementar la Ayuda contextual mediante WinHelp, MFC también admite el uso de Ayuda HTML. Para obtener más información sobre esta compatibilidad y la programación con la Ayuda de HTML, consulte [ayuda HTML: ayuda contextual para los programas](../mfc/html-help-context-sensitive-help-for-your-programs.md).  
  
## <a name="types-of-help-supported"></a>Tipos de ayuda compatible  
 Hay dos tipos de ayuda contextual que se implementa en aplicaciones de Windows. La primera, conoce como "Ayuda de F1" implica la creación de WinHelp con el contexto adecuado en función del objeto activo actualmente. El segundo es el modo "MAYÚS + F1". En este modo, el cursor del mouse cambia para el cursor de ayuda y el usuario avanza a haga clic en un objeto. En ese momento, se inicia WinHelp para proporcionar ayuda para el objeto que el usuario ha hecho clic.  
  
 Microsoft Foundation Classes implementar ambas de estas formas de ayuda. Además, el marco de trabajo admite dos comandos ayuda simple, utilizando ayuda y el índice de la Ayuda.  
  
## <a name="help-files"></a>Archivos de ayuda  
 Microsoft Foundation classes suponga un único archivo de ayuda. Este archivo de ayuda debe tener el mismo nombre y ruta de acceso que la aplicación. Por ejemplo, si el ejecutable es C:\MyApplication\MyHelp.exe el archivo de ayuda debe ser C:\MyApplication\MyHelp.hlp. Establecer la ruta de acceso a través de la `m_pszHelpFilePath` variable miembro de la [CWinApp (clase)](../mfc/reference/cwinapp-class.md).  
  
## <a name="help-context-ranges"></a>Intervalos de contexto de ayuda  
 La implementación predeterminada de MFC requiere un programa seguir ciertas reglas sobre la asignación de identificadores de contexto de ayuda. Estas reglas son un intervalo de identificadores asignados a controles específicos. Puede invalidar estas reglas proporcionando implementaciones diferentes de las distintas funciones de miembro relacionadas con la Ayuda.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
0x00010000 + ID_  
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
0x00020000 + IDR_  
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
0x00040000 + IDW_  
```  
  
## <a name="simple-help-commands"></a>Comandos de simple "Ayuda"  
 Hay dos comandos simples de ayuda que se implementan mediante Microsoft Foundation Classes:  
  
-   ID_HELP_INDEX implementado por [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)  
  
-   ID_HELP_USING implementado por [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)  
  
 El primer comando muestra el índice de ayuda para la aplicación. El segundo muestra la Ayuda de usuario sobre cómo utilizar el programa de WinHelp.  
  
## <a name="context-sensitive-help-f1-help"></a>Ayuda contextual (Ayuda F1)  
 La tecla F1 normalmente se traduce en un comando con un Id. de `ID_HELP` por un acelerador colocado en la tabla de aceleradores de la ventana principal. El `ID_HELP` comando también puede generarse mediante un botón con un Id. de `ID_HELP` en el cuadro de diálogo o ventana principal.  
  
 Independientemente de cómo `ID_HELP` se genere un comando, se enruta como un comando normal hasta que llega a un controlador de comandos. Para obtener más información acerca de la arquitectura de enrutamiento de comandos MFC, consulte [21 de nota técnica](../mfc/tn021-command-and-message-routing.md). Si la aplicación dispone de ayuda está habilitada, el `ID_HELP` comando será procesado por [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). El objeto de aplicación recibe el mensaje de ayuda y, a continuación, distribuye el comando de forma adecuada. Esto es necesario porque el enrutamiento de comandos predeterminado no es adecuado para determinar el contexto más específico.  
  
 `CWinApp::OnHelp` intenta iniciar WinHelp en el orden siguiente:  
  
1.  Busca un activo `AfxMessageBox` llame con un identificador de ayuda. Si un cuadro de mensaje está activo actualmente, WinHelp se inicia con el contexto adecuado en ese cuadro de mensajes.  
  
2.  Envía un mensaje WM_COMMANDHELP a la ventana activa. Si esa ventana no responde iniciando WinHelp, el mismo mensaje, a continuación, se envía a los antecesores de esa ventana hasta que se procesa el mensaje o la ventana actual es una ventana de nivel superior.  
  
3.  Envía un ID_DEFAULT_HELP (comando) a la ventana principal. Esto invoca la Ayuda predeterminada. Este comando normalmente se asigna a `CWinApp::OnHelpIndex`.  
  
 Para invalidar globalmente los valores de base del Id. del valor predeterminado (por ejemplo, 0 x 10000 para comandos y 0 x 20000 para recursos como cuadros de diálogo), la aplicación debe invalidar [CWinApp:: WinHelp](../mfc/reference/cwinapp-class.md#winhelp).  
  
 Para invalidar esta funcionalidad y la forma en que se determina un contexto de ayuda, debe controlar el mensaje WM_COMMANDHELP. Puede que desee proporcionar más específica ayuda enrutamiento que proporciona el marco de trabajo, pues solo como profundas como la ventana secundaria MDI actual. También puede proporcionar ayuda más específica para un cuadro de diálogo, quizás basadas en el estado interno actual de ese objeto o el control activo en el cuadro de diálogo o ventana en particular.  
  
## <a name="wmcommandhelp"></a>WM_COMMANDHELP  
  
```  
 
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
 
```  
  
 WM_COMMANDHELP es un mensaje privado de MFC de Windows que se recibe por la ventana activa cuando se solicita ayuda. Cuando la ventana recibe este mensaje, puede llamar a `CWinApp::WinHelp` con contexto que coincide con el estado interno de la ventana.  
  
 `lParam`  
 Contiene el contexto de ayuda disponible actualmente. `lParam` es cero si no se ha determinado ningún contexto de ayuda. Una implementación de `OnCommandHelp` puede utilizar el identificador de contexto en `lParam` para determinar un contexto diferente o simplemente puede pasar a `CWinApp::WinHelp`.  
  
 `wParam`  
 No se utiliza y será cero.  
  
 Si el `OnCommandHelp` llamadas a funciones `CWinApp::WinHelp`, debe devolver `TRUE`. Devolver `TRUE` detiene el enrutamiento de este comando a otras clases y a otras ventanas.  
  
## <a name="help-mode-shiftf1-help"></a>Modo de ayuda (MAYÚS + F1 Ayuda)  
 Se trata de la segunda forma de ayuda contextual. Por lo general, este modo se escribe, presione MAYÚS + F1 o a través de la barra de menús y herramientas. Se implementa como un comando (**ID_CONTEXT_HELP**). El enlace del filtro de mensaje no se usa para traducir este comando al cuadro de diálogo modal o menú está activo, por lo tanto, este comando solo está disponible para el usuario si la aplicación se está ejecutando el suministro de mensajes principal (`CWinApp::Run`).  
  
 Después de escribir este modo, se muestra el cursor de ayuda sobre todas las áreas de la aplicación, incluso si la aplicación normalmente mostraría su propio cursor para dicha área (por ejemplo, el borde de tamaño alrededor de la ventana). El usuario es capaz de utilizar el mouse o el teclado para seleccionar un comando. En lugar de ejecutar el comando, se muestra la Ayuda de ese comando. Además, el usuario puede hacer clic en un objeto visible en la pantalla, como un botón en la barra de herramientas, y se mostrará la ayuda para ese objeto. Este modo de ayuda se proporciona por `CWinApp::OnContextHelp`.  
  
 Durante la ejecución de este bucle, todas las entradas del teclado está inactivo, excepto para las claves que tener acceso al menú. Además, la traducción de comando aún se realiza a través de `PreTranslateMessage` para permitir al usuario que presione una tecla de aceleración y recibir ayuda sobre ese comando.  
  
 Si no hay determinado traducciones o acciones que están teniendo colocar en el `PreTranslateMessage` función que no debería tener lugar durante el modo de ayuda MAYÚS+F1, debe comprobar la `m_bHelpMode` miembro de `CWinApp` antes de realizar estas operaciones. El `CDialog` implementación de `PreTranslateMessage` comprueba esto antes de llamar a `IsDialogMessage`, por ejemplo. Esto deshabilita las claves "navegación del cuadro de diálogo" en los cuadros de diálogo no modales durante el modo de MAYÚS + F1. Además, `CWinApp::OnIdle` todavía se denomina durante este bucle.  
  
 Si el usuario elige un comando en el menú, se trata como ayuda en ese comando (a través de **WM_COMMANDHELP**, vea más adelante). Si el usuario hace clic en un área visible de la ventana de las aplicaciones, se realiza una determinación sobre si es un no cliente o un cliente, haga clic en. `OnContextHelp` asignación de identificadores de no cliente hace clic en a los clics de cliente automáticamente. Si es un cliente, haga clic en, a continuación, envía una **WM_HELPHITTEST** a la ventana que se ha hecho clic. Si esa ventana devuelve un valor distinto de cero, ese valor se utiliza como el contexto para obtener ayuda. Si devuelve cero, `OnContextHelp` trata de la ventana primaria (y si no es posible, su elemento primario y así sucesivamente). Si no se puede determinar el contexto de ayuda, el valor predeterminado es enviar un **ID_DEFAULT_HELP** comando a la ventana principal, que, a continuación, se asigna (normalmente) a `CWinApp::OnHelpIndex`.  
  
## <a name="wmhelphittest"></a>WM_HELPHITTEST  
  
```  
 
afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)  
```  
  
 **WM_HELPHITTEST** es un mensaje de windows privados de MFC que se recibe en la ventana activa que se hizo clic en el modo de ayuda MAYÚS+F1. Cuando la ventana recibe este mensaje, devuelve un identificador de Ayuda de DWORD para su uso por WinHelp.  
  
 LOWORD(lParam)  
 contiene la coordenada de dispositivo del eje x donde se hizo clic del mouse en relación con el área de cliente de la ventana.  
  
 HIWORD(lParam)  
 contiene la coordenada del eje y.  
  
 `wParam`  
 No se utiliza y será cero. Si el valor devuelto es distinto de cero, se denomina WinHelp con ese contexto. Si el valor devuelto es cero, la ventana primaria se consulta para obtener ayuda.  
  
 En muchos casos, puede aprovechar el código de prueba de posicionamiento que quizás ya tenga. Vea la implementación de **CToolBar::OnHelpHitTest** para obtener un ejemplo de control de la **WM_HELPHITTEST** mensaje (el código usa el código de prueba de posicionamiento utilizado en los botones e información sobre herramientas en `CControlBar`).  
  
## <a name="mfc-application-wizard-support-and-makehm"></a>MAKEHM y soporte de Asistente para aplicaciones MFC  
 El Asistente para aplicaciones MFC crea los archivos necesarios para compilar un archivo de ayuda (archivos .cnt y .hpj). También incluye una serie de archivos .rtf creada previamente que puede aceptar el compilador de Ayuda de Microsoft. Muchos de los temas están completos, pero algunos pueden necesitar modificar para su aplicación específica.  
  
 Creación automática de un archivo "Ayuda" asignación"es compatible con una utilidad denominada MAKEHM. La utilidad MAKEHM puede traducir recursos de la aplicación. H del proyecto a un archivo de asignación de ayuda. Por ejemplo:  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 se traducirá en:  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 Este formato es compatible con el servicio del compilador de ayuda, que permite asignar identificadores de contexto (los números en el lado derecho) con nombres de temas (los símbolos en el lado izquierdo).  
  
 El código fuente de MAKEHM está disponible en el ejemplo de programación MFC [MAKEHM](../visual-cpp-samples.md).  
  
## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>Agregar ayuda y soporte técnico después de ejecutar al Asistente para aplicaciones MFC  
 Es la mejor manera de agregar ayuda a la aplicación comprobar la opción "Ayuda contextual" en la página características avanzadas del Asistente para aplicaciones MFC antes de crear la aplicación. De este modo el Asistente para aplicaciones MFC agrega automáticamente las entradas del mapa de mensajes necesarios para su `CWinApp`-clase derivada para admitir la Ayuda.  
  
## <a name="help-on-message-boxes"></a>Ayuda en cuadros de mensaje  
 Se admite la Ayuda en cuadros de mensaje (a veces denominado alertas) a través de la `AfxMessageBox` función, un contenedor para el `MessageBox` API de Windows.  
  
 Hay dos versiones de `AfxMessageBox`, uno para su uso con un identificador de cadena y otro para su uso con un puntero a la cadena (`LPCSTR`):  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```  
  
 En ambos casos, hay un opcional Identificador de ayuda.  
  
 En el primer caso, el valor predeterminado de nIDHelp es 0, que indica que no hay ayuda para este cuadro de mensaje. Si el usuario presiona F1 mientras como mensaje cuadro está activo, el usuario no recibirá ayuda (incluso si la aplicación admite Ayuda). Si esto no es deseable, debe proporcionarse un Id. de ayuda para nIDHelp.  
  
 En el segundo caso, el valor predeterminado de nIDHelp es -1, lo que indica que el identificador de ayuda es el mismo que nIDPrompt. Ayuda solo funcionará si la aplicación es basadas en la Ayuda, por supuesto). Debe proporcionar 0 para nIDHelp si desea que el cuadro de mensaje no tiene ninguna ayuda y soporte técnico. Si quiere que el mensaje de ayuda está habilitada, pero desea obtener un identificador de ayuda diferente que nIDPrompt, basta con proporcionar un valor positivo para nIDHelp distinto de nIDPrompt.  
  
## <a name="see-also"></a>Vea también  
 [Notas técnicas por número](../mfc/technical-notes-by-number.md)   
 [Notas técnicas por categoría](../mfc/technical-notes-by-category.md)

