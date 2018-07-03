---
title: 监视 BizTalk 应用程序部署的进度 |Microsoft Docs
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
ms.openlocfilehash: 07beea810ff64c807685b8170009d5204ede1af7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001150"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a><span data-ttu-id="a6a70-102">监视 BizTalk 应用程序部署的进度</span><span class="sxs-lookup"><span data-stu-id="a6a70-102">Monitoring the Progress of Your BizTalk Application Deployment</span></span>
<span data-ttu-id="a6a70-103">您可以用两种方式 BizTalk 应用程序部署的进度：</span><span class="sxs-lookup"><span data-stu-id="a6a70-103">You can monitor the progress of your BizTalk application deployment in two ways:</span></span>  
  
- <span data-ttu-id="a6a70-104">**BizTalk 安装日志**： 您可以参阅 BizTalk Server 生成的安装日志。</span><span class="sxs-lookup"><span data-stu-id="a6a70-104">**BizTalk installation log**: You can consult the installation log that BizTalk Server generates.</span></span> <span data-ttu-id="a6a70-105">安装日志文件位于 %SystemDrive%\Documents and 设置\\<*当前用户*\>\Application Data\Microsoft\BizTalk server\deployment。</span><span class="sxs-lookup"><span data-stu-id="a6a70-105">Installation logs are located in %SystemDrive%\Documents and Settings\\<*current user*\>\Application Data\Microsoft\BizTalk Server\Deployment.</span></span>  
  
- <span data-ttu-id="a6a70-106">**本地事件日志**： 你可以跟踪的本地事件日志中的安装进度。</span><span class="sxs-lookup"><span data-stu-id="a6a70-106">**Local event log**: You can track the progress of an installation in the local event log.</span></span> <span data-ttu-id="a6a70-107">因此，您可以在每个服务器基础上跟踪自定义安装操作。</span><span class="sxs-lookup"><span data-stu-id="a6a70-107">Therefore, you can track custom installation actions on a per-server basis.</span></span>  
  
- <span data-ttu-id="a6a70-108">**Windows 安装程序日志**: Microsoft Windows 安装程序创建自定义操作的操作记录在本地计算机上的日志文件。</span><span class="sxs-lookup"><span data-stu-id="a6a70-108">**Windows Installer log**: Microsoft Windows Installer creates a log file on the local computer that logs the actions of a custom action.</span></span> <span data-ttu-id="a6a70-109">您可以使用 msiexec 命令的 /log 选项指定此日志文件。</span><span class="sxs-lookup"><span data-stu-id="a6a70-109">You can specify this log file by using the /log option of the msiexec command.</span></span> <span data-ttu-id="a6a70-110">有关详细信息，请参阅 Windows Installer 的文档。</span><span class="sxs-lookup"><span data-stu-id="a6a70-110">For more information, see the documentation for Windows Installer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6a70-111">部署或取消部署属性架构可能会暴露敏感数据，进而在跟踪中暴露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="a6a70-111">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="a6a70-112">只要部署或取消部署包含属性架构的程序集，事件查看器就会在 Windows 应用程序事件日志中记录该事件。</span><span class="sxs-lookup"><span data-stu-id="a6a70-112">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="a6a70-113">您应该在事件日志中检查这些消息，以确保所有程序集部署活动均符合您的敏感数据策略。</span><span class="sxs-lookup"><span data-stu-id="a6a70-113">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="a6a70-114">(部署为事件日志中生成的消息:"用户"{1}"已部署程序集"{0}"包含属性架构"。</span><span class="sxs-lookup"><span data-stu-id="a6a70-114">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="a6a70-115">取消部署为事件日志中生成的消息:"用户"{1}"已取消部署程序集"{0}"包含属性架构"。)</span><span class="sxs-lookup"><span data-stu-id="a6a70-115">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a70-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6a70-116">See Also</span></span>  
 [<span data-ttu-id="a6a70-117">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="a6a70-117">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)