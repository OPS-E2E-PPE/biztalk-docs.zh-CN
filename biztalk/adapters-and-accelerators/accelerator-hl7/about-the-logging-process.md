---
title: 有关日志记录进程 |Microsoft Docs
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
ms.openlocfilehash: 110c7d4505e6518836fa481ed268771aef72d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981054"
---
# <a name="about-the-logging-process"></a><span data-ttu-id="612cc-102">有关日志记录进程</span><span class="sxs-lookup"><span data-stu-id="612cc-102">About the Logging Process</span></span>
<span data-ttu-id="612cc-103">你的应用程序处理关键，因为时间敏感和货币数据，审核将成为应用程序的关键部分。</span><span class="sxs-lookup"><span data-stu-id="612cc-103">Since your applications handle critical, time sensitive and monetary data, auditing becomes a critical part of the application.</span></span> <span data-ttu-id="612cc-104">若要启用企业级可管理性和可用性，Microsoft[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]依赖以下共享运行的时和管理组件：</span><span class="sxs-lookup"><span data-stu-id="612cc-104">To enable enterprise level manageability and availability, Microsoft [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] relies on the following shared run time and administrative components:</span></span>  
  
- <span data-ttu-id="612cc-105">**日志记录**： 若要收集和路由的所有日志事件中指定的数据库的托管方法</span><span class="sxs-lookup"><span data-stu-id="612cc-105">**Logging**: to collect and route all log events in a managed way to a designated database</span></span>  
  
- <span data-ttu-id="612cc-106">**事件监视和调试服务**： 若要配置日志记录行为以及调查/管理面向系统管理员和其他 IT 专业人员收集的信息</span><span class="sxs-lookup"><span data-stu-id="612cc-106">**Event Monitoring and Service Debugging**: to configure logging behavior and to investigate/manage collected information for system administrators and other IT professionals</span></span>  
  
  <span data-ttu-id="612cc-107">与增强审核中的功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，可以优化运营效率、 安全性和性能，以确保 HL7 法规符合性。</span><span class="sxs-lookup"><span data-stu-id="612cc-107">With the enhanced auditing features in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], you can optimize your operational efficiency, security, and performance to ensure compliance with HL7 regulations.</span></span>  
  
## <a name="types-of-data"></a><span data-ttu-id="612cc-108">类型的数据</span><span class="sxs-lookup"><span data-stu-id="612cc-108">Types of Data</span></span>  
 <span data-ttu-id="612cc-109">本主题介绍不同类型的日志记录功能和存储此数据使用的日志记录数据：</span><span class="sxs-lookup"><span data-stu-id="612cc-109">This topic describes different types of logging data used by the logging feature and where this data is stored:</span></span>  
  
- <span data-ttu-id="612cc-110">配置数据： 日志记录配置数据存储在配置数据库 （也称为 BizTalk 管理数据库） 中并包含审核信息和审核数据的 SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件查看器中，集中式数据库 WMI) 位置。</span><span class="sxs-lookup"><span data-stu-id="612cc-110">Configuration data: Logging configuration data is stored in the Configuration database (also known as the BizTalk Management database) and includes SQL auditing information and audit data ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event viewer, centralized database WMI) location.</span></span>  
  
- <span data-ttu-id="612cc-111">存档数据： 事件日志表中的 SQL 日志存储日志记录的数据。</span><span class="sxs-lookup"><span data-stu-id="612cc-111">Archival data: The EventLog table in the SQL log stores the 'Logging' data.</span></span>  
  
## <a name="how-logging-works"></a><span data-ttu-id="612cc-112">日志记录的工作原理</span><span class="sxs-lookup"><span data-stu-id="612cc-112">How Logging Works</span></span>  
 <span data-ttu-id="612cc-113">本主题介绍三种类型的事件日志的软件，以及可以在其中存储日志的数据的三个位置。</span><span class="sxs-lookup"><span data-stu-id="612cc-113">This topic describes the three types of events the software logs, as well as the three locations where you can store the logged data.</span></span>  
  
