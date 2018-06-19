---
title: 高可用性和 Microsoft Operations Framework |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a06bdadb026617dc55ed40d03e0344584111a0c
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710440"
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a><span data-ttu-id="7c48d-102">高可用性和 Microsoft Operations Framework</span><span class="sxs-lookup"><span data-stu-id="7c48d-102">High Availability and the Microsoft Operations Framework</span></span>
<span data-ttu-id="7c48d-103">将 Microsoft Operations Framework (MOF) 进程模型应用于的规划和实现高度可用的 Microsoft BizTalk Server 解决方案可帮助你确保在发布生命周期的不同阶段具有适当的过程。</span><span class="sxs-lookup"><span data-stu-id="7c48d-103">Applying the Microsoft Operations Framework (MOF) process model to the planning and implementation of a highly available Microsoft BizTalk Server solution can help you make sure that you have appropriate processes at the different stages of the release life cycle.</span></span> <span data-ttu-id="7c48d-104">通过提前查看所有生命周期阶段在高可用性的表面，你可以安装、 维护和故障排除的更方便您环境中的可用性问题。</span><span class="sxs-lookup"><span data-stu-id="7c48d-104">By looking ahead at all the life cycle stages where high availability surfaces, you can make the installation, maintenance, and troubleshooting of availability issues in your environment easier.</span></span>  
  
 <span data-ttu-id="7c48d-105">本部分包含有关 MOF 进程必须要考虑高可用性任务的信息。</span><span class="sxs-lookup"><span data-stu-id="7c48d-105">This section contains information about the MOF processes where you have to consider high-availability tasks.</span></span>  
  
