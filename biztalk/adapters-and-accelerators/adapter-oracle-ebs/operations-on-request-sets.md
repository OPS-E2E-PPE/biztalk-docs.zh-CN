---
title: 请求集的操作 |Microsoft Docs
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
ms.openlocfilehash: cfc8c773be09a302e740b2eb7d59828e3a1688b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375296"
---
# <a name="operations-on-request-sets"></a>请求集的操作
设置 Oracle E-business Suite 中的请求是一组报表和已组织成各个阶段的并发程序。 可以使用单个请求设置为运行一组报表和并发程序。 请求集划分为一个或多个阶段，并且每个阶段包含了一组报表和并发程序。 这些阶段链接，并定义每个阶段的执行顺序。 有关请求集的多个特定于 Oracle 的信息，请转到[ http://go.microsoft.com/fwlink/p/?LinkId=129539 ](http://go.microsoft.com/fwlink/p/?LinkId=129539)。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 可以在 Oracle E-business Suite 中执行请求集。 请求集将作为中的操作公开[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 请求集包含一组并发程序，因为这些并发程序将是输入的参数，为请求设置操作。 并发程序，以及请求设置操作采用四个复杂类型参数和简单类型参数作为输入。  
  
> [!IMPORTANT]
>  您必须设置应用程序上下文设置请求[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]才能执行请求集的任何操作。 这是因为设置应用程序上下文通过设置 （如责任、 组织和语言设置） 的用户首选项和某一项目的访问控制来帮助实现 Oracle E-business Suite 中的安全事务。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="complex-type-parameters"></a>复杂类型参数
  
-   **SetRelClassOptions**:可以设置的请求集的计划选项。 如果设置 SetRelClassOptions 和 SetRepeatOptions SetRelClassOptions 需要优先顺序。 SetRelClassOptions 将作为参数的以下选项：  
  
    -   **应用程序**:指示请求集关联的应用程序的短名称。  
  
    -   **类名**:指示与请求集相关联的类的名称。  
  
    -   **CanceOrHold**:指示取消或保留标志。  
  
    -   **StaleDate**:表示该日期当天或之后此如果请求集尚未运行，也将取消请求集。  
  
    -   **ContinueOnFail**:指示请求集提交应继续还是 SetRelClassOptions 失败的情况下引发异常。 您可以指定"True"（继续） 或"False"（引发了异常）。  
  
-   **SetPrintOptions**:可以设置的请求集的打印选项。 SetPrintOptions 将作为参数的以下选项：  
  
    -   **打印机**:指示应发送请求集输出的位置的打印机名称。  
  
    -   **样式**:表示用于打印请求集输出的打印样式。 例如，可以指定的方向 （"风景"或"纵向"）。  
  
    -   **副本**:指示请求设置输出的打印的份数。  
  
    -   **SaveOutput**:指示要保存的输出文件。 您可以指定"True"False"。  
  
    -   **PrintTogether**:仅适用于子请求。 指示如何打印输出的子请求。 如果指定"Y"，在所有子请求都完成后才打印输出的子请求。 如果指定"N"，每个子请求的输出打印在它完成。  
  
    -   **ContinueOnFail**:指示请求集提交应继续还是 SetPrintOptions 失败的情况下引发异常。 您可以指定"True"（继续） 或"False"（引发了异常）。  
  
-   **SetRepeatOptions**:使您可以设置的请求集重复的选项。 SetRepeatOptions 将作为参数的以下选项：  
  
    -   **RepeatTime**:指示要重复的请求集日期的时间。  
  
    -   **RepeatInterval**:此参数是仅在**RepeatTime**为 NULL。 指示请求的重新提交之间的间隔。 使用此选项与**RepeatUnit**指定重新提交之间的时间。  
  
    -   **RepeatUnit**:此参数是仅在**RepeatTime**为 NULL。 与所用的时间单位**RepeatInterval**指定之间重新提交请求的时间。 您可以指定"分钟数"、"小时"、"天"或"月"。  
  
    -   **RepeatType**:此参数是仅在**RepeatTime**为 NULL。 指示是否将重复间隔应用的上一个请求的"启动"设置执行后或在上一个请求的"end"设置执行。  
  
    -   **RepeatEndTime**:指示要停止重新提交请求集的日期和时间。  
  
    -   **ContinueOnFail**:指示请求集提交应继续还是 SetRepeatOptions 失败的情况下引发异常。 您可以指定"True"（继续） 或"False"（引发了异常）。  
  
-   **SetNlsOptions**:可以设置的请求集的 NLS 选项。 SetNlsOptions 将作为参数的以下选项：  
  
    -   **语言**:指示 NLS 语言。  
  
    -   **语言**:指示语言区域。  
  
    -   **ContinueOnFail**:指示请求集提交应继续还是 SetNlsOptions 失败的情况下引发异常。 您可以指定"True"（继续） 或"False"（引发了异常）。  
  
## <a name="simple-type-parameter"></a>简单类型参数
  
 **startTime**:指示请求集应开始运行的时间。  
  
 如果请求设置成功完成，返回的 ID 的并发请求。 否则，返回"0"。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)