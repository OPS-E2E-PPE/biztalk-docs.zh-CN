---
title: 后台示例方案的信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b135dc4b322a2fe09289e971021ddbb387cf2915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530641"
---
# <a name="background-information-for-sample-scenarios"></a><span data-ttu-id="1e5da-102">示例方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="1e5da-102">Background Information for Sample Scenarios</span></span>
<span data-ttu-id="1e5da-103">本主题包含在本部分方案的背景信息。</span><span class="sxs-lookup"><span data-stu-id="1e5da-103">This topic contains background information for the scenarios in this section.</span></span>  
  
## <a name="background-for-all-scenarios"></a><span data-ttu-id="1e5da-104">所有方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="1e5da-104">Background for all scenarios</span></span>  
 <span data-ttu-id="1e5da-105">在主要威胁模型会议之前, 我们收集了以下背景信息。</span><span class="sxs-lookup"><span data-stu-id="1e5da-105">Before the main threat model meeting, we collected the following background information.</span></span> <span data-ttu-id="1e5da-106">此信息适用于我们在示例体系结构发现的所有使用方案：</span><span class="sxs-lookup"><span data-stu-id="1e5da-106">This information applies to all the usage scenarios we identified for the sample architecture:</span></span>  
  
-   <span data-ttu-id="1e5da-107">边界和体系结构的作用域</span><span class="sxs-lookup"><span data-stu-id="1e5da-107">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="1e5da-108">受信任和不受信任的组件之间的边界</span><span class="sxs-lookup"><span data-stu-id="1e5da-108">Boundaries between trusted and untrusted components</span></span>  
  
-   <span data-ttu-id="1e5da-109">每个组件的配置和管理模型</span><span class="sxs-lookup"><span data-stu-id="1e5da-109">Configuration and administration model for each component</span></span>  
  
-   <span data-ttu-id="1e5da-110">有关其他组件和应用程序的假设</span><span class="sxs-lookup"><span data-stu-id="1e5da-110">Assumptions about other components and applications</span></span>  
  
### <a name="boundaries-and-scope-of-the-architecture"></a><span data-ttu-id="1e5da-111">边界和体系结构的作用域</span><span class="sxs-lookup"><span data-stu-id="1e5da-111">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="1e5da-112">防火墙 2 有助于保护服务器和电子商务域中的应用程序从外围网络和你的环境 （例如，公司的域或其他应用程序的域） 的任何其他域。</span><span class="sxs-lookup"><span data-stu-id="1e5da-112">Firewall 2 helps protect the servers and applications in the E-Business domain both from the perimeter network and from any other domains in your environment (for example, a corporate domain or domains for other applications).</span></span>  
  
-   <span data-ttu-id="1e5da-113">防火墙 2 路由所有传入和传出的电子商务域的流量。</span><span class="sxs-lookup"><span data-stu-id="1e5da-113">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="1e5da-114">所有用户组和访问 BizTalk Server 环境的帐户必须都是电子商务域中的全局组。</span><span class="sxs-lookup"><span data-stu-id="1e5da-114">All user groups and accounts that access the BizTalk Server environment must be global groups in the E-Business domain.</span></span>  
  
-   <span data-ttu-id="1e5da-115">访问仅限于该主机实例; 的服务帐户删除消息的接收服务器中的文件、 SQL 或消息队列; 任何应用程序管理员和 BizTalk Server、 企业单一登录 (SSO) 和 Windows。</span><span class="sxs-lookup"><span data-stu-id="1e5da-115">Access is limited to the service account for the host instance; any applications that drop messages in the receive server for File, SQL, or Message Queuing; and administrators for BizTalk Server, Enterprise Single Sign-On (SSO), and Windows.</span></span>  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a><span data-ttu-id="1e5da-116">受信任和不受信任的公司之间的边界</span><span class="sxs-lookup"><span data-stu-id="1e5da-116">Boundaries between trusted and untrusted companies</span></span>  
  
-   <span data-ttu-id="1e5da-117">防火墙 2 路由所有传入和传出的电子商务域的流量。</span><span class="sxs-lookup"><span data-stu-id="1e5da-117">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="1e5da-118">使用不同的 BizTalk 主机作为 BizTalk Server 中的应用程序之间的安全边界。</span><span class="sxs-lookup"><span data-stu-id="1e5da-118">Use different BizTalk Hosts as a security boundary between applications within BizTalk Server.</span></span>  
  
-   <span data-ttu-id="1e5da-119">仅当你信任的应用程序 （例如，不要在受信任的主机中运行第三方组件） 中的代码，请使用受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="1e5da-119">Use trusted hosts only when you trust the code within the application (for example, do not run third-party components in a trusted host).</span></span>  
  
