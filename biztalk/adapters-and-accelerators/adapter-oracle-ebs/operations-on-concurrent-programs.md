---
title: 对并发程序的操作 |Microsoft 文档
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
ms.openlocfilehash: 2bd7aae5d90c85e913c0e65a20f1d03e81c526e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218309"
---
# <a name="operations-on-concurrent-programs"></a>对并发程序操作
在 Oracle E-business Suite 的并发程序作为中的操作进行展示[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  以及特定于 Oracle 应用程序的并发程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还显示以下三个标准操作： Get_Status、 Wait_For_Request 和 Submit_Request。 这意味着如果 Oracle 应用程序具有两个并发节目，将公开的 5 个操作： 一个用于每个并发程序和三个用于标准操作。  
  
 有关的信息：  
  
-   浏览和搜索并发程序，请参阅[浏览、 搜索和用于 Oracle E-business 操作获取元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
-   如何以调用中的并发程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[调用 Oracle E-business Suite 使用 BizTalk Server 中的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)。  
  
> [!IMPORTANT]
>  必须设置应用程序上下文中的并发程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]然后你才能执行并发程序的任何操作。 这是因为设置应用程序上下文通过 Oracle E-business Suite 中的安全事务来促进设置 （例如责任、 组织和语言设置） 的用户首选项和项目的访问控制。 有关应用程序上下文中，以及如何将其设置的信息，请参阅设置应用程序上下文[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 以下各节提供有关通过公开的操作信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]并发程序。  
  
##  <a name="Concurrent"></a>< Concurrent_Program_Name > 操作  
 如前所述，将为 Oracle Aapplication 中的并发程序数的任意多个 < Concurrent_Program_Name > 操作。 < Concurrent_Program_Name > 操作采用标准的五个参数： 三个复杂类型，且两个简单类型。  
  
> [!NOTE]
>  对于不公开其元数据的并发程序，Oracle E-business 适配器为每个这些并发程序公开 100 的可选参数。 若要成功调用这些并发程序，用户必须咨询 Oracle E-business Suite 文档以找出需要一个值，并发程序的参数，然后指定它们。 这样的并发程序的一个示例是**日志导入**(实际名称： **GLLEZL**) 中**常规分类帐**应用程序。  
  
 **复杂类型参数**  
  
-   **SetOptions**： 使你可以在提交请求之前设置的并发程序选项。 SetOptions 使用作为参数的以下选项：  
  
    -   **隐式**： 指示是否要在 Oracle E-business Suite 的用户的并发请求窗体中显示的并发请求。 你可以指定任何以下四个值：**否**，**是**，**错误**或**警告**。 指定**否**会导致请求要在用户的并发请求在 Oracle E-business Suite 的窗体中显示。 指定**是**意味着，可能仅从系统管理员特权的并发请求窗体中查看请求。 指定**错误**会导致请求失败的情况下，才在用户的并发请求窗体中显示。 指定**警告**警告或错误会导致它没有显示用户的并发请求窗体仅当请求。  
  
    -   **受保护**： 指示是否并发请求不会受到在 Oracle E-business Suite 中使用并发请求窗体进行的更新。 你可以指定**是**（受保护） 或**否**（不受保护）。  
  
    -   **语言**： 指示区域语言支持 (NLS) 语言。 如果未不指定任何值，则它默认为当前的语言。  
  
    -   **区域**： 指示语言区域。 如果未不指定任何值，它默认为当前的语言区域。  
  
    -   **ContinueOnFail**： 指示是否应继续还是在情况下引发的异常并发请求提交**SetOptions**失败。 你可以指定**True** （继续） 或**False** （引发异常）。  
  
-   **SetPrintOptions**： 使你能够在提交请求之前设置并发程序的打印选项。 SetPrintOptions 使用作为参数的以下选项：  
  
    -   **打印机**： 指示并发请求输出应发送到的位置的打印机名称。 如果已将其设置在 Oracle E-business Suite 的并发程序窗体中，不能重写此打印选项。  
  
    -   **样式**： 指示用于打印的并发请求输出的打印样式。 例如，可以指定的方向 (**横向**或**纵向**)。 如果打印的样式已在的并发程序窗体中 Oracle E-business Suite 中设置和**所需的样式**选中复选框，则不能重写此打印选项。  
  
    -   **副本**： 指示要打印的并发请求输出的副本数。  
  
    -   **SaveOutput**： 指示是否保存输出文件。 你可以指定**是**或**否**。  
  
    -   **PrintTogether**： 仅适用于包含子请求这些请求。 指示如何打印的子请求输出。 如果指定**Y**，仅在所有子请求完成之后打印的子请求输出。 如果指定**N**，在完成打印每个子请求的输出。  
  
    -   **ContinueOnFail**： 指示是否应继续还是在情况下引发的异常并发请求提交**SetPrintOptions**失败。 你可以指定**True** （继续） 或**False** （引发异常）。  
  
-   **SetRepeatOptions**： 使你能够在提交请求之前设置并发程序重复的选项。 **SetRepeatOptions**采用作为参数的以下选项：  
  
    -   **RepeatTime**： 表示一天中重复并发请求的时间。  
  
    -   **RepeatInterval**： 此参数是适用时，才**RepeatTime**为 NULL。 指示重新提交的请求之间的间隔。 使用此选项以及**RepeatUnit**指定之间重新提交的时间。  
  
    -   **RepeatUnit**： 此参数是适用时，才**RepeatTime**为 NULL。 连同所用的时间单位**RepeatInterval**指定之间重新提交请求的时间。 你可以指定**分钟**，**小时**，**天**或**月**。  
  
    -   **RepeatType**： 此参数是适用时，才**RepeatTime**为 NULL。 指示后的并发请求执行的"开始"或"结束"的并发请求执行后是否应用重复间隔时间。  
  
    -   **RepeatEndTime**： 指示要停止重新提交并发请求的日期和时间。  
  
    -   **ContinueOnFail**： 指示是否应继续还是在情况下引发的异常并发请求提交**SetRepeatOptions**。 你可以指定**True** （继续） 或**False** （引发异常）。  
  
 **简单类型参数**  
  
-   **说明**： 并发请求的说明。  
  
-   **StartTime**： 表示并发请求应开始运行的时间。  
  
## <a name="getstatus-operation"></a>Get_Status 操作  
 标准操作 Get_Status，返回请求阶段/状态和并发程序完成消息。 此操作使用的并发程序的请求 ID (**RequestID**) 作为输入，然后返回以下信息：  
  
-   **阶段**: FND_LOOKUPS 从用户友好的请求阶段。  
  
-   **状态**: FND_LOOKUPS 中的用户友好的请求状态。  
  
-   **DevPhase**： 请求阶段可以用于程序逻辑比较的字符串。  
  
-   **DevStatus**： 可以用于程序逻辑比较的字符串形式的请求状态。  
  
-   **消息**： 完成消息如果请求已完成。  
  
## <a name="waitforrequest-operation"></a>Wait_For_Request 操作  
 标准操作 Wait_For_Request，等待请求完成，然后返回请求阶段/状态和完成消息。 此操作使用的并发程序的请求 ID (**RequestID**)，检查之间等待的秒数 (**间隔**)，以及以秒为单位等待请求的完成 （最长的时间**MaxWait**) 作为输入参数，然后返回如下所示 Get_Status 操作相同的信息。  
  
## <a name="submitrequest-operation"></a>Submit_Request 操作  
 标准操作 Submit_Request，提交对由并发管理器处理的并发请求。 如果请求成功完成，此操作将返回并发请求 id。 否则，它将返回"0"。  
  
 Submit_Request 操作采用标准的六个参数： 三每个复杂类型的简单类型。 除了这些参数，它还将并发程序的自变量作为字符串的数组。  
  
 **复杂类型参数**  
  
 Submit_Request 操作采用**SetOptions**， **SetPrintOptions**，和**SetRepeatOptions**作为输入参数。 有关这些参数的信息，请参阅[ &lt;Concurrent_Program_Name&gt;操作](#Concurrent)本部分前面的。  
  
 **简单类型参数**  
  
-   **程序**： 应为其提交的请求的并发程序的短名称。  
  
-   **说明**： 并发请求的说明。  
  
-   **StartTime**： 并发请求应开始运行的时间。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)