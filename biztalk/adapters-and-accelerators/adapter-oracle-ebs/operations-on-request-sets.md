---
title: 对请求设置的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0537354d-821e-4cf9-a4d1-f4e7d1643df9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8051a94df28df4090f78287070c5143e6f866ed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217293"
---
# <a name="operations-on-request-sets"></a>对请求设置的操作
在 Oracle E-business Suite 中设置的请求是一组报表和组织成各个阶段的并发程序。 你可以使用单个请求设置为运行一组报表和并发程序。 请求集划分为一个或多个阶段和每个阶段包含一组报表和并发程序。 这些阶段链接相互，且每个阶段执行的顺序进行定义。 有关请求集的多个特定于 Oracle 的信息，请转到[http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539)。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]使您能够在 Oracle E-business Suite 中执行请求集。 中的操作作为公开请求集[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 由于请求集包含的并发程序集时，这些并发的程序的输入的参数为请求设置操作。 并发的程序，以及请求设置操作可使用四个复杂类型参数和简单类型参数作为输入。  
  
> [!IMPORTANT]
>  为请求设置中，必须设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以执行对请求设置的任何操作之前。 这是因为设置应用程序上下文通过 Oracle E-business Suite 中的安全事务来促进设置 （例如责任、 组织和语言设置） 的用户首选项和项目的访问控制。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="complex-type-parameters"></a>复杂类型参数
  
-   **SetRelClassOptions**： 使你能够设置请求组的计划选项。 如果设置 SetRelClassOptions 和 SetRepeatOptions SetRelClassOptions 将取得优先权。 SetRelClassOptions 使用作为参数的以下选项：  
  
    -   **应用程序**： 指示请求集关联的应用程序的短名称。  
  
    -   **类名**： 指示请求集与关联的类的名称。  
  
    -   **CanceOrHold**： 指示取消或保留标志。  
  
    -   **StaleDate**： 指示日期或之后此如果请求集尚未运行，将被取消请求组。  
  
    -   **ContinueOnFail**： 指示请求集提交是否应继续还是 SetRelClassOptions 失败的情况下引发异常。 你可以指定"True"（继续） 或"False"（引发了异常）。  
  
-   **SetPrintOptions**： 使你能够设置请求集的打印选项。 SetPrintOptions 使用作为参数的以下选项：  
  
    -   **打印机**： 指示应将设置输出该申请发送其中的打印机名称。  
  
    -   **样式**： 指示用于打印请求集输出的打印样式。 例如，你可以指定的方向 （"横向"或"纵向"）。  
  
    -   **副本**： 指示要打印的请求集输出的副本数。  
  
    -   **SaveOutput**： 指示是否保存输出文件。 你可以指定"True"False"。  
  
    -   **PrintTogether**： 仅适用于子请求。 指示如何打印的子请求输出。 如果指定"Y"，在所有子请求都完成后才将打印的子请求输出。 如果指定"N"，每个子请求的输出将打印在完成。  
  
    -   **ContinueOnFail**： 指示请求集提交是否应继续还是 SetPrintOptions 失败的情况下引发异常。 你可以指定"True"（继续） 或"False"（引发了异常）。  
  
-   **SetRepeatOptions**： 使你能够设置的重复请求集选项。 SetRepeatOptions 使用作为参数的以下选项：  
  
    -   **RepeatTime**： 表示一天中重复请求集的时间。  
  
    -   **RepeatInterval**： 此参数是适用时，才**RepeatTime**为 NULL。 指示重新提交的请求之间的间隔。 使用此选项以及**RepeatUnit**指定之间重新提交的时间。  
  
    -   **RepeatUnit**： 此参数是适用时，才**RepeatTime**为 NULL。 连同所用的时间单位**RepeatInterval**指定之间重新提交请求的时间。 你可以指定"分钟数"、"Hours"、"Days"或"Months"。  
  
    -   **RepeatType**： 此参数是适用时，才**RepeatTime**为 NULL。 指示是否将以前的请求的"开始"设置执行之后，或者在以前的请求的"结束"设置执行应用的重复间隔。  
  
    -   **RepeatEndTime**： 指示停止重新提交请求集的日期和时间。  
  
    -   **ContinueOnFail**： 指示请求集提交是否应继续还是 SetRepeatOptions 失败的情况下引发异常。 你可以指定"True"（继续） 或"False"（引发了异常）。  
  
-   **SetNlsOptions**： 使你能够设置请求集 NLS 选项。 SetNlsOptions 使用作为参数的以下选项：  
  
    -   **语言**： 指示 NLS 语言。  
  
    -   **语言**： 指示语言区域。  
  
    -   **ContinueOnFail**： 指示请求集提交是否应继续还是 SetNlsOptions 失败的情况下引发异常。 你可以指定"True"（继续） 或"False"（引发了异常）。  
  
## <a name="simple-type-parameter"></a>简单类型参数
  
 **StartTime**： 表示请求集应开始运行的时间。  
  
 如果请求设置成功完成，则返回 ID 的并发请求。 否则，返回"0"。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)