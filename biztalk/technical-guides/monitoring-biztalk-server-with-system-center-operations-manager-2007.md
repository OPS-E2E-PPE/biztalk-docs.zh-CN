---
title: 监视 BizTalk Server 使用 System Center Operations Manager 2007 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cee8275-bbd0-435f-ac54-07f582190538
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8005fa8287b7156374445b1a596a2c4bc21709c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379485"
---
# <a name="monitoring-biztalk-server-with-system-center-operations-manager-2007"></a><span data-ttu-id="ec7ef-102">监视 BizTalk Server 使用 System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="ec7ef-102">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>
<span data-ttu-id="ec7ef-103">监视 BizTalk 应用程序和基础结构与 Microsoft System Center Operations Manager (Operations Manager) 是首选的监视方法。</span><span class="sxs-lookup"><span data-stu-id="ec7ef-103">Monitoring your BizTalk applications and infrastructure with Microsoft System Center Operations Manager (Operations Manager) is the preferred monitoring approach.</span></span> <span data-ttu-id="ec7ef-104">Operations Manager 的 Microsoft BizTalk Server 管理包提供运行的计算机的主动式和反应式监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ec7ef-104">The Microsoft BizTalk Server management packs for Operations Manager provide proactive and reactive monitoring of computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ec7ef-105">这些管理包提供了几十个内置的可自定义规则以允许进行全面和自动监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ec7ef-105">These management packs provide dozens of built-in, customizable rules to allow for comprehensive and automated monitoring of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ec7ef-106">以下 BizTalk Server 管理包是可与 Operations Manager 一起使用：</span><span class="sxs-lookup"><span data-stu-id="ec7ef-106">The following BizTalk Server management pack is available for use with Operations Manager:</span></span>  
  
- <span data-ttu-id="ec7ef-107">[监视管理包的 BizTalk Server 2010](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666)。</span><span class="sxs-lookup"><span data-stu-id="ec7ef-107">[BizTalk Server 2010 Monitoring Management Pack](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666).</span></span>  
  
  <span data-ttu-id="ec7ef-108">操作指南此部分包含的背景信息、 最佳实践、 检查表和可用于帮助实现基于 Operations Manager 的监视策略的过程。</span><span class="sxs-lookup"><span data-stu-id="ec7ef-108">This section of the operations guide includes background information, best practices, checklists, and procedures that you can use to assist in implementing a monitoring strategy based on Operations Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec7ef-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="ec7ef-109">In This Section</span></span>  
  
-   [<span data-ttu-id="ec7ef-110">使用 Operations Manager 2007 进行监视的最佳做法</span><span class="sxs-lookup"><span data-stu-id="ec7ef-110">Best Practices for Monitoring with Operations Manager 2007</span></span>](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)  
  
-   [<span data-ttu-id="ec7ef-111">使用性能阈值规则监视带宽限制</span><span class="sxs-lookup"><span data-stu-id="ec7ef-111">Monitoring Throttling Using Performance Threshold Rules</span></span>](../technical-guides/monitoring-throttling-using-performance-threshold-rules.md)  
  
-   [<span data-ttu-id="ec7ef-112">监视 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec7ef-112">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)  
  
-   [<span data-ttu-id="ec7ef-113">监视应用程序和主机实例</span><span class="sxs-lookup"><span data-stu-id="ec7ef-113">Monitoring Applications and Host Instances</span></span>](../technical-guides/monitoring-applications-and-host-instances.md)