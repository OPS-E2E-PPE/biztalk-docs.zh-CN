---
title: "后台示例方案的信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dbb247e42116d5b308170d5ef365ed9f20d793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="background-information-for-sample-scenarios"></a><span data-ttu-id="93f32-102">示例方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="93f32-102">Background Information for Sample Scenarios</span></span>
<span data-ttu-id="93f32-103">本主题介绍本部分中各个方案的背景信息。</span><span class="sxs-lookup"><span data-stu-id="93f32-103">This topic contains background information for the scenarios in this section.</span></span>  
  
## <a name="background-for-all-scenarios"></a><span data-ttu-id="93f32-104">所有方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="93f32-104">Background for all scenarios</span></span>  
 <span data-ttu-id="93f32-105">在主要威胁模型会议前，我们收集了以下背景信息。</span><span class="sxs-lookup"><span data-stu-id="93f32-105">Before the main threat model meeting, we collected the following background information.</span></span> <span data-ttu-id="93f32-106">此信息适用于为示例结构确定的所有使用方案：</span><span class="sxs-lookup"><span data-stu-id="93f32-106">This information applies to all the usage scenarios we identified for the sample architecture:</span></span>  
  
-   <span data-ttu-id="93f32-107">结构的边界和作用域</span><span class="sxs-lookup"><span data-stu-id="93f32-107">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="93f32-108">可信组件与不可信组件之间的边界</span><span class="sxs-lookup"><span data-stu-id="93f32-108">Boundaries between trusted and untrusted components</span></span>  
  
-   <span data-ttu-id="93f32-109">每个组件的配置和管理模式</span><span class="sxs-lookup"><span data-stu-id="93f32-109">Configuration and administration model for each component</span></span>  
  
-   <span data-ttu-id="93f32-110">有关其他组件和应用程序的假设</span><span class="sxs-lookup"><span data-stu-id="93f32-110">Assumptions about other components and applications</span></span>  
  
### <a name="boundaries-and-scope-of-the-architecture"></a><span data-ttu-id="93f32-111">结构的边界和作用域</span><span class="sxs-lookup"><span data-stu-id="93f32-111">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="93f32-112">防火墙 2 有助于保护电子商务域中的服务器和应用程序免受外围网络和您的环境中其他任何域（例如，公司域或其他应用程序的域）的影响。</span><span class="sxs-lookup"><span data-stu-id="93f32-112">Firewall 2 helps protect the servers and applications in the E-Business domain both from the perimeter network and from any other domains in your environment (for example, a corporate domain or domains for other applications).</span></span>  
  
-   <span data-ttu-id="93f32-113">防火墙 2 将所有传入和传出的通信路由到电子商务域。</span><span class="sxs-lookup"><span data-stu-id="93f32-113">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="93f32-114">访问 BizTalk Server 环境的所有用户组和帐户都必须是电子商务域中的全局组。</span><span class="sxs-lookup"><span data-stu-id="93f32-114">All user groups and accounts that access the BizTalk Server environment must be global groups in the E-Business domain.</span></span>  
  
-   <span data-ttu-id="93f32-115">仅将访问权限授予主机实例的服务帐户；在文件、SQL 或消息队列的接收服务器中存放消息的任何应用程序；以及 BizTalk Server、企业单一登录 (SSO) 和 Windows 的管理员。</span><span class="sxs-lookup"><span data-stu-id="93f32-115">Access is limited to the service account for the host instance; any applications that drop messages in the receive server for File, SQL, or Message Queuing; and administrators for BizTalk Server, Enterprise Single Sign-On (SSO), and Windows.</span></span>  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a><span data-ttu-id="93f32-116">受信任的公司与不受信任的公司之间的边界</span><span class="sxs-lookup"><span data-stu-id="93f32-116">Boundaries between trusted and untrusted companies</span></span>  
  
-   <span data-ttu-id="93f32-117">防火墙 2 将所有传入和传出的通信路由到电子商务域。</span><span class="sxs-lookup"><span data-stu-id="93f32-117">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="93f32-118">使用其他 BizTalk 主机作为 BizTalk Server 内应用程序之间的安全边界。</span><span class="sxs-lookup"><span data-stu-id="93f32-118">Use different BizTalk Hosts as a security boundary between applications within BizTalk Server.</span></span>  
  
-   <span data-ttu-id="93f32-119">仅在您信任应用程序内的代码时才使用受信任的主机（例如，不要在受信任的主机中运行第三方组件）。</span><span class="sxs-lookup"><span data-stu-id="93f32-119">Use trusted hosts only when you trust the code within the application (for example, do not run third-party components in a trusted host).</span></span>  
  
