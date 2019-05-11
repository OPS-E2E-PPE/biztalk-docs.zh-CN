---
title: 使用 Operations Manager 2007 监视的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a5026c-ef59-498b-9bef-ea0f1c932eae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afdc0c4e9d89b83aedf184dc138a3558ef3f5eec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399311"
---
# <a name="best-practices-for-monitoring-with-operations-manager-2007"></a><span data-ttu-id="f5f17-102">监视使用 Operations Manager 2007 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="f5f17-102">Best Practices for Monitoring with Operations Manager 2007</span></span>
<span data-ttu-id="f5f17-103">遵循本主题以有效地监视使用 Operations Manager 2007 的应用程序中列出的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="f5f17-103">Adhere to the best practices listed in this topic to effectively monitor your applications using Operations Manager 2007.</span></span>  
  
 <span data-ttu-id="f5f17-104">**安装更完整的覆盖范围的附加管理包**</span><span class="sxs-lookup"><span data-stu-id="f5f17-104">**Install additional management packs for more complete coverage**</span></span>  
  
- <span data-ttu-id="f5f17-105">为确保 Operations Manager 2007 监视中的关键应用程序在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，应安装以下管理包：</span><span class="sxs-lookup"><span data-stu-id="f5f17-105">To help ensure that Operations Manager 2007 monitors the key applications in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, you should install the following management packs:</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f5f17-106">（必需）</span><span class="sxs-lookup"><span data-stu-id="f5f17-106">(required)</span></span>  
  
  - <span data-ttu-id="f5f17-107">Windows Server Operating System （可选）</span><span class="sxs-lookup"><span data-stu-id="f5f17-107">Windows Server Operating System (optional)</span></span>  
  
  - <span data-ttu-id="f5f17-108">Microsoft Windows Server 故障转移群集 （如果群集是使用 （可选））</span><span class="sxs-lookup"><span data-stu-id="f5f17-108">Microsoft Windows Server Failover Cluster (if clusters are used, optional)</span></span>  
  
  - <span data-ttu-id="f5f17-109">SQL Server 监视</span><span class="sxs-lookup"><span data-stu-id="f5f17-109">SQL Server Monitoring</span></span>  
  
  - <span data-ttu-id="f5f17-110">Internet Information Services 7</span><span class="sxs-lookup"><span data-stu-id="f5f17-110">Internet Information Services 7</span></span>  
  
  - <span data-ttu-id="f5f17-111">消息队列 (MSMQ) 5.0 （可选）</span><span class="sxs-lookup"><span data-stu-id="f5f17-111">Message Queuing (MSMQ) 5.0 (optional)</span></span>  
  
  <span data-ttu-id="f5f17-112">**查看并确定每日警报优先级**</span><span class="sxs-lookup"><span data-stu-id="f5f17-112">**Review and prioritize alerts on a daily basis**</span></span>  
  
- <span data-ttu-id="f5f17-113">检查并确定每日警报优先级有助于确保及时地解决问题。</span><span class="sxs-lookup"><span data-stu-id="f5f17-113">Reviewing and prioritizing alerts on a daily basis helps to ensure that issues are resolved in a timely manner.</span></span>  
  
  <span data-ttu-id="f5f17-114">**验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Operations Manager 2007 服务器通信。**</span><span class="sxs-lookup"><span data-stu-id="f5f17-114">**Verify that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is communicating with the Operations Manager 2007 server.**</span></span>  
  
- <span data-ttu-id="f5f17-115">如果运行的服务器之间的通信失败[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与监视基础结构，您将不会收到警报。</span><span class="sxs-lookup"><span data-stu-id="f5f17-115">If communication fails between the servers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the monitoring infrastructure, you will not receive alerts.</span></span>  
  
  <span data-ttu-id="f5f17-116">**启用和禁用规则，根据需要**</span><span class="sxs-lookup"><span data-stu-id="f5f17-116">**Enable and disable rules as necessary**</span></span>  
  
- <span data-ttu-id="f5f17-117">默认情况下中的规则的一些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="f5f17-117">By default, some of the rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack are disabled.</span></span> <span data-ttu-id="f5f17-118">这些禁用的规则属于以下类型： 需要自定义，用作模板的规则和规则用于监视其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事件。</span><span class="sxs-lookup"><span data-stu-id="f5f17-118">These disabled rules are of the following types: rules needing customization, rules that serve as templates, and rules for monitoring additional [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] events.</span></span> <span data-ttu-id="f5f17-119">请确保相关的规则你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]之外的环境。</span><span class="sxs-lookup"><span data-stu-id="f5f17-119">Make sure the relevant rules for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment are enabled.</span></span>  
  
  <span data-ttu-id="f5f17-120">**自定义规则根据您的环境**</span><span class="sxs-lookup"><span data-stu-id="f5f17-120">**Customize rules as necessary for your environment**</span></span>  
  