## <a name="microsoft-operations-framework-process-model"></a><span data-ttu-id="7c48d-106">Microsoft Operations Framework 进程模型</span><span class="sxs-lookup"><span data-stu-id="7c48d-106">Microsoft Operations Framework Process Model</span></span>  
 <span data-ttu-id="7c48d-107">[Microsoft Operations Framework (MOF)](https://technet.microsoft.com/solutionaccelerators/dd320379.aspx)提供使组织能够实现任务关键型系统可靠性、 可用性、 可支持性和可管理性的 Microsoft 产品和技术的指导.</span><span class="sxs-lookup"><span data-stu-id="7c48d-107">The [Microsoft Operations Framework (MOF)](https://technet.microsoft.com/solutionaccelerators/dd320379.aspx) provides guidance that enables organizations to achieve mission-critical system reliability, availability, supportability, and manageability of Microsoft products and technologies.</span></span> <span data-ttu-id="7c48d-108">MOF 提供操作指导的白皮书，操作指南、 评估工具、 最佳实践、 案例研究、 模板、 支持工具和服务的形式。</span><span class="sxs-lookup"><span data-stu-id="7c48d-108">MOF provides operational guidance in the form of white papers, operations guides, assessment tools, best practices, case studies, templates, support tools, and services.</span></span> <span data-ttu-id="7c48d-109">本指南解决与复杂、 分布式和异类 IT 环境相关的人员、 流程、 技术和管理问题。</span><span class="sxs-lookup"><span data-stu-id="7c48d-109">This guidance addresses the people, process, technology, and management issues pertaining to complex, distributed, and heterogeneous IT environments.</span></span> 
  
 <span data-ttu-id="7c48d-110">MOF 过程模型使公司到︰</span><span class="sxs-lookup"><span data-stu-id="7c48d-110">The MOF process model enables companies to:</span></span>  
  
-   <span data-ttu-id="7c48d-111">跨服务解决方案，从而简化一致的 IT 服务管理。</span><span class="sxs-lookup"><span data-stu-id="7c48d-111">Facilitate consistent IT service management across service solutions.</span></span>  
  
-   <span data-ttu-id="7c48d-112">建立一个结构，用于 IT 函数、 过程和步骤。</span><span class="sxs-lookup"><span data-stu-id="7c48d-112">Establish a structure for IT functions, processes, and procedures.</span></span>  
  
-   <span data-ttu-id="7c48d-113">表示生命周期方法。</span><span class="sxs-lookup"><span data-stu-id="7c48d-113">Represent a life-cycle approach.</span></span>  
  
 <span data-ttu-id="7c48d-114">MOF 进程模型的核心是其分为四个象限的操作的进程和过程，名为服务管理功能 (Smf)。</span><span class="sxs-lookup"><span data-stu-id="7c48d-114">Central to the MOF process model is its division into four quadrants of operational processes and procedures, named service management functions (SMFs).</span></span> <span data-ttu-id="7c48d-115">Smf 是 foundation 级别的最佳实践和操作和维护的 IT 环境的规范性指引。</span><span class="sxs-lookup"><span data-stu-id="7c48d-115">The SMFs are the foundation-level best practices and prescriptive guidance for operating and maintaining an IT environment.</span></span>  
  
 <span data-ttu-id="7c48d-116">下图显示你需要考虑高可用性的 MOF 进程。</span><span class="sxs-lookup"><span data-stu-id="7c48d-116">The following figure shows the MOF processes where you have to consider high availability.</span></span>  
  
 <span data-ttu-id="7c48d-117">![MOF 过程](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")</span><span class="sxs-lookup"><span data-stu-id="7c48d-117">![MOF Processes](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")</span></span>  
  
## <a name="changing-quadrant"></a><span data-ttu-id="7c48d-118">不断变化 Quadrant</span><span class="sxs-lookup"><span data-stu-id="7c48d-118">Changing Quadrant</span></span>  
 <span data-ttu-id="7c48d-119">更改象限包括标识、 查看、 批准，和将更改合并到的被管理的 IT 环境所需的服务管理功能 (Smf)。</span><span class="sxs-lookup"><span data-stu-id="7c48d-119">The changing quadrant includes the service management functions (SMFs) required to identify, review, approve, and incorporate change into a managed IT environment.</span></span> <span data-ttu-id="7c48d-120">这包括软件、 硬件、 文档、 角色和职责，并还特定的进程和过程的更改中的更改。</span><span class="sxs-lookup"><span data-stu-id="7c48d-120">This includes changes in software, hardware, documentation, roles and responsibilities, and also specific process and procedural changes.</span></span>  
  
### <a name="change-management"></a><span data-ttu-id="7c48d-121">更改管理</span><span class="sxs-lookup"><span data-stu-id="7c48d-121">Change Management</span></span>  
 <span data-ttu-id="7c48d-122">更改管理负责技术、 系统、 应用程序、 硬件、 工具、 文档和进程中的更改，也会更改在角色和职责。</span><span class="sxs-lookup"><span data-stu-id="7c48d-122">Change management is responsible for changes in technology, systems, applications, hardware, tools, documentation, and processes, and also changes in roles and responsibilities.</span></span>  
  
 <span data-ttu-id="7c48d-123">在更改管理过程中，属于设计您的 BizTalk Server 实现，您可以执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="7c48d-123">During the change management process, as part of designing your BizTalk Server implementation, you can do the following:</span></span>  
  
-   <span data-ttu-id="7c48d-124">确定与你的合作伙伴或客户的服务级别协议是否需要特定级别的可用性、 运行时间、 和负载处理功能。</span><span class="sxs-lookup"><span data-stu-id="7c48d-124">Determine whether the service level agreement with your partners or customers requires a certain level of availability, uptime, and load-processing capabilities.</span></span>  
  
-   <span data-ttu-id="7c48d-125">确定你的业务需求的 BizTalk Server 数据库的最佳群集配置。</span><span class="sxs-lookup"><span data-stu-id="7c48d-125">Determine the best cluster configuration for the BizTalk Server databases for your business needs.</span></span> <span data-ttu-id="7c48d-126">运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="7c48d-126">The run-time processes write to the BizTalk Management database, MessageBox databases, Tracking Analysis Services database, BAM Analysis database, BAM Star Schema database, BAM Primary Import database, and BAM Archive database.</span></span> <span data-ttu-id="7c48d-127">因此，这些数据库是特别重要，如果灾难发生，并且确定群集的数据库时，必须具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="7c48d-127">Therefore, these databases are especially important if a disaster occurs, and must have greater priority when determining what databases to cluster.</span></span> <span data-ttu-id="7c48d-128">仅用户或工具写入其他数据库。</span><span class="sxs-lookup"><span data-stu-id="7c48d-128">Only users or tools write to the other databases.</span></span> <span data-ttu-id="7c48d-129">对于 MessageBox 数据库中，你可以考虑尽量减少所需的硬件的主动/主动/主动/被动四台服务器群集。</span><span class="sxs-lookup"><span data-stu-id="7c48d-129">For the MessageBox databases, you can consider an active/active/active/passive four-server cluster to minimize the hardware needed.</span></span>  
  
-   <span data-ttu-id="7c48d-130">确定是否群集主密钥服务器，或者如果手动上还原主密钥另一台企业单一登录服务器已经为你的方案令人满意。</span><span class="sxs-lookup"><span data-stu-id="7c48d-130">Determine whether to cluster the master secret server, or if manually restoring the master secret on another Enterprise Single Sign-On server is satisfactory for your scenario.</span></span> <span data-ttu-id="7c48d-131">此解决方案是可用，但不是高度可用。</span><span class="sxs-lookup"><span data-stu-id="7c48d-131">This solution is available, but not highly available.</span></span>  
  
-   <span data-ttu-id="7c48d-132">确定主机和主机将需要处理预期的消息负载，从而提供高可用性的实例的数。</span><span class="sxs-lookup"><span data-stu-id="7c48d-132">Determine the number of hosts and host instances that you will need to process your expected message load and to provide high availability.</span></span>  
  
-   <span data-ttu-id="7c48d-133">在更改管理过程中创建将涉及的人员的列表。</span><span class="sxs-lookup"><span data-stu-id="7c48d-133">Create a list of the people that will be involved in the change-management process.</span></span> <span data-ttu-id="7c48d-134">此列表将包括但不限于，域管理员、 数据库管理员、 基础结构管理员、 BizTalk Server 管理员和 IT 操作人员。</span><span class="sxs-lookup"><span data-stu-id="7c48d-134">This list will include, but is not limited to, the domain administrator, database administrator, infrastructure administrator, BizTalk Server administrator, and IT operations staff.</span></span>  
  
### <a name="configuration-management"></a><span data-ttu-id="7c48d-135">配置管理</span><span class="sxs-lookup"><span data-stu-id="7c48d-135">Configuration Management</span></span>  
 <span data-ttu-id="7c48d-136">配置管理负责标识、 控制和跟踪软件、 硬件、 文档、 进程、 过程和受控制的更改管理 IT 环境的所有其他组件的所有版本。</span><span class="sxs-lookup"><span data-stu-id="7c48d-136">Configuration management is responsible for identifying, controlling, and tracking all versions of software, hardware, documentation, processes, procedures, and all other components of the IT environment under the control of change management.</span></span>  
  
 <span data-ttu-id="7c48d-137">在配置管理过程中，你必须创建如何为 BizTalk Server 实现高可用性解决方案的详细的计划。</span><span class="sxs-lookup"><span data-stu-id="7c48d-137">During the configuration management process, you must create a detailed plan for how you are going to implement your highly available solution for BizTalk Server.</span></span> <span data-ttu-id="7c48d-138">你必须记录你所花费的创建你的解决方案的步骤。</span><span class="sxs-lookup"><span data-stu-id="7c48d-138">You must also document the steps that you took to create your solution.</span></span> <span data-ttu-id="7c48d-139">在高级别的步骤如下︰</span><span class="sxs-lookup"><span data-stu-id="7c48d-139">At a high level, the steps are:</span></span>  
  
-   <span data-ttu-id="7c48d-140">域控制器创建的域组和将在你的 BizTalk 服务器环境中使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="7c48d-140">The domain controller creates the domain groups and accounts that you will use in your BizTalk Server environment.</span></span>  
  
-   <span data-ttu-id="7c48d-141">基础结构管理员为 BizTalk Server 数据库创建 Windows 群集，并为主密钥服务器创建 Windows 群集。</span><span class="sxs-lookup"><span data-stu-id="7c48d-141">The infrastructure administrator creates the Windows cluster for the BizTalk Server databases and the Windows cluster for the master secret server.</span></span>  
  
-   <span data-ttu-id="7c48d-142">数据库管理员上安装和配置 Microsoft SQL Server 的 BizTalk Server 数据库的 Windows 群集。</span><span class="sxs-lookup"><span data-stu-id="7c48d-142">The database administrator installs and configures Microsoft SQL Server on the Windows cluster for the BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="7c48d-143">BizTalk Server 管理员配置的主密钥服务器群集。</span><span class="sxs-lookup"><span data-stu-id="7c48d-143">The BizTalk Server administrator configures the master secret server cluster.</span></span>  
  
-   <span data-ttu-id="7c48d-144">BizTalk Server 管理员上安装和配置 BizTalk Server 处理，接收和发送方服务器。</span><span class="sxs-lookup"><span data-stu-id="7c48d-144">The BizTalk Server administrator installs and configures BizTalk Server on the processing, receiving, and sending servers.</span></span>  
  
-   <span data-ttu-id="7c48d-145">BizTalk Server 管理员创建主机，并提供高可用性或增加容量，或两者的相应服务器上安装主机实例。</span><span class="sxs-lookup"><span data-stu-id="7c48d-145">The BizTalk Server administrator creates the hosts and installs the host instances on the appropriate servers to provide high availability or to increase capacity, or both.</span></span>  
  
## <a name="operating-quadrant"></a><span data-ttu-id="7c48d-146">操作象限</span><span class="sxs-lookup"><span data-stu-id="7c48d-146">Operating Quadrant</span></span>  
 <span data-ttu-id="7c48d-147">操作象限包括 Smf 需监视、 控制、 管理和管理每日服务解决方案以实现和维护预先确定的参数中的服务级别。</span><span class="sxs-lookup"><span data-stu-id="7c48d-147">The operating quadrant includes the SMFs required to monitor, control, manage, and administer service solutions daily to achieve and maintain service levels within predetermined parameters.</span></span>  
  
### <a name="job-scheduling"></a><span data-ttu-id="7c48d-148">作业计划</span><span class="sxs-lookup"><span data-stu-id="7c48d-148">Job Scheduling</span></span>  
 <span data-ttu-id="7c48d-149">作业计划涉及作业持续的组织，并以最有效的序列中，处理最大化系统的吞吐量和用于满足服务级别协议要求。</span><span class="sxs-lookup"><span data-stu-id="7c48d-149">Job scheduling involves the continuous organization of jobs and processes in the most efficient sequence, maximizing system throughput and use to meet service level agreement requirements.</span></span>  
  
 <span data-ttu-id="7c48d-150">请确保你计划停机时间，例如计划的更新，在消息负载较低时 （例如，夜间后期） 尽量减小对业务的潜在影响的时间安排。</span><span class="sxs-lookup"><span data-stu-id="7c48d-150">Make sure that you schedule planned downtime, such as scheduled updates, at times when the message load is low (for example, late at night) to minimize the potential effect on your business.</span></span>  
  
## <a name="supporting-quadrant"></a><span data-ttu-id="7c48d-151">支持象限</span><span class="sxs-lookup"><span data-stu-id="7c48d-151">Supporting Quadrant</span></span>  
 <span data-ttu-id="7c48d-152">支持象限包括标识、 分配、 诊断、 跟踪和解决事件、 问题和请求中包含的服务级别协议中的已批准要求所需的 Smf。</span><span class="sxs-lookup"><span data-stu-id="7c48d-152">The supporting quadrant includes the SMFs required to identify, assign, diagnose, track, and resolve incidents, problems, and requests within the approved requirements that are contained in the service level agreements.</span></span>  
  
## <a name="optimizing-quadrant"></a><span data-ttu-id="7c48d-153">优化象限</span><span class="sxs-lookup"><span data-stu-id="7c48d-153">Optimizing Quadrant</span></span>  
 <span data-ttu-id="7c48d-154">优化象限包括 Smf 造成维护业务和 IT 对齐方式，通过将重点放在维护或提高服务级别同时减少 IT 成本。</span><span class="sxs-lookup"><span data-stu-id="7c48d-154">The optimizing quadrant includes the SMFs that contribute to maintaining business and IT alignment by focusing on decreasing IT costs while maintaining or improving service levels.</span></span> <span data-ttu-id="7c48d-155">这包括服务中断和事件的检查、 成本结构、 人员评估、 可用性和性能分析和容量预测的检查。</span><span class="sxs-lookup"><span data-stu-id="7c48d-155">This includes review of outages and incidents, examination of cost structures, staff assessments, availability and performance analysis, and capacity forecasting.</span></span>  
  
### <a name="service-level-management"></a><span data-ttu-id="7c48d-156">服务级别管理</span><span class="sxs-lookup"><span data-stu-id="7c48d-156">Service Level Management</span></span>  
 <span data-ttu-id="7c48d-157">服务级别管理旨在维护并持续改进 IT 服务，通过协商和监视服务级别要求的常量周期的质量。</span><span class="sxs-lookup"><span data-stu-id="7c48d-157">The goal of service level management is to maintain and continuously improve the quality of IT service, through a constant cycle of negotiating and monitoring service level requirements.</span></span> <span data-ttu-id="7c48d-158">成功的服务级别管理函数导致的服务、 更高级别的客户工作效率和理想情况下，单击提供服务的总体成本的减少的质量中的改进。</span><span class="sxs-lookup"><span data-stu-id="7c48d-158">The successful service level management function causes an improvement in quality of service, greater levels of customer productivity, and ideally, a reduction in the overall cost of services provided.</span></span>  
  
 <span data-ttu-id="7c48d-159">在服务级别管理过程中，您可以执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="7c48d-159">During the service level management process, you can do the following:</span></span>  
  
-   <span data-ttu-id="7c48d-160">评估当前环境满足您的服务级别协议要求的方式。</span><span class="sxs-lookup"><span data-stu-id="7c48d-160">Evaluate how the current environment satisfies your service level agreement requirements.</span></span>  
  
-   <span data-ttu-id="7c48d-161">建议处理、 接收或发送消息以满足要求的新服务器的添加。</span><span class="sxs-lookup"><span data-stu-id="7c48d-161">Recommend the addition of new servers for processing, receiving, or sending messages to meet the requirements.</span></span>  
  
-   <span data-ttu-id="7c48d-162">如有必要，建议创建对故障点的已不最初缓解满足服务级别协议的可用性要求的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="7c48d-162">If necessary, recommend creating highly available solutions for points of failure that were not originally mitigated to meet the availability requirements in the service level agreement.</span></span>  
  
### <a name="availability-management"></a><span data-ttu-id="7c48d-163">可用性管理</span><span class="sxs-lookup"><span data-stu-id="7c48d-163">Availability Management</span></span>  
 <span data-ttu-id="7c48d-164">可用性管理单个目标是确保你的客户可以使用特定的 IT 服务，只要它们希望。</span><span class="sxs-lookup"><span data-stu-id="7c48d-164">The single goal of availability management is to make sure that your customers can use a particular IT service whenever they want.</span></span>  
  
 <span data-ttu-id="7c48d-165">可用性管理过程，您可以建立通知 IT 人员，以便他们可以修复或更换硬件尽可能快地发生硬件故障时的机制和服务器负载大于特定阈值时通知 IT 人员的机制。</span><span class="sxs-lookup"><span data-stu-id="7c48d-165">For the availability management process, you can establish mechanisms for notifying IT personnel when a hardware failure occurs so that they can fix or replace the hardware as quickly as possible, and mechanisms for notifying IT personnel when the server load is larger than a particular threshold.</span></span>  
  
### <a name="service-continuity-management"></a><span data-ttu-id="7c48d-166">服务连续性管理</span><span class="sxs-lookup"><span data-stu-id="7c48d-166">Service Continuity Management</span></span>  
 <span data-ttu-id="7c48d-167">服务连续性管理功能的目的是确保指定的 IT 服务，如果常规可用性解决方案失败在向客户提供了值。</span><span class="sxs-lookup"><span data-stu-id="7c48d-167">The objective of the service continuity management function is to make sure that a specified IT service provides value to the customer if regular-availability solutions fail.</span></span>  
  
 <span data-ttu-id="7c48d-168">在服务连续性函数期间必须检查哪些高可用性配置以实现，若要确保你继续为客户提供他们期望甚至计划或非计划停机时间时的服务。</span><span class="sxs-lookup"><span data-stu-id="7c48d-168">During the service continuity function you must examine what high-availability configuration to implement to make sure that you continue providing your customers with the services they expect even when a planned or unplanned downtime occurs.</span></span> <span data-ttu-id="7c48d-169">非计划停机时间的示例包括硬件故障或自然灾害。</span><span class="sxs-lookup"><span data-stu-id="7c48d-169">Examples of unplanned downtime are hardware failures or acts of nature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c48d-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c48d-170">See Also</span></span>  
 [<span data-ttu-id="7c48d-171">BizTalk Server 高可用性示例方案</span><span class="sxs-lookup"><span data-stu-id="7c48d-171">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)