### <a name="configuration-and-administration-model-for-each-component"></a><span data-ttu-id="1e5da-120">每个组件的配置和管理模型</span><span class="sxs-lookup"><span data-stu-id="1e5da-120">Configuration and administration model for each component</span></span>  
 <span data-ttu-id="1e5da-121">**配置模型：**</span><span class="sxs-lookup"><span data-stu-id="1e5da-121">**Configuration model:**</span></span>  
  
- <span data-ttu-id="1e5da-122">仅在 BizTalk 服务器上安装 BizTalk Server 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="1e5da-122">BizTalk Server runtime components are installed only on the BizTalk Servers.</span></span>  
  
- <span data-ttu-id="1e5da-123">主密钥服务器不包含任何其他组件。</span><span class="sxs-lookup"><span data-stu-id="1e5da-123">Master secret server has no additional components.</span></span>  
  
- <span data-ttu-id="1e5da-124">SQL Server 包含所有 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="1e5da-124">SQL Server contains all BizTalk Server databases.</span></span>  
  
- <span data-ttu-id="1e5da-125">服务器在外围网络中的没有任何 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="1e5da-125">Servers in the perimeter networks do not have any BizTalk Server components.</span></span>  
  
- <span data-ttu-id="1e5da-126">管理客户端用于管理电子商务域中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="1e5da-126">Administration client is used to administer all servers in the E-Business domain.</span></span>  
  
  <span data-ttu-id="1e5da-127">**管理模型：**</span><span class="sxs-lookup"><span data-stu-id="1e5da-127">**Administration model:**</span></span>  
  
- <span data-ttu-id="1e5da-128">从桌面 （或便携式计算机） 中，管理员身份连接到具有管理工具 （使用终端服务或远程桌面连接） 的计算机。</span><span class="sxs-lookup"><span data-stu-id="1e5da-128">From a desktop (or laptop), an administrator connects to the computer that has the administration tools (using either Terminal Services or Remote Desktop connection).</span></span> <span data-ttu-id="1e5da-129">管理员在连接到的计算机的管理工具后，管理员可以使用 BizTalk 管理工具来管理所有服务器和域中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e5da-129">After the administrator connects to the computer that has the administration tools, the administrator can use the BizTalk Administration tools to manage all servers and applications within the domain.</span></span>  
  
### <a name="assumptions-about-other-components-and-applications"></a><span data-ttu-id="1e5da-130">有关其他组件和应用程序的假设</span><span class="sxs-lookup"><span data-stu-id="1e5da-130">Assumptions about other components and applications</span></span>  
 <span data-ttu-id="1e5da-131">所有其他应用程序和与 BizTalk Server 环境交互的组件位于之外 （例如，在外围网络中） 的电子商务域的域。</span><span class="sxs-lookup"><span data-stu-id="1e5da-131">All other applications and components that interact with the BizTalk Server environment are in a domain other than the E-Business domain (for example, in a perimeter network).</span></span> <span data-ttu-id="1e5da-132">这些应用程序和组件到和从 BizTalk Server 环境的流量都通过防火墙 2。</span><span class="sxs-lookup"><span data-stu-id="1e5da-132">The traffic from those applications and components to and from the BizTalk Server environment goes through Firewall 2.</span></span>  
  
 <span data-ttu-id="1e5da-133">BizTalk Server 的任何第三方应用程序来自受信任的供应商。</span><span class="sxs-lookup"><span data-stu-id="1e5da-133">Any third-party applications for BizTalk Server come from a trusted vendor.</span></span>  
  
