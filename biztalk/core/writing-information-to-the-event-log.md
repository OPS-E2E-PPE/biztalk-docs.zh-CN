---
title: 向事件日志中写入信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f848cafd6ee9247511db3b9a6dad7dc5da91236b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289573"
---
# <a name="writing-information-to-the-event-log"></a><span data-ttu-id="7b42a-102">将信息写入事件日志</span><span class="sxs-lookup"><span data-stu-id="7b42a-102">Writing Information to the Event Log</span></span>
<span data-ttu-id="7b42a-103">您可能要通过将信息写入默认的应用程序日志或自定义的事件日志，监控您的 BizTalk 应用程序内的不同业务流程的进度。</span><span class="sxs-lookup"><span data-stu-id="7b42a-103">You may want to monitor the progress of the different business processes within your BizTalk application by writing information to the default Application log or to a custom event log.</span></span> <span data-ttu-id="7b42a-104">在以下情况下将信息写入事件日志可能会很有用：</span><span class="sxs-lookup"><span data-stu-id="7b42a-104">Writing to the event log can be useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="7b42a-105">您要使用 Windows 提供的工具以标准方法访问应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="7b42a-105">You want to access application messages in a standard way using tools supplied by Windows.</span></span>  
  
-   <span data-ttu-id="7b42a-106">您想要将来自服务器环境的其他消息与信息一起存档，以便获得更完整的历史记录。</span><span class="sxs-lookup"><span data-stu-id="7b42a-106">You want to archive information with other messages from the server environment for a more complete history.</span></span>  
  
-   <span data-ttu-id="7b42a-107">您想要能够使用与事件日志交互的工具监控您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b42a-107">You want the ability to monitor your application using tools that interact with the event log.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b42a-108">System.Diagnostics.EventLog.WriteEntry 方法对消息字符串有大小限制。</span><span class="sxs-lookup"><span data-stu-id="7b42a-108">The System.Diagnostics.EventLog.WriteEntry method has a size limitation on the message string.</span></span> <span data-ttu-id="7b42a-109">如果消息字符串超过 32766 个字节，则会发生异常。</span><span class="sxs-lookup"><span data-stu-id="7b42a-109">You will receive exception if the message string exceeds 32766 bytes.</span></span>  
  
## <a name="writing-to-the-application-log"></a><span data-ttu-id="7b42a-110">写入应用程序日志</span><span class="sxs-lookup"><span data-stu-id="7b42a-110">Writing to the Application Log</span></span>  
 <span data-ttu-id="7b42a-111">你可以写入应用程序日志或任何其他日志从你的代码通过使用**System.Diagnostics.EventLog**在下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="7b42a-111">You can write to the Application log or any other log from your code by using **System.Diagnostics.EventLog** as shown in the following:</span></span>  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 <span data-ttu-id="7b42a-112">同样，您还可以写入以下内容：</span><span class="sxs-lookup"><span data-stu-id="7b42a-112">Similar, you can also do,</span></span>  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 <span data-ttu-id="7b42a-113">如果你使用的自定义日志，则应使用**SourceExists**方法，以确保它存在之前向其中写入。</span><span class="sxs-lookup"><span data-stu-id="7b42a-113">If you are using a custom log, you should use the **SourceExists** method to ensure it exists before you write to it.</span></span>  
  
## <a name="writing-to-a-custom-log"></a><span data-ttu-id="7b42a-114">写入自定义日志</span><span class="sxs-lookup"><span data-stu-id="7b42a-114">Writing to a Custom Log</span></span>  
 <span data-ttu-id="7b42a-115">写入自定义日志类似于写入应用程序日志，但有一个例外，就是您必须首先创建自定义日志。</span><span class="sxs-lookup"><span data-stu-id="7b42a-115">Writing to a custom log is similar to writing to the Application log with the exception that you must first create the custom log.</span></span> <span data-ttu-id="7b42a-116">用于创建自定义日志的代码十分简单：</span><span class="sxs-lookup"><span data-stu-id="7b42a-116">The code to create a custom log is straightforward:</span></span>  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 <span data-ttu-id="7b42a-117">但是，您不应假定代码将基于具有创建新事件日志的安全权限的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="7b42a-117">However, you should not assume that your code will be run under an account that has the security privileges to create a new event log.</span></span> <span data-ttu-id="7b42a-118">创建事件日志需要管理员权限，并且应在单独的实用程序中完成，最好作为 .msi 安装的一部分完成。</span><span class="sxs-lookup"><span data-stu-id="7b42a-118">Creating an event log takes administrator privileges and should be done in a separate utility program or, ideally, as part of an .msi installation.</span></span> <span data-ttu-id="7b42a-119">有关进行无导出的.msi 安装使用自定义脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="7b42a-119">For more information about using custom script with an exported .msi installation, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>