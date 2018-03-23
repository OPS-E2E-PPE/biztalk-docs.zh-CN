---
title: 为什么为 BAM 编写代码？ |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10b8ccb29d95daf8ccdf80d67faef3e50495af04
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="why-write-code-for-bam"></a><span data-ttu-id="381a0-103">为什么为 BAM 编写代码？</span><span class="sxs-lookup"><span data-stu-id="381a0-103">Why Write Code For BAM?</span></span>
<span data-ttu-id="381a0-104">在大多数情况下，您不必编写自己的代码就可以使用 BAM 工具执行跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="381a0-104">In most circumstances you can use the BAM tools without writing your own code to perform your tracking functions.</span></span> <span data-ttu-id="381a0-105">这些工具是用于 Excel、BAM 管理实用程序和跟踪配置文件编辑器 (TPE) 的 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="381a0-105">These tools are the BAM Add-in for Excel, the BAM Management utility, and the Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="381a0-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 BAM 为 BizTalk 业务流程和消息传送组件（管道和端口）提供侦听器。</span><span class="sxs-lookup"><span data-stu-id="381a0-106">BAM in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides interceptors for BizTalk orchestrations and messaging components (pipelines and ports).</span></span> <span data-ttu-id="381a0-107">侦听器是一种用于装备应用程序的软件，以便应用程序可以基于配置文件以常规方式收集数据。</span><span class="sxs-lookup"><span data-stu-id="381a0-107">An interceptor is software that instruments an application so that it can collect data in a generic way based on a configuration file.</span></span> <span data-ttu-id="381a0-108">您可以使用跟踪配置文件编辑器来装备您的应用程序，以便使用这些侦听器。</span><span class="sxs-lookup"><span data-stu-id="381a0-108">You can instrument your application to use these interceptors by using the Tracking Profile Editor.</span></span> <span data-ttu-id="381a0-109">有关跟踪配置文件编辑器中的详细信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="381a0-109">For more information about the Tracking Profile Editor, see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
 <span data-ttu-id="381a0-110">有时，使用 BAM API 装备您的应用程序可能更有利，这主要体现在以下两种情况上：</span><span class="sxs-lookup"><span data-stu-id="381a0-110">There are two primary scenarios, however, in which you will find it advantageous to instrument your application using the BAM APIs:</span></span>  
  
-   <span data-ttu-id="381a0-111">对于您要监视的主机，不存在 BAM 侦听器。</span><span class="sxs-lookup"><span data-stu-id="381a0-111">There is no BAM interceptor for the host you intend to monitor.</span></span>  
  
-   <span data-ttu-id="381a0-112">内置的侦听器不支持复杂的应用程序。</span><span class="sxs-lookup"><span data-stu-id="381a0-112">The built-in interceptor does not allow for the complexity of your application.</span></span>  
  
 <span data-ttu-id="381a0-113">如果没有任何内置拦截器，你可以使用 BAM **EventStream** Api 来捕获感兴趣的事件。</span><span class="sxs-lookup"><span data-stu-id="381a0-113">When there is no built-in interceptor, you can use the BAM **EventStream** APIs to capture the events of interest.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="381a0-114">你可以组合 **EventStream** 类与 **BAMInterceptor** 类，以创建你自己的侦听器。</span><span class="sxs-lookup"><span data-stu-id="381a0-114">You can combine **EventStream** classes with the **BAMInterceptor** class to create your own interceptor.</span></span> <span data-ttu-id="381a0-115">BAM API SDK 示例阐释了一个您可以扩展的简单的一般侦听器。</span><span class="sxs-lookup"><span data-stu-id="381a0-115">The BAM API SDK sample illustrates a simple generic interceptor that you can extend.</span></span> <span data-ttu-id="381a0-116">通过构建您自己的侦听器，您不必为每个应用程序都编写新代码，即可装备多种类似进程。</span><span class="sxs-lookup"><span data-stu-id="381a0-116">By constructing your own interceptor you can instrument a number of similar processes without writing new code for each application.</span></span> <span data-ttu-id="381a0-117">若要查看 BAM API SDK 示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="381a0-117">To view the BAM API SDK sample, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381a0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="381a0-118">See Also</span></span>  
 [<span data-ttu-id="381a0-119">实现 BAM 解决方案</span><span class="sxs-lookup"><span data-stu-id="381a0-119">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)