### <a name="configuration-and-administration-model-for-each-component"></a><span data-ttu-id="93f32-120">每个组件的配置和管理模式</span><span class="sxs-lookup"><span data-stu-id="93f32-120">Configuration and administration model for each component</span></span>  
 <span data-ttu-id="93f32-121">**配置模型：**</span><span class="sxs-lookup"><span data-stu-id="93f32-121">**Configuration model:**</span></span>  
  
-   <span data-ttu-id="93f32-122">BizTalk Server 运行时组件仅安装在 BizTalk Server 上。</span><span class="sxs-lookup"><span data-stu-id="93f32-122">BizTalk Server runtime components are installed only on the BizTalk Servers.</span></span>  
  
-   <span data-ttu-id="93f32-123">主密钥服务器不包含任何其他组件。</span><span class="sxs-lookup"><span data-stu-id="93f32-123">Master secret server has no additional components.</span></span>  
  
-   <span data-ttu-id="93f32-124">SQL Server 包含所有 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="93f32-124">SQL Server contains all BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="93f32-125">外围网络中的服务器不包含任何 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="93f32-125">Servers in the perimeter networks do not have any BizTalk Server components.</span></span>  
  
-   <span data-ttu-id="93f32-126">使用管理客户端来管理电子商务域中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="93f32-126">Administration client is used to administer all servers in the E-Business domain.</span></span>  
  
 <span data-ttu-id="93f32-127">**管理模型：**</span><span class="sxs-lookup"><span data-stu-id="93f32-127">**Administration model:**</span></span>  
  
-   <span data-ttu-id="93f32-128">管理员（使用终端服务或远程桌面连接）从台式计算机（或便携式计算机）连接到具有管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="93f32-128">From a desktop (or laptop), an administrator connects to the computer that has the administration tools (using either Terminal Services or Remote Desktop connection).</span></span> <span data-ttu-id="93f32-129">管理员在连接到具有管理工具的计算机后，可以使用 BizTalk 管理工具来管理域中的所有服务器和应用程序。</span><span class="sxs-lookup"><span data-stu-id="93f32-129">After the administrator connects to the computer that has the administration tools, the administrator can use the BizTalk Administration tools to manage all servers and applications within the domain.</span></span>  
  
### <a name="assumptions-about-other-components-and-applications"></a><span data-ttu-id="93f32-130">有关其他组件和应用程序的假设</span><span class="sxs-lookup"><span data-stu-id="93f32-130">Assumptions about other components and applications</span></span>  
 <span data-ttu-id="93f32-131">与 BizTalk Server 环境交互的所有其他应用程序和组件都位于电子商务域之外的域中（例如，在外围网络中）。</span><span class="sxs-lookup"><span data-stu-id="93f32-131">All other applications and components that interact with the BizTalk Server environment are in a domain other than the E-Business domain (for example, in a perimeter network).</span></span> <span data-ttu-id="93f32-132">这些应用程序和组件与 BizTalk Server 环境之间通过防火墙 2 进行通信。</span><span class="sxs-lookup"><span data-stu-id="93f32-132">The traffic from those applications and components to and from the BizTalk Server environment goes through Firewall 2.</span></span>  
  
 <span data-ttu-id="93f32-133">BizTalk Server 的所有第三方应用程序均来自受信任的供应商。</span><span class="sxs-lookup"><span data-stu-id="93f32-133">Any third-party applications for BizTalk Server come from a trusted vendor.</span></span>  
  