|<span data-ttu-id="612cc-114">组件</span><span class="sxs-lookup"><span data-stu-id="612cc-114">Component</span></span>|<span data-ttu-id="612cc-115">用途</span><span class="sxs-lookup"><span data-stu-id="612cc-115">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="612cc-116">配置编辑器</span><span class="sxs-lookup"><span data-stu-id="612cc-116">Configuration Editor</span></span>|<span data-ttu-id="612cc-117">若要指定保存日志数据的位置。</span><span class="sxs-lookup"><span data-stu-id="612cc-117">To specify where to save the log data.</span></span> <span data-ttu-id="612cc-118">BTAHL7 支持日志记录到以下任意组合： 事件查看器、 WMI 和 SQL Server 日志记录。</span><span class="sxs-lookup"><span data-stu-id="612cc-118">BTAHL7 supports logging to any combination of the following: Event Viewer, WMI, and SQL Server logging.</span></span>|  
|<span data-ttu-id="612cc-119">事件代理</span><span class="sxs-lookup"><span data-stu-id="612cc-119">Event Broker</span></span>|<span data-ttu-id="612cc-120">若要接收日志事件引发的其他组件，并记录基于配置数据的日志记录。</span><span class="sxs-lookup"><span data-stu-id="612cc-120">To receive log events raised by other components and log them based on logging configuration data.</span></span>|  
|<span data-ttu-id="612cc-121">日志记录 API</span><span class="sxs-lookup"><span data-stu-id="612cc-121">Logging API</span></span>|<span data-ttu-id="612cc-122">日志记录调用 BTAHL7 的所有程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="612cc-122">Logging interface called by all BTAHL7 assemblies.</span></span>|  
  
### <a name="types-of-logging"></a><span data-ttu-id="612cc-123">类型的日志记录</span><span class="sxs-lookup"><span data-stu-id="612cc-123">Types of Logging</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="612cc-124"> 日志三种类型的错误：</span><span class="sxs-lookup"><span data-stu-id="612cc-124"> logs three types of errors:</span></span>  
  
- <span data-ttu-id="612cc-125">信息性事件、 启动或停止的服务或事件失败。</span><span class="sxs-lookup"><span data-stu-id="612cc-125">Informational events, such a service started or stopped or an event failed.</span></span>  
  
