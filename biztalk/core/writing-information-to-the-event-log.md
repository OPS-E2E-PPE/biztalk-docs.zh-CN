---
title: 将信息写入到事件日志 |Microsoft Docs
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
ms.openlocfilehash: ae31f6c09e8ffaeb562aa5bd5380dd533173cad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261987"
---
# <a name="writing-information-to-the-event-log"></a><span data-ttu-id="2c51d-102">将信息写入到事件日志</span><span class="sxs-lookup"><span data-stu-id="2c51d-102">Writing Information to the Event Log</span></span>
<span data-ttu-id="2c51d-103">您可能想要通过默认应用程序日志或自定义事件日志写入信息来监视 BizTalk 应用程序中的不同业务流程的进度。</span><span class="sxs-lookup"><span data-stu-id="2c51d-103">You may want to monitor the progress of the different business processes within your BizTalk application by writing information to the default Application log or to a custom event log.</span></span> <span data-ttu-id="2c51d-104">写入事件日志可在以下方案中：</span><span class="sxs-lookup"><span data-stu-id="2c51d-104">Writing to the event log can be useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="2c51d-105">你想要使用由 Windows 提供工具以标准方式访问应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="2c51d-105">You want to access application messages in a standard way using tools supplied by Windows.</span></span>  
  
-   <span data-ttu-id="2c51d-106">你想要存档包含更完整的历史记录的服务器环境的其他电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="2c51d-106">You want to archive information with other messages from the server environment for a more complete history.</span></span>  
  
-   <span data-ttu-id="2c51d-107">您希望能够监视应用程序事件日志中使用交互的工具。</span><span class="sxs-lookup"><span data-stu-id="2c51d-107">You want the ability to monitor your application using tools that interact with the event log.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c51d-108">System.Diagnostics.EventLog.WriteEntry 方法对消息字符串的大小限制。</span><span class="sxs-lookup"><span data-stu-id="2c51d-108">The System.Diagnostics.EventLog.WriteEntry method has a size limitation on the message string.</span></span> <span data-ttu-id="2c51d-109">如果消息字符串超过 32766 个字节，将收到异常。</span><span class="sxs-lookup"><span data-stu-id="2c51d-109">You will receive exception if the message string exceeds 32766 bytes.</span></span>  
  
## <a name="writing-to-the-application-log"></a><span data-ttu-id="2c51d-110">向应用程序日志写入</span><span class="sxs-lookup"><span data-stu-id="2c51d-110">Writing to the Application Log</span></span>  
 <span data-ttu-id="2c51d-111">您可以在应用程序日志或任何其他日志在代码中使用写入**System.Diagnostics.EventLog**在下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="2c51d-111">You can write to the Application log or any other log from your code by using **System.Diagnostics.EventLog** as shown in the following:</span></span>  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 <span data-ttu-id="2c51d-112">类似，您还可以执行，</span><span class="sxs-lookup"><span data-stu-id="2c51d-112">Similar, you can also do,</span></span>  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 <span data-ttu-id="2c51d-113">如果使用自定义日志，则应使用**SourceExists**方法，以确保它存在，才能向其中写入。</span><span class="sxs-lookup"><span data-stu-id="2c51d-113">If you are using a custom log, you should use the **SourceExists** method to ensure it exists before you write to it.</span></span>  
  
## <a name="writing-to-a-custom-log"></a><span data-ttu-id="2c51d-114">写入自定义日志</span><span class="sxs-lookup"><span data-stu-id="2c51d-114">Writing to a Custom Log</span></span>  
 <span data-ttu-id="2c51d-115">写入自定义日志是类似于写入应用程序日志，必须先创建自定义日志的异常。</span><span class="sxs-lookup"><span data-stu-id="2c51d-115">Writing to a custom log is similar to writing to the Application log with the exception that you must first create the custom log.</span></span> <span data-ttu-id="2c51d-116">若要创建自定义日志的代码非常简单：</span><span class="sxs-lookup"><span data-stu-id="2c51d-116">The code to create a custom log is straightforward:</span></span>  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 <span data-ttu-id="2c51d-117">但是，不应假定，将创建一个新的事件日志的安全特权的帐户下运行你的代码。</span><span class="sxs-lookup"><span data-stu-id="2c51d-117">However, you should not assume that your code will be run under an account that has the security privileges to create a new event log.</span></span> <span data-ttu-id="2c51d-118">创建事件日志需要管理员权限，并应在单独的实用程序或完成，理想情况下，作为.msi 安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="2c51d-118">Creating an event log takes administrator privileges and should be done in a separate utility program or, ideally, as part of an .msi installation.</span></span> <span data-ttu-id="2c51d-119">有关使用导出的.msi 安装使用自定义脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="2c51d-119">For more information about using custom script with an exported .msi installation, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>