### <a name="data-flow-diagrams"></a><span data-ttu-id="93f32-134">数据流程图</span><span class="sxs-lookup"><span data-stu-id="93f32-134">Data flow diagrams</span></span>  
 <span data-ttu-id="93f32-135">每个使用方案的背景信息的最终元素是一个数据流关系图 (DFD)。</span><span class="sxs-lookup"><span data-stu-id="93f32-135">The final element of background information for each usage scenario is a data flow diagram (DFD).</span></span> <span data-ttu-id="93f32-136">DFD 阐释了数据如何在结构中传输。</span><span class="sxs-lookup"><span data-stu-id="93f32-136">A DFD illustrates how data flows through the architecture.</span></span> <span data-ttu-id="93f32-137">每个方案都具有不同的 DFD。</span><span class="sxs-lookup"><span data-stu-id="93f32-137">Each scenario has a different DFD.</span></span> <span data-ttu-id="93f32-138">在本文档中，数据流关系图包含下图中所示的元素：</span><span class="sxs-lookup"><span data-stu-id="93f32-138">In this document, the data flow diagrams contain the elements shown in the following figure.</span></span>  
  
 <span data-ttu-id="93f32-139">**图 1 的 DFD 元素**</span><span class="sxs-lookup"><span data-stu-id="93f32-139">**Figure 1 Elements of the DFD**</span></span>  
  
 <span data-ttu-id="93f32-140">![元素的 DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span><span class="sxs-lookup"><span data-stu-id="93f32-140">![Elements of the DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span></span>  
  
## <a name="background-for-adapter-scenarios"></a><span data-ttu-id="93f32-141">适配器方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="93f32-141">Background for adapter scenarios</span></span>  
 <span data-ttu-id="93f32-142">在此示例结构中，我们根据可开箱即用的某些适配器确定了以下使用方案：</span><span class="sxs-lookup"><span data-stu-id="93f32-142">In our sample architecture, we identified the following usage scenarios based on some of the adapters you can use out-of-the-box:</span></span>  
  
-   <span data-ttu-id="93f32-143">HTTP 和 SOAP (Web Services) 适配器方案</span><span class="sxs-lookup"><span data-stu-id="93f32-143">HTTP and SOAP (Web services) adapters scenario</span></span>  
  
-   <span data-ttu-id="93f32-144">BizTalk 消息队列适配器方案</span><span class="sxs-lookup"><span data-stu-id="93f32-144">BizTalk Message Queuing adapter scenario</span></span>  
  
-   <span data-ttu-id="93f32-145">文件适配器方案</span><span class="sxs-lookup"><span data-stu-id="93f32-145">File adapter scenario</span></span>  
  
-   <span data-ttu-id="93f32-146">FTP 适配器方案</span><span class="sxs-lookup"><span data-stu-id="93f32-146">FTP adapter scenario</span></span>  
  
 <span data-ttu-id="93f32-147">对于每个方案，我们均遵循以下步骤来完成威胁模型分析：</span><span class="sxs-lookup"><span data-stu-id="93f32-147">For each scenario, we followed these steps to complete the threat model analysis:</span></span>  
  
-   <span data-ttu-id="93f32-148">收集的背景信息</span><span class="sxs-lookup"><span data-stu-id="93f32-148">Collect background information</span></span>  
  
-   <span data-ttu-id="93f32-149">创建和分析的威胁模型</span><span class="sxs-lookup"><span data-stu-id="93f32-149">Create and analyze the threat model</span></span>  
  
-   <span data-ttu-id="93f32-150">查看威胁</span><span class="sxs-lookup"><span data-stu-id="93f32-150">Review threats</span></span>  
  
-   <span data-ttu-id="93f32-151">标识缓解技术和技术</span><span class="sxs-lookup"><span data-stu-id="93f32-151">Identify mitigation techniques and technologies</span></span>  
  
 <span data-ttu-id="93f32-152">对于每个方案，我们已尝试为各种攻击可能表示的威胁级别评定通用等级。</span><span class="sxs-lookup"><span data-stu-id="93f32-152">For each scenario, we have tried to develop generic ratings of the level of threat that the various attacks might represent.</span></span> <span data-ttu-id="93f32-153">不过，根据您的环境或经验，对特定威胁建议评定的等级可能不同于我们给出的等级。</span><span class="sxs-lookup"><span data-stu-id="93f32-153">However, your environment or experience might suggest that a particular threat deserves a different rating than we have given it.</span></span> <span data-ttu-id="93f32-154">与所有安全方案一样，您自己的数据对于确定威胁级别是最可靠的，建议您使用我们的分析和结果作为指导来进行自己的分析。</span><span class="sxs-lookup"><span data-stu-id="93f32-154">As with all security scenarios, your own data is the most robust to determine threat levels, and we recommend that you conduct your own analysis, using our analysis and results as a guide.</span></span>  
  
 <span data-ttu-id="93f32-155">背景信息 — 数据流关系图 (DFD) 除外 — 对于所有我们使用方案是相同的。</span><span class="sxs-lookup"><span data-stu-id="93f32-155">The background information—except for the data flow diagram (DFD)—is the same for all our usage scenarios.</span></span> <span data-ttu-id="93f32-156">在接下来的部分中，我们将显示每个方案的 DFD。</span><span class="sxs-lookup"><span data-stu-id="93f32-156">In the next sections we show the DFD for each scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f32-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93f32-157">See Also</span></span>  
 <span data-ttu-id="93f32-158">[威胁模型分析](../core/threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="93f32-158">[Threat Model Analysis](../core/threat-model-analysis.md) </span></span>  
 <span data-ttu-id="93f32-159">[威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="93f32-159">[Sample Scenarios for Threat Model Analysis](../core/sample-scenarios-for-threat-model-analysis.md) </span></span>  
 <span data-ttu-id="93f32-160">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="93f32-160">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="93f32-161">对于小型和中型公司示例体系结构</span><span class="sxs-lookup"><span data-stu-id="93f32-161">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)