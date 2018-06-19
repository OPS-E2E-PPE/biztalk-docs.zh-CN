---
title: 监视你的 BizTalk 应用程序部署的进度 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a91910fd1955858260466d987bede1647f0be90c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972891"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a><span data-ttu-id="e3e6b-102">监视 BizTalk 应用程序部署的进度</span><span class="sxs-lookup"><span data-stu-id="e3e6b-102">Monitoring the Progress of Your BizTalk Application Deployment</span></span>
<span data-ttu-id="e3e6b-103">您可以用两种方式 BizTalk 应用程序部署的进度：</span><span class="sxs-lookup"><span data-stu-id="e3e6b-103">You can monitor the progress of your BizTalk application deployment in two ways:</span></span>  
  
-   <span data-ttu-id="e3e6b-104">**BizTalk 安装日志**： 安装，请查阅的日志[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-104">**BizTalk installation log**: You can consult the installation log that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates.</span></span> <span data-ttu-id="e3e6b-105">安装日志位于 %SystemDrive%\Documents 和设置\\<*当前用户*\>\Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-105">Installation logs are located in %SystemDrive%\Documents and Settings\\<*current user*\>\Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment.</span></span>  
  
-   <span data-ttu-id="e3e6b-106">**本地事件日志**： 你可以跟踪在本地事件日志中安装的进度。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-106">**Local event log**: You can track the progress of an installation in the local event log.</span></span> <span data-ttu-id="e3e6b-107">因此，您可以在每个服务器基础上跟踪自定义安装操作。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-107">Therefore, you can track custom installation actions on a per-server basis.</span></span>  
  
-   <span data-ttu-id="e3e6b-108">**Windows Installer 日志**: Microsoft Windows Installer 创建记录的自定义操作的操作的本地计算机上的日志文件。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-108">**Windows Installer log**: Microsoft Windows Installer creates a log file on the local computer that logs the actions of a custom action.</span></span> <span data-ttu-id="e3e6b-109">您可以使用 msiexec 命令的 /log 选项指定此日志文件。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-109">You can specify this log file by using the /log option of the msiexec command.</span></span> <span data-ttu-id="e3e6b-110">有关详细信息，请参阅 Windows Installer 的文档。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-110">For more information, see the documentation for Windows Installer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3e6b-111">部署或取消部署属性架构可能会暴露敏感数据，进而在跟踪中暴露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-111">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="e3e6b-112">只要部署或取消部署包含属性架构的程序集，事件查看器就会在 Windows 应用程序事件日志中记录该事件。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-112">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="e3e6b-113">您应该在事件日志中检查这些消息，以确保所有程序集部署活动均符合您的敏感数据策略。</span><span class="sxs-lookup"><span data-stu-id="e3e6b-113">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="e3e6b-114">(部署为生成到事件日志的消息:"用户"{1}"已部署的程序集"{0}"包含属性的架构。"</span><span class="sxs-lookup"><span data-stu-id="e3e6b-114">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="e3e6b-115">取消部署为生成到事件日志的消息:"用户"{1}"已取消部署的程序集"{0}"包含属性的架构。")</span><span class="sxs-lookup"><span data-stu-id="e3e6b-115">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e6b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e6b-116">See Also</span></span>  
 [<span data-ttu-id="e3e6b-117">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="e3e6b-117">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)