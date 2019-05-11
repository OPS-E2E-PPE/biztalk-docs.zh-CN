---
title: 对并发程序的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbc40e4c-d5a1-4763-9683-09a744e5b656
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 204466141d0e50201383f3067241e947b632a1fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375343"
---
# <a name="operations-on-concurrent-programs"></a>对并发程序的操作
Oracle E-business Suite 中的并发程序空间中的操作作为[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  以及特定于 Oracle 应用程序，并发程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还显示以下三种标准操作：Get_Status、 Wait_For_Request 和 Submit_Request。 这意味着如果 Oracle 应用程序具有两个并发程序，将公开五个操作： 一个用于每个并发程序，三个用于标准操作。  
  
 有关信息：  
  
- 浏览并搜索并发程序，请参阅[浏览、 搜索和获取元数据用于 Oracle E-business 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
- 如何调用并发程序中的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[Oracle E-business Suite 使用 BizTalk Server 中调用并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)。  
  
> [!IMPORTANT]
>  必须设置应用程序上下文中的并发程序的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以执行对并发程序的任何操作之前。 这是因为设置应用程序上下文通过设置 （如责任、 组织和语言设置） 的用户首选项和某一项目的访问控制来帮助实现 Oracle E-business Suite 中的安全事务。 有关应用程序上下文中，以及如何将其设置的信息，请参阅设置应用程序上下文[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 以下各节提供有关通过公开的操作信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]并发程序的。  
  
##  <a name="Concurrent"></a> < Concurrent_Program_Name > 操作  
 前面曾提到，将尽可能多的 < Concurrent_Program_Name > 操作为 Oracle 应用程序中的并发程序数。 < Concurrent_Program_Name > 操作采用标准的五个参数： 这三个复杂类型和两个简单类型。  
  
> [!NOTE]
>  对于那些不公开其元数据的并发程序，Oracle E-business 适配器公开这些并发程序的每个 100 的可选参数。 若要成功调用这些并发程序，用户必须请查阅 Oracle E-business Suite 文档以找出需要一个值，用于并发程序的参数，然后指定它们。 此类的并发程序的一个示例是**日记本的导入**(实际名称：**GLLEZL**) 中**总帐**应用程序。  
  
 **复杂类型参数**  
  
- **SetOptions**:可以在提交请求之前设置并发程序的选项。 SetOptions 将作为参数的以下选项：  
  
  -   **隐式**:指示是否要在 Oracle E-business Suite 中的用户的并发请求窗体中显示的并发请求。 您可以指定任何以下四个值：**否**，**是**，**错误**或**警告**。 指定**否**会导致用于 Oracle E-business Suite 中的用户的并发请求窗体中显示的请求。 指定**是**意味着该请求可能会查看仅从系统管理员特权的并发请求窗体。 指定**错误**将导致请求失败的情况下，才会显示在用户的并发请求窗体中。 指定**警告**警告或错误将导致其没有显示用户的并发请求窗体仅当请求。  
  
  -   **受保护的**:指示针对使用 Oracle E-business Suite 中的并发请求窗体所做的更新是否受保护的并发请求。 您可以指定**是**（受保护） 或**否**（不受保护）。  
  
  -   **语言**:指示国家/地区语言支持 (NLS) 语言。 如果未不指定任何值，则默认为当前的语言。  
  
  -   **Territory**:指示语言区域。 如果未不指定任何值，它默认为当前的语言区域。  
  
  -   **ContinueOnFail**:指示是否应继续还是在情况下引发异常的并发请求提交**SetOptions**失败。 您可以指定 **，则返回 True** （继续） 或**False** （引发异常）。  
  
- **SetPrintOptions**:可以在提交请求之前设置并发程序的打印选项。 SetPrintOptions 将作为参数的以下选项：  
  
  -   **打印机**:指示应发送的并发请求输出的位置的打印机名称。 如果已设置 Oracle E-business Suite 中的并发程序窗体中，不能重写此打印选项。  
  
  -   **样式**:表示用于打印并发请求的输出的打印样式。 例如，可以指定的方向 (**横向**或**纵向**)。 如果打印样式已在 Oracle E-business Suite 中的并发程序窗体中设置并**所需的样式**复选框处于选中状态，则不能重写此打印选项。  
  
  -   **副本**:指示的并发请求输出中打印的份数。  
  
  -   **SaveOutput**:指示要保存的输出文件。 您可以指定**是**或**否**。  
  
  -   **PrintTogether**:仅适用于包含子请求这些请求。 指示如何打印输出的子请求。 如果指定**Y**，只有在完成所有的子请求之后打印输出的子请求。 如果指定**N**，每个子请求的输出打印在它完成。  
  
  -   **ContinueOnFail**:指示是否应继续还是在情况下引发异常的并发请求提交**SetPrintOptions**失败。 您可以指定 **，则返回 True** （继续） 或**False** （引发异常）。  
  
- **SetRepeatOptions**:可以在提交请求之前设置并发程序重复的选项。 **SetRepeatOptions**采用作为参数的以下选项：  
  
  -   **RepeatTime**:指示一天重复执行的并发请求的时间。  
  
  -   **RepeatInterval**:此参数是仅在**RepeatTime**为 NULL。 指示请求的重新提交之间的间隔。 使用此选项与**RepeatUnit**指定重新提交之间的时间。  
  
  -   **RepeatUnit**:此参数是仅在**RepeatTime**为 NULL。 与所用的时间单位**RepeatInterval**指定之间重新提交请求的时间。 您可以指定**分钟**，**小时**，**天**或者**几个月**。  
  
  -   **RepeatType**:此参数是仅在**RepeatTime**为 NULL。 指示并发请求执行的"start"或"end"的并发请求执行之后是否应用重复间隔时间。  
  
  -   **RepeatEndTime**:指示要停止重新提交的并发请求的日期和时间。  
  
  -   **ContinueOnFail**:指示是否应继续还是在情况下引发异常的并发请求提交**SetRepeatOptions**。 您可以指定 **，则返回 True** （继续） 或**False** （引发异常）。  
  
  **简单类型参数**  
  
- **说明**：并发请求的说明。  
  
- **startTime**:指示并发请求应开始运行的时间。  
  
## <a name="getstatus-operation"></a>Get_Status 操作  
 标准操作，Get_Status，返回请求阶段/状态和并发程序完成消息。 此操作需要并发程序的请求 ID (**RequestID**) 作为输入，然后返回以下信息：  
  
-   **阶段**:从 FND_LOOKUPS 用户友好请求阶段。  
  
-   **状态**：从 FND_LOOKUPS 用户友好的请求的状态。  
  
-   **DevPhase**:作为可用于程序逻辑比较的字符串的请求阶段。  
  
-   **DevStatus**:可用于程序逻辑比较的字符串形式的请求状态。  
  
-   **消息**:如果请求已完成完成的消息。  
  
## <a name="waitforrequest-operation"></a>Wait_For_Request 操作  
 标准操作，Wait_For_Request，等待请求完成，然后返回请求阶段/状态和完成消息。 此操作需要并发程序的请求 ID (**RequestID**)，检查之间需等待的秒数 (**间隔**)，并最大时间 （秒） 等待请求的完成 （**MaxWait**) 作为输入参数，然后返回相同的信息，如 Get_Status 操作中所示。  
  
## <a name="submitrequest-operation"></a>Submit_Request 操作  
 标准操作，Submit_Request，提交以供并发管理器处理的并发请求。 如果请求成功完成，此操作将返回并发请求 id。 否则，返回"0"。  
  
 Submit_Request 操作采用标准的六个参数： 三每个复杂类型的简单类型。 除了这些参数，它还将作为字符串数组，并发程序的参数。  
  
 **复杂类型参数**  
  
 Submit_Request 操作采用**SetOptions**， **SetPrintOptions**，并**SetRepeatOptions**作为输入参数。 有关这些参数的信息，请参阅[ &lt;Concurrent_Program_Name&gt;操作](#Concurrent)本部分前面。  
  
 **简单类型参数**  
  
-   **程序**:应为其提交的请求的并发程序的短名称。  
  
-   **说明**：并发请求的说明。  
  
-   **startTime**:并发请求应开始运行时间。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)