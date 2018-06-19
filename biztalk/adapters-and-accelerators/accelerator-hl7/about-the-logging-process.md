---
title: 有关日志记录流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07dba617358d6ad451c53eeb75dbe5d1986f9066
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204717"
---
# <a name="about-the-logging-process"></a><span data-ttu-id="2ad22-102">有关日志记录流程</span><span class="sxs-lookup"><span data-stu-id="2ad22-102">About the Logging Process</span></span>
<span data-ttu-id="2ad22-103">你的应用程序处理关键的因为时间敏感数据和货币数据，审核将成为应用程序的关键部分。</span><span class="sxs-lookup"><span data-stu-id="2ad22-103">Since your applications handle critical, time sensitive and monetary data, auditing becomes a critical part of the application.</span></span> <span data-ttu-id="2ad22-104">若要启用企业级别的可管理性和可用性， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]依赖于以下共享的运行的时和管理组件：</span><span class="sxs-lookup"><span data-stu-id="2ad22-104">To enable enterprise level manageability and availability, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] relies on the following shared run time and administrative components:</span></span>  
  
-   <span data-ttu-id="2ad22-105">**日志记录**： 收集和路由的所有日志事件中指定的数据库的托管方法</span><span class="sxs-lookup"><span data-stu-id="2ad22-105">**Logging**: to collect and route all log events in a managed way to a designated database</span></span>  
  
-   <span data-ttu-id="2ad22-106">**事件监视和服务调试**： 配置日志记录行为以及调查/管理系统管理员和其他 IT 专业人士收集的信息</span><span class="sxs-lookup"><span data-stu-id="2ad22-106">**Event Monitoring and Service Debugging**: to configure logging behavior and to investigate/manage collected information for system administrators and other IT professionals</span></span>  
  
 <span data-ttu-id="2ad22-107">与增强审核中的功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，你可以优化你的运营效率、 安全性和性能，以确保 HL7 法规的合规性。</span><span class="sxs-lookup"><span data-stu-id="2ad22-107">With the enhanced auditing features in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], you can optimize your operational efficiency, security, and performance to ensure compliance with HL7 regulations.</span></span>  
  
## <a name="types-of-data"></a><span data-ttu-id="2ad22-108">类型的数据</span><span class="sxs-lookup"><span data-stu-id="2ad22-108">Types of Data</span></span>  
 <span data-ttu-id="2ad22-109">本主题介绍了不同类型的使用日志记录功能和存储此数据的日志记录数据：</span><span class="sxs-lookup"><span data-stu-id="2ad22-109">This topic describes different types of logging data used by the logging feature and where this data is stored:</span></span>  
  
-   <span data-ttu-id="2ad22-110">配置数据： 日志记录配置数据存储在配置数据库 （也称为 BizTalk 管理数据库） 中并包含审核信息和审核数据的 SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件查看器中，集中数据库 WMI) 位置。</span><span class="sxs-lookup"><span data-stu-id="2ad22-110">Configuration data: Logging configuration data is stored in the Configuration database (also known as the BizTalk Management database) and includes SQL auditing information and audit data ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event viewer, centralized database WMI) location.</span></span>  
  
-   <span data-ttu-id="2ad22-111">存档数据： 事件日志中的 SQL 日志的表存储日志记录数据。</span><span class="sxs-lookup"><span data-stu-id="2ad22-111">Archival data: The EventLog table in the SQL log stores the 'Logging' data.</span></span>  
  
## <a name="how-logging-works"></a><span data-ttu-id="2ad22-112">日志记录的工作原理</span><span class="sxs-lookup"><span data-stu-id="2ad22-112">How Logging Works</span></span>  
 <span data-ttu-id="2ad22-113">本主题介绍三种类型的事件日志的软件，以及你可以在其中存储记录的数据的三个位置。</span><span class="sxs-lookup"><span data-stu-id="2ad22-113">This topic describes the three types of events the software logs, as well as the three locations where you can store the logged data.</span></span>  
  
|<span data-ttu-id="2ad22-114">组件</span><span class="sxs-lookup"><span data-stu-id="2ad22-114">Component</span></span>|<span data-ttu-id="2ad22-115">用途</span><span class="sxs-lookup"><span data-stu-id="2ad22-115">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="2ad22-116">配置编辑器</span><span class="sxs-lookup"><span data-stu-id="2ad22-116">Configuration Editor</span></span>|<span data-ttu-id="2ad22-117">若要指定保存的日志数据的位置。</span><span class="sxs-lookup"><span data-stu-id="2ad22-117">To specify where to save the log data.</span></span> <span data-ttu-id="2ad22-118">BTAHL7 支持记录到以下的任意组合： 事件查看器、 WMI 和 SQL Server 日志记录。</span><span class="sxs-lookup"><span data-stu-id="2ad22-118">BTAHL7 supports logging to any combination of the following: Event Viewer, WMI, and SQL Server logging.</span></span>|  
|<span data-ttu-id="2ad22-119">事件代理</span><span class="sxs-lookup"><span data-stu-id="2ad22-119">Event Broker</span></span>|<span data-ttu-id="2ad22-120">若要接收日志事件引发的其他组件并将它们记录基于日志记录配置数据。</span><span class="sxs-lookup"><span data-stu-id="2ad22-120">To receive log events raised by other components and log them based on logging configuration data.</span></span>|  
|<span data-ttu-id="2ad22-121">日志记录 API</span><span class="sxs-lookup"><span data-stu-id="2ad22-121">Logging API</span></span>|<span data-ttu-id="2ad22-122">由所有 BTAHL7 程序集的日志记录接口。</span><span class="sxs-lookup"><span data-stu-id="2ad22-122">Logging interface called by all BTAHL7 assemblies.</span></span>|  
  