### <a name="data-flow-diagrams"></a><span data-ttu-id="1e5da-134">数据流关系图</span><span class="sxs-lookup"><span data-stu-id="1e5da-134">Data flow diagrams</span></span>  
 <span data-ttu-id="1e5da-135">每个使用方案的背景信息的最后一个元素是数据数据流关系图 (DFD)。</span><span class="sxs-lookup"><span data-stu-id="1e5da-135">The final element of background information for each usage scenario is a data flow diagram (DFD).</span></span> <span data-ttu-id="1e5da-136">DFD 阐释了数据如何流经体系结构。</span><span class="sxs-lookup"><span data-stu-id="1e5da-136">A DFD illustrates how data flows through the architecture.</span></span> <span data-ttu-id="1e5da-137">每个方案都包含不同的 DFD。</span><span class="sxs-lookup"><span data-stu-id="1e5da-137">Each scenario has a different DFD.</span></span> <span data-ttu-id="1e5da-138">在本文档中，数据流关系图包含下图中显示的元素。</span><span class="sxs-lookup"><span data-stu-id="1e5da-138">In this document, the data flow diagrams contain the elements shown in the following figure.</span></span>  
  
 <span data-ttu-id="1e5da-139">**图 1 DFD 的元素**</span><span class="sxs-lookup"><span data-stu-id="1e5da-139">**Figure 1 Elements of the DFD**</span></span>  
  
 <span data-ttu-id="1e5da-140">![DFD 的元素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span><span class="sxs-lookup"><span data-stu-id="1e5da-140">![Elements of the DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span></span>  
  
## <a name="background-for-adapter-scenarios"></a><span data-ttu-id="1e5da-141">适配器方案的背景信息</span><span class="sxs-lookup"><span data-stu-id="1e5da-141">Background for adapter scenarios</span></span>  
 <span data-ttu-id="1e5da-142">在示例体系结构中，我们发现基于以下使用方案上某些适配器可以使用开箱：</span><span class="sxs-lookup"><span data-stu-id="1e5da-142">In our sample architecture, we identified the following usage scenarios based on some of the adapters you can use out-of-the-box:</span></span>  
  
- <span data-ttu-id="1e5da-143">HTTP 和 SOAP (Web services) 适配器方案</span><span class="sxs-lookup"><span data-stu-id="1e5da-143">HTTP and SOAP (Web services) adapters scenario</span></span>  
  
- <span data-ttu-id="1e5da-144">BizTalk 消息队列适配器方案</span><span class="sxs-lookup"><span data-stu-id="1e5da-144">BizTalk Message Queuing adapter scenario</span></span>  
  
- <span data-ttu-id="1e5da-145">文件适配器方案</span><span class="sxs-lookup"><span data-stu-id="1e5da-145">File adapter scenario</span></span>  
  
- <span data-ttu-id="1e5da-146">FTP 适配器方案</span><span class="sxs-lookup"><span data-stu-id="1e5da-146">FTP adapter scenario</span></span>  
  
  <span data-ttu-id="1e5da-147">对于每个方案中，我们将遵循以下步骤来完成威胁模型分析：</span><span class="sxs-lookup"><span data-stu-id="1e5da-147">For each scenario, we followed these steps to complete the threat model analysis:</span></span>  
  
- <span data-ttu-id="1e5da-148">收集背景信息</span><span class="sxs-lookup"><span data-stu-id="1e5da-148">Collect background information</span></span>  
  
- <span data-ttu-id="1e5da-149">创建和分析威胁模型</span><span class="sxs-lookup"><span data-stu-id="1e5da-149">Create and analyze the threat model</span></span>  
  
- <span data-ttu-id="1e5da-150">查看威胁</span><span class="sxs-lookup"><span data-stu-id="1e5da-150">Review threats</span></span>  
  
- <span data-ttu-id="1e5da-151">确定缓解措施</span><span class="sxs-lookup"><span data-stu-id="1e5da-151">Identify mitigation techniques and technologies</span></span>  
  
  <span data-ttu-id="1e5da-152">对于每个方案中，我们已尝试进行评定通用等级的各种攻击可能表示的威胁级别。</span><span class="sxs-lookup"><span data-stu-id="1e5da-152">For each scenario, we have tried to develop generic ratings of the level of threat that the various attacks might represent.</span></span> <span data-ttu-id="1e5da-153">但是，您的环境或体验可能会建议对特定威胁需要不同级别，比我们给出它。</span><span class="sxs-lookup"><span data-stu-id="1e5da-153">However, your environment or experience might suggest that a particular threat deserves a different rating than we have given it.</span></span> <span data-ttu-id="1e5da-154">与所有安全方案，你自己的数据是最可靠确定威胁级别，以及我们建议您进行您自己的分析，使用我们的分析和结果作为指导。</span><span class="sxs-lookup"><span data-stu-id="1e5da-154">As with all security scenarios, your own data is the most robust to determine threat levels, and we recommend that you conduct your own analysis, using our analysis and results as a guide.</span></span>  
  
  <span data-ttu-id="1e5da-155">背景信息 — 除数据流关系图 (DFD)-对于所有使用方案是相同的。</span><span class="sxs-lookup"><span data-stu-id="1e5da-155">The background information—except for the data flow diagram (DFD)—is the same for all our usage scenarios.</span></span> <span data-ttu-id="1e5da-156">在接下来的部分中，我们将介绍每个方案的 dfd:。</span><span class="sxs-lookup"><span data-stu-id="1e5da-156">In the next sections we show the DFD for each scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5da-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e5da-157">See Also</span></span>  
 <span data-ttu-id="1e5da-158">[威胁模型分析](../core/threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="1e5da-158">[Threat Model Analysis](../core/threat-model-analysis.md) </span></span>  
 <span data-ttu-id="1e5da-159">[威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="1e5da-159">[Sample Scenarios for Threat Model Analysis](../core/sample-scenarios-for-threat-model-analysis.md) </span></span>  
 <span data-ttu-id="1e5da-160">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="1e5da-160">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="1e5da-161">中小型公司的示例体系结构</span><span class="sxs-lookup"><span data-stu-id="1e5da-161">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)