- <span data-ttu-id="f5f17-121">您应该自定义中的规则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，以满足你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="f5f17-121">You should customize the rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack to suit your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span> <span data-ttu-id="f5f17-122">某些规则需要监视阈值或时间阈值定义的最佳基于您的特定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="f5f17-122">Some rules require monitoring thresholds or time thresholds that are best defined based on your specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
  <span data-ttu-id="f5f17-123">**创建其他规则有必要，请根据中包含的规则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包**</span><span class="sxs-lookup"><span data-stu-id="f5f17-123">**Create additional rules as necessary, based on the rules included in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack**</span></span>  
  
- <span data-ttu-id="f5f17-124">规则提供用于连接作为项目的创建，如模板[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机。</span><span class="sxs-lookup"><span data-stu-id="f5f17-124">Rules are provided for use as templates for artifacts that you create, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts.</span></span> <span data-ttu-id="f5f17-125">创建特定于项目的规则，如时，应使用这些模板规则作为参考：</span><span class="sxs-lookup"><span data-stu-id="f5f17-125">You should use these template rules as a reference when creating artifact-specific rules such as:</span></span>  
  
  -   <span data-ttu-id="f5f17-126">特定于主机的规则，例如，托管队列监视，并托管阻止监视</span><span class="sxs-lookup"><span data-stu-id="f5f17-126">Host-specific rules, for example, host queue monitoring, and host throttling monitoring</span></span>  
  
  -   <span data-ttu-id="f5f17-127">特定于 MessageBox 的规则</span><span class="sxs-lookup"><span data-stu-id="f5f17-127">MessageBox-specific rules</span></span>  
  
  -   <span data-ttu-id="f5f17-128">对于其他第三方组件，例如，MQSeries 适配器的规则</span><span class="sxs-lookup"><span data-stu-id="f5f17-128">Rules for additional third party components, for example, MQSeries adapter</span></span>  
  
  <span data-ttu-id="f5f17-129">**监视所有 BizTalk Server 相关组件**</span><span class="sxs-lookup"><span data-stu-id="f5f17-129">**Monitor all the BizTalk Server related components**</span></span>  
  
  <span data-ttu-id="f5f17-130">组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应监视以确保它们运行的环境包括但不是一定是限制为：</span><span class="sxs-lookup"><span data-stu-id="f5f17-130">The components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment that you should monitor to ensure that they are running include, but are not necessarily limited to:</span></span>  
  
- <span data-ttu-id="f5f17-131">BizTalk 主机实例</span><span class="sxs-lookup"><span data-stu-id="f5f17-131">BizTalk Host instances</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] <span data-ttu-id="f5f17-132">使用安装的代理作业 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5f17-132">Agent jobs installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="f5f17-133">为 BizTalk 解决方案开发的任何自定义服务</span><span class="sxs-lookup"><span data-stu-id="f5f17-133">Any custom services developed for the BizTalk solution</span></span>  
  
- <span data-ttu-id="f5f17-134">为 BizTalk 解决方案开发的任何自定义数据库的状态</span><span class="sxs-lookup"><span data-stu-id="f5f17-134">Status of any custom databases developed for the BizTalk solution</span></span>  
  
- <span data-ttu-id="f5f17-135">与相关的任何自定义事件日志条目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境</span><span class="sxs-lookup"><span data-stu-id="f5f17-135">Any custom event log entries relevant to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f17-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5f17-136">See Also</span></span>  
 [<span data-ttu-id="f5f17-137">使用 System Center Operations Manager 2007 监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f5f17-137">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)