### <a name="types-of-logging"></a><span data-ttu-id="2ad22-123">类型的日志记录</span><span class="sxs-lookup"><span data-stu-id="2ad22-123">Types of Logging</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="2ad22-124">日志三种类型的错误：</span><span class="sxs-lookup"><span data-stu-id="2ad22-124"> logs three types of errors:</span></span>  
  
-   <span data-ttu-id="2ad22-125">信息性事件，启动或停止服务或事件失败。</span><span class="sxs-lookup"><span data-stu-id="2ad22-125">Informational events, such a service started or stopped or an event failed.</span></span>  
  
-   <span data-ttu-id="2ad22-126">如非严重错误和警告中的警告事件[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件日志。</span><span class="sxs-lookup"><span data-stu-id="2ad22-126">Warning events such as non-critical errors and warnings in [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event logs.</span></span> <span data-ttu-id="2ad22-127">例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为数据验证失败。</span><span class="sxs-lookup"><span data-stu-id="2ad22-127">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because data validation failed.</span></span>  
  
-   <span data-ttu-id="2ad22-128">组件中的严重故障的错误事件。</span><span class="sxs-lookup"><span data-stu-id="2ad22-128">Error events for critical failures in a component.</span></span> <span data-ttu-id="2ad22-129">例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为分析器错误。</span><span class="sxs-lookup"><span data-stu-id="2ad22-129">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because of parser failures.</span></span>  
  
 <span data-ttu-id="2ad22-130">系统可以记录[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到下列可配置的位置的事件：</span><span class="sxs-lookup"><span data-stu-id="2ad22-130">The system can log [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] events into following configurable locations:</span></span>  
  
-   [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]<span data-ttu-id="2ad22-131">事件查看器</span><span class="sxs-lookup"><span data-stu-id="2ad22-131"> Event viewer</span></span>  
  
-   <span data-ttu-id="2ad22-132">WMI 事件</span><span class="sxs-lookup"><span data-stu-id="2ad22-132">WMI events</span></span>  
  
-   <span data-ttu-id="2ad22-133">集中的数据库 （SQL 日志记录数据库）</span><span class="sxs-lookup"><span data-stu-id="2ad22-133">Centralized database (SQL logging database)</span></span>  
  
 <span data-ttu-id="2ad22-134">事件 broker 接收所有[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志记录事件，基于的配置信息、 将它们发送到的适当位置。</span><span class="sxs-lookup"><span data-stu-id="2ad22-134">An event broker receives all [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging events and, based on the configuration information, sends them to the appropriate location.</span></span>  
  
### <a name="overview-of-features"></a><span data-ttu-id="2ad22-135">功能概述</span><span class="sxs-lookup"><span data-stu-id="2ad22-135">Overview of Features</span></span>  
 <span data-ttu-id="2ad22-136">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志记录功能提供了：</span><span class="sxs-lookup"><span data-stu-id="2ad22-136">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging feature provides:</span></span>  
  
-   <span data-ttu-id="2ad22-137">日志记录所有错误消息的统一的方法</span><span class="sxs-lookup"><span data-stu-id="2ad22-137">A unified way of logging all the error messages</span></span>  
  
-   <span data-ttu-id="2ad22-138">集中式存储库用于存储所有的事件详细信息</span><span class="sxs-lookup"><span data-stu-id="2ad22-138">A centralized repository for storing all event details</span></span>  
  
-   <span data-ttu-id="2ad22-139">日志记录消息流到离散的业务线应用程序一致的对象模型</span><span class="sxs-lookup"><span data-stu-id="2ad22-139">A consistent object model for logging messages flowing to discrete line-of-business applications</span></span>  
  
-   <span data-ttu-id="2ad22-140">日志记录和跟踪来帮助的系统管理员关联的组合的文档记录错误</span><span class="sxs-lookup"><span data-stu-id="2ad22-140">A combination of logging and tracing to help system administrators correlate logged errors with documents</span></span>  
  
## <a name="event-log-data"></a><span data-ttu-id="2ad22-141">事件日志数据</span><span class="sxs-lookup"><span data-stu-id="2ad22-141">Event Log Data</span></span>  
 <span data-ttu-id="2ad22-142">本主题介绍的格式和内容的事件日志数据。</span><span class="sxs-lookup"><span data-stu-id="2ad22-142">This topic describes the format and content of the event log data.</span></span>  
  
 <span data-ttu-id="2ad22-143">下表显示了有关合作伙伴的典型记录的数据。</span><span class="sxs-lookup"><span data-stu-id="2ad22-143">The following table shows typical logged data for partners.</span></span>  
  
|<span data-ttu-id="2ad22-144">data</span><span class="sxs-lookup"><span data-stu-id="2ad22-144">Data</span></span>|<span data-ttu-id="2ad22-145">Description</span><span class="sxs-lookup"><span data-stu-id="2ad22-145">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2ad22-146">日志数据</span><span class="sxs-lookup"><span data-stu-id="2ad22-146">LogData</span></span>|<span data-ttu-id="2ad22-147">数据日志</span><span class="sxs-lookup"><span data-stu-id="2ad22-147">Data log</span></span>|  
|<span data-ttu-id="2ad22-148">CategoryNumber</span><span class="sxs-lookup"><span data-stu-id="2ad22-148">CategoryNumber</span></span>|<span data-ttu-id="2ad22-149">类别号</span><span class="sxs-lookup"><span data-stu-id="2ad22-149">Category number</span></span>|  
|<span data-ttu-id="2ad22-150">EntryType</span><span class="sxs-lookup"><span data-stu-id="2ad22-150">EntryType</span></span>|<span data-ttu-id="2ad22-151">事件的类型</span><span class="sxs-lookup"><span data-stu-id="2ad22-151">Type of the event</span></span>|  
|<span data-ttu-id="2ad22-152">EventId</span><span class="sxs-lookup"><span data-stu-id="2ad22-152">EventId</span></span>|<span data-ttu-id="2ad22-153">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2ad22-153">Event ID</span></span>|  
|<span data-ttu-id="2ad22-154">MachineName</span><span class="sxs-lookup"><span data-stu-id="2ad22-154">MachineName</span></span>|<span data-ttu-id="2ad22-155">计算机名称</span><span class="sxs-lookup"><span data-stu-id="2ad22-155">Computer name</span></span>|  
|<span data-ttu-id="2ad22-156">消息</span><span class="sxs-lookup"><span data-stu-id="2ad22-156">Message</span></span>|<span data-ttu-id="2ad22-157">消息详细信息</span><span class="sxs-lookup"><span data-stu-id="2ad22-157">Message detail</span></span>|  
|<span data-ttu-id="2ad22-158">数据源</span><span class="sxs-lookup"><span data-stu-id="2ad22-158">Source</span></span>|<span data-ttu-id="2ad22-159">创建、 更新、 读取、 删除、 部署，或将数据存档</span><span class="sxs-lookup"><span data-stu-id="2ad22-159">Creating, updating, reading, deleting, deploying, or archiving data</span></span>|  
|<span data-ttu-id="2ad22-160">TimeGenerated</span><span class="sxs-lookup"><span data-stu-id="2ad22-160">TimeGenerated</span></span>|<span data-ttu-id="2ad22-161">成功或失败</span><span class="sxs-lookup"><span data-stu-id="2ad22-161">Success or Failure</span></span>|  
|<span data-ttu-id="2ad22-162">UserName</span><span class="sxs-lookup"><span data-stu-id="2ad22-162">UserName</span></span>|<span data-ttu-id="2ad22-163">用户名</span><span class="sxs-lookup"><span data-stu-id="2ad22-163">User name</span></span>|  
|<span data-ttu-id="2ad22-164">MsgGuid</span><span class="sxs-lookup"><span data-stu-id="2ad22-164">MsgGuid</span></span>|<span data-ttu-id="2ad22-165">消息 GUID</span><span class="sxs-lookup"><span data-stu-id="2ad22-165">Message GUID</span></span>|  
|<span data-ttu-id="2ad22-166">SvcGuid</span><span class="sxs-lookup"><span data-stu-id="2ad22-166">SvcGuid</span></span>|<span data-ttu-id="2ad22-167">服务 GUID</span><span class="sxs-lookup"><span data-stu-id="2ad22-167">Service GUID</span></span>|  
|<span data-ttu-id="2ad22-168">运算</span><span class="sxs-lookup"><span data-stu-id="2ad22-168">Operation</span></span>|<span data-ttu-id="2ad22-169">操作详细信息</span><span class="sxs-lookup"><span data-stu-id="2ad22-169">Operation detail</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ad22-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad22-170">See Also</span></span>  
 [<span data-ttu-id="2ad22-171">配置日志记录</span><span class="sxs-lookup"><span data-stu-id="2ad22-171">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)