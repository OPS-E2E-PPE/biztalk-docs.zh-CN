---
title: 为什么为 BAM 编写代码？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d8d6fb370ca7815cf0df2d3685d73c60bc8d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242805"
---
# <a name="why-write-code-for-bam"></a><span data-ttu-id="0bdf8-103">为什么为 BAM 编写代码？</span><span class="sxs-lookup"><span data-stu-id="0bdf8-103">Why Write Code For BAM?</span></span>
<span data-ttu-id="0bdf8-104">在大多数情况下您可以使用 BAM 工具而无需编写自己的代码来执行跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-104">In most circumstances you can use the BAM tools without writing your own code to perform your tracking functions.</span></span> <span data-ttu-id="0bdf8-105">这些工具是 BAM 外接程序 Excel、 BAM 管理实用程序，和跟踪配置文件编辑器 (TPE)。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-105">These tools are the BAM Add-in for Excel, the BAM Management utility, and the Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="0bdf8-106">中的 BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 BizTalk 业务流程和消息传送组件 （管道和端口） 提供侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-106">BAM in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides interceptors for BizTalk orchestrations and messaging components (pipelines and ports).</span></span> <span data-ttu-id="0bdf8-107">侦听器是检测应用程序，以便它可以基于配置文件以一般方式收集数据的软件。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-107">An interceptor is software that instruments an application so that it can collect data in a generic way based on a configuration file.</span></span> <span data-ttu-id="0bdf8-108">您还可以检测应用程序以使用跟踪配置文件编辑器中使用这些侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-108">You can instrument your application to use these interceptors by using the Tracking Profile Editor.</span></span> <span data-ttu-id="0bdf8-109">有关跟踪配置文件编辑器的详细信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-109">For more information about the Tracking Profile Editor, see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
 <span data-ttu-id="0bdf8-110">有两种主要方案，但是，在其中你会发现更有利检测使用 BAM Api 的应用程序：</span><span class="sxs-lookup"><span data-stu-id="0bdf8-110">There are two primary scenarios, however, in which you will find it advantageous to instrument your application using the BAM APIs:</span></span>  
  
- <span data-ttu-id="0bdf8-111">不存在 BAM 侦听器你想要监视的主机。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-111">There is no BAM interceptor for the host you intend to monitor.</span></span>  
  
- <span data-ttu-id="0bdf8-112">内置的侦听器不允许你的应用程序的复杂性。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-112">The built-in interceptor does not allow for the complexity of your application.</span></span>  
  
  <span data-ttu-id="0bdf8-113">当有内置的侦听器时，可以使用 BAM **EventStream** Api，以捕获感兴趣的事件。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-113">When there is no built-in interceptor, you can use the BAM **EventStream** APIs to capture the events of interest.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bdf8-114">你可以组合**EventStream**类与**BAMInterceptor**类，以创建您自己的侦听器。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-114">You can combine **EventStream** classes with the **BAMInterceptor** class to create your own interceptor.</span></span> <span data-ttu-id="0bdf8-115">BAM API SDK 示例说明了简单的一般侦听器，您可以充分利用。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-115">The BAM API SDK sample illustrates a simple generic interceptor that you can extend.</span></span> <span data-ttu-id="0bdf8-116">通过构建您自己的侦听器可以检测多种类似进程，而无需为每个应用程序编写新代码。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-116">By constructing your own interceptor you can instrument a number of similar processes without writing new code for each application.</span></span> <span data-ttu-id="0bdf8-117">若要查看 BAM API SDK 示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0bdf8-117">To view the BAM API SDK sample, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdf8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bdf8-118">See Also</span></span>  
 [<span data-ttu-id="0bdf8-119">实现 BAM 解决方案</span><span class="sxs-lookup"><span data-stu-id="0bdf8-119">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)