- <span data-ttu-id="612cc-126">警告事件，例如非严重错误和警告中的[!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]事件日志。</span><span class="sxs-lookup"><span data-stu-id="612cc-126">Warning events such as non-critical errors and warnings in [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event logs.</span></span> <span data-ttu-id="612cc-127">例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为数据验证失败。</span><span class="sxs-lookup"><span data-stu-id="612cc-127">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because data validation failed.</span></span>  
  
- <span data-ttu-id="612cc-128">在组件中的严重故障的错误事件。</span><span class="sxs-lookup"><span data-stu-id="612cc-128">Error events for critical failures in a component.</span></span> <span data-ttu-id="612cc-129">例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]挂起消息，因为分析器错误。</span><span class="sxs-lookup"><span data-stu-id="612cc-129">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because of parser failures.</span></span>  
  
  <span data-ttu-id="612cc-130">系统可以记录[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到下列可配置的位置的事件：</span><span class="sxs-lookup"><span data-stu-id="612cc-130">The system can log [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] events into following configurable locations:</span></span>  
  
- [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]<span data-ttu-id="612cc-131"> 事件查看器</span><span class="sxs-lookup"><span data-stu-id="612cc-131"> Event viewer</span></span>  
  
- <span data-ttu-id="612cc-132">WMI 事件</span><span class="sxs-lookup"><span data-stu-id="612cc-132">WMI events</span></span>  
  
- <span data-ttu-id="612cc-133">集中式的数据库 （SQL 日志记录数据库）</span><span class="sxs-lookup"><span data-stu-id="612cc-133">Centralized database (SQL logging database)</span></span>  
  
  <span data-ttu-id="612cc-134">事件代理接收所有[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]记录事件和，基于配置信息，请在将其发送到相应的位置。</span><span class="sxs-lookup"><span data-stu-id="612cc-134">An event broker receives all [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging events and, based on the configuration information, sends them to the appropriate location.</span></span>  
  
### <a name="overview-of-features"></a><span data-ttu-id="612cc-135">功能概述</span><span class="sxs-lookup"><span data-stu-id="612cc-135">Overview of Features</span></span>  
 <span data-ttu-id="612cc-136">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]日志记录功能提供了：</span><span class="sxs-lookup"><span data-stu-id="612cc-136">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging feature provides:</span></span>  
  
-   <span data-ttu-id="612cc-137">一种统一日志记录所有错误消息的方法</span><span class="sxs-lookup"><span data-stu-id="612cc-137">A unified way of logging all the error messages</span></span>  
  
-   <span data-ttu-id="612cc-138">用于存储所有事件的详细信息的集中式存储库</span><span class="sxs-lookup"><span data-stu-id="612cc-138">A centralized repository for storing all event details</span></span>  
  
-   <span data-ttu-id="612cc-139">日志记录消息流到离散的业务线应用程序一致的对象模型</span><span class="sxs-lookup"><span data-stu-id="612cc-139">A consistent object model for logging messages flowing to discrete line-of-business applications</span></span>  
  
-   <span data-ttu-id="612cc-140">日志记录和跟踪来帮助的系统管理员将关联的组合记录了错误的文档</span><span class="sxs-lookup"><span data-stu-id="612cc-140">A combination of logging and tracing to help system administrators correlate logged errors with documents</span></span>  
  
## <a name="event-log-data"></a><span data-ttu-id="612cc-141">事件日志数据</span><span class="sxs-lookup"><span data-stu-id="612cc-141">Event Log Data</span></span>  
 <span data-ttu-id="612cc-142">本主题介绍的格式和内容的事件日志数据。</span><span class="sxs-lookup"><span data-stu-id="612cc-142">This topic describes the format and content of the event log data.</span></span>  
  
 <span data-ttu-id="612cc-143">下表显示适用于合作伙伴的典型记录的数据。</span><span class="sxs-lookup"><span data-stu-id="612cc-143">The following table shows typical logged data for partners.</span></span>  
  
|<span data-ttu-id="612cc-144">data</span><span class="sxs-lookup"><span data-stu-id="612cc-144">Data</span></span>|<span data-ttu-id="612cc-145">Description</span><span class="sxs-lookup"><span data-stu-id="612cc-145">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="612cc-146">日志数据</span><span class="sxs-lookup"><span data-stu-id="612cc-146">LogData</span></span>|<span data-ttu-id="612cc-147">数据日志</span><span class="sxs-lookup"><span data-stu-id="612cc-147">Data log</span></span>|  
|<span data-ttu-id="612cc-148">CategoryNumber</span><span class="sxs-lookup"><span data-stu-id="612cc-148">CategoryNumber</span></span>|<span data-ttu-id="612cc-149">分类数</span><span class="sxs-lookup"><span data-stu-id="612cc-149">Category number</span></span>|  
|<span data-ttu-id="612cc-150">EntryType</span><span class="sxs-lookup"><span data-stu-id="612cc-150">EntryType</span></span>|<span data-ttu-id="612cc-151">事件的类型</span><span class="sxs-lookup"><span data-stu-id="612cc-151">Type of the event</span></span>|  
|<span data-ttu-id="612cc-152">存在 EventId</span><span class="sxs-lookup"><span data-stu-id="612cc-152">EventId</span></span>|<span data-ttu-id="612cc-153">事件 ID</span><span class="sxs-lookup"><span data-stu-id="612cc-153">Event ID</span></span>|  
|<span data-ttu-id="612cc-154">MachineName</span><span class="sxs-lookup"><span data-stu-id="612cc-154">MachineName</span></span>|<span data-ttu-id="612cc-155">计算机名称</span><span class="sxs-lookup"><span data-stu-id="612cc-155">Computer name</span></span>|  
|<span data-ttu-id="612cc-156">消息</span><span class="sxs-lookup"><span data-stu-id="612cc-156">Message</span></span>|<span data-ttu-id="612cc-157">消息详细信息</span><span class="sxs-lookup"><span data-stu-id="612cc-157">Message detail</span></span>|  
|<span data-ttu-id="612cc-158">数据源</span><span class="sxs-lookup"><span data-stu-id="612cc-158">Source</span></span>|<span data-ttu-id="612cc-159">创建、 更新、 读取、 删除、 部署，或将数据存档</span><span class="sxs-lookup"><span data-stu-id="612cc-159">Creating, updating, reading, deleting, deploying, or archiving data</span></span>|  
|<span data-ttu-id="612cc-160">TimeGenerated</span><span class="sxs-lookup"><span data-stu-id="612cc-160">TimeGenerated</span></span>|<span data-ttu-id="612cc-161">成功或失败</span><span class="sxs-lookup"><span data-stu-id="612cc-161">Success or Failure</span></span>|  
|<span data-ttu-id="612cc-162">UserName</span><span class="sxs-lookup"><span data-stu-id="612cc-162">UserName</span></span>|<span data-ttu-id="612cc-163">“用户名”</span><span class="sxs-lookup"><span data-stu-id="612cc-163">User name</span></span>|  
|<span data-ttu-id="612cc-164">MsgGuid</span><span class="sxs-lookup"><span data-stu-id="612cc-164">MsgGuid</span></span>|<span data-ttu-id="612cc-165">消息的 GUID</span><span class="sxs-lookup"><span data-stu-id="612cc-165">Message GUID</span></span>|  
|<span data-ttu-id="612cc-166">SvcGuid</span><span class="sxs-lookup"><span data-stu-id="612cc-166">SvcGuid</span></span>|<span data-ttu-id="612cc-167">服务 GUID</span><span class="sxs-lookup"><span data-stu-id="612cc-167">Service GUID</span></span>|  
|<span data-ttu-id="612cc-168">运算</span><span class="sxs-lookup"><span data-stu-id="612cc-168">Operation</span></span>|<span data-ttu-id="612cc-169">操作详细信息</span><span class="sxs-lookup"><span data-stu-id="612cc-169">Operation detail</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="612cc-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="612cc-170">See Also</span></span>  
 [<span data-ttu-id="612cc-171">配置日志记录</span><span class="sxs-lookup"><span data-stu-id="612cc-171">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)