---
title: 'Cómo: administrar una instancia del programador | Documentos de Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 699abcbc75dc4f0df40d07d26c0e6987d4711fe3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-manage-a-scheduler-instance"></a>Cómo: Administrar una instancia del programador
Las instancias del Programador permiten asociar directivas de programación concretas con varios tipos de cargas de trabajo. Este tema contiene dos ejemplos básicos que muestran cómo crear y administrar una instancia del programador.  
  
 En los ejemplos se crean programadores que usan las directivas del programador predeterminado. Para un ejemplo que crea un programador que utiliza una directiva personalizada, consulte [Cómo: especificar directivas de programador específicas](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
### <a name="to-manage-a-scheduler-instance-in-your-application"></a>Para administrar una instancia del programador en su aplicación  
  
1.  Crear un [Concurrency:: SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) objeto que contiene la directiva de valores, debe usar el programador.  
  

2.  Llame a la [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) método o la [concurrency::Scheduler::Create](reference/scheduler-class.md#create) método para crear una instancia del programador.  
  
     Si usas el `Scheduler::Create` método, llame a la [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) método cuando necesite asociar el programador al contexto actual.  
  
3.  Llame a la [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) función para crear un identificador para un objeto de evento de restablecimiento automático no señalado.  
  
4.  Pasar el identificador para el objeto de evento que acaba de crear para el [concurrency::CurrentScheduler::RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) método o la [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) método. De esta forma se registra el evento que se debe establecer cuando se destruya el programador.  
  
5.  Realice las tareas que desea que programe el programador actual.  
  
6.  Llame a la [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) método para desasociar el programador actual y restaurar el programador anterior como el actual.  
  
     Si usas el `Scheduler::Create` método, llame a la [concurrency::Scheduler::Release](reference/scheduler-class.md#release) método para reducir el recuento de referencias de la `Scheduler` objeto.  
  
7.  Pasar el identificador del evento a la [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) función que espere a que el programador se cierre.  
  
8.  Llame a la [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) función cerrar el identificador para el objeto de evento.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se muestran dos maneras de administrar una instancia del programador. En cada ejemplo se usa primero el programador predeterminado para realizar una tarea que imprima el identificador único del programador actual. A continuación, se usa una instancia del programador para realizar la misma tarea de nuevo. Finalmente, en cada ejemplo se restaura el programador predeterminado como el actual y se realiza la tarea una vez más.  
  
 El primer ejemplo se utiliza la [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) clase para crear una instancia del programador y asociarla con el contexto actual. El segundo ejemplo se usa el [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) clase para realizar la misma tarea. Normalmente, la clase `CurrentScheduler` se usa con el programador actual. El segundo ejemplo, que usa la clase `Scheduler`, es útil si se desea controlar cuándo está asociado el programador al contexto actual o si se desea asociar programadores concretos a tareas concretas.  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 Este ejemplo produce el siguiente resultado:  
  
```Output  
Using CurrentScheduler class...  
 
Current scheduler id: 0  
Creating and attaching scheduler...  
Current scheduler id: 1  
Detaching scheduler...  
Current scheduler id: 0  
 
Using Scheduler class...  
 
Current scheduler id: 0  
Creating scheduler...  
Attaching scheduler...  
Current scheduler id: 2  
Detaching scheduler...  
Current scheduler id: 0  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o péguelo en un archivo denominado `scheduler-instance.cpp` y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 **cl.exe/EHsc scheduler-instance.cpp**  
  
## <a name="see-also"></a>Vea también  
 [Instancias del programador](../../parallel/concrt/scheduler-instances.md)   
 [Procedimiento para especificar directivas de Scheduler concretas](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

