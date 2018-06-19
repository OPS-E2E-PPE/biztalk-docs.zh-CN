---
title: 服务级别管理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b7ba1672660af2a68a5d193729a0a9009173d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294725"
---
# <a name="service-level-management"></a><span data-ttu-id="27e97-102">服务级别管理</span><span class="sxs-lookup"><span data-stu-id="27e97-102">Service Level Management</span></span>
<span data-ttu-id="27e97-103">AmberPoint SMS 服务级别管理器提供了到特定的性能和企业级 SOA 基于系统内的可用性问题的可见性。</span><span class="sxs-lookup"><span data-stu-id="27e97-103">The AmberPoint SMS Service Level Manager provides visibility into specific performance and availability issues within enterprise-level SOA-based systems.</span></span> <span data-ttu-id="27e97-104">它会检测并为每个 Microsoft BizTalk Server 接收位置和发送端口跟踪度量值。</span><span class="sxs-lookup"><span data-stu-id="27e97-104">It instruments and tracks the metrics for each Microsoft BizTalk Server receive location and send port.</span></span> <span data-ttu-id="27e97-105">这可实时运行状况和状态指示，除了这些组件的正在进行的性能特征描述。</span><span class="sxs-lookup"><span data-stu-id="27e97-105">This provides real-time health and status indication, in addition to ongoing performance characterization of these components.</span></span> <span data-ttu-id="27e97-106">图 1 显示与接收位置相关联的度量值的显示。</span><span class="sxs-lookup"><span data-stu-id="27e97-106">Figure 1 shows the display of the metrics associated with a receive location.</span></span>  
  
 <span data-ttu-id="27e97-107">![AmberPoint 接收位置](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9 AmberPointReceiveLocation")</span><span class="sxs-lookup"><span data-stu-id="27e97-107">![AmberPoint Receive Location](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")</span></span>  
  
 <span data-ttu-id="27e97-108">**图 1**</span><span class="sxs-lookup"><span data-stu-id="27e97-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="27e97-109">**接收位置与关联的度量值**</span><span class="sxs-lookup"><span data-stu-id="27e97-109">**The metrics associated with a receive location**</span></span>  
  
 <span data-ttu-id="27e97-110">AmberPoint 实时运行分析允许用户设置阈值和系统跨越严重事件阈值，包括符合性警告事件、 符合性冲突事件和后续返回到符合性时发送警报。</span><span class="sxs-lookup"><span data-stu-id="27e97-110">AmberPoint run-time analytics allow users to set thresholds and send alerts when a system crosses a critical event threshold, including compliance warnings events, compliance violations events, and a subsequent return to compliance.</span></span> <span data-ttu-id="27e97-111">图 2 显示的显示，其中用户配置服务级别协议和查看针对此服务级别协议生成的警报。</span><span class="sxs-lookup"><span data-stu-id="27e97-111">Figure 2 shows the display where users configure service level agreements and view alerts generated for this service level agreement.</span></span>  
  
 <span data-ttu-id="27e97-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9 AmberPointSLA")</span><span class="sxs-lookup"><span data-stu-id="27e97-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")</span></span>  
  
 <span data-ttu-id="27e97-113">**图 2**</span><span class="sxs-lookup"><span data-stu-id="27e97-113">**Figure 2**</span></span>  
  
 <span data-ttu-id="27e97-114">**屏幕以配置服务级别协议和查看警报**</span><span class="sxs-lookup"><span data-stu-id="27e97-114">**The screens to configure a service level agreement and view alerts**</span></span>  
  
 <span data-ttu-id="27e97-115">你可以建立服务级别管理器中的性能目标。</span><span class="sxs-lookup"><span data-stu-id="27e97-115">You can establish performance targets within the Service Level Manager.</span></span> <span data-ttu-id="27e97-116">软件然后跟踪各个消息、 来自特定用户的消息从组的用户，来衡量针对这些目标的性能。</span><span class="sxs-lookup"><span data-stu-id="27e97-116">The software then tracks individual messages, messages from a specific user, or messages from groups of users, to measure performance against these targets.</span></span>  
  
 <span data-ttu-id="27e97-117">你还可以配置日志记录策略，以指导 AmberPoint SMS 动态收集并检查消息上下文和 BizTalk Server 中，通过传递数据，如图 3 中所示。</span><span class="sxs-lookup"><span data-stu-id="27e97-117">You can also configure logging policies that instruct AmberPoint SMS to dynamically collect and inspect message context and data passing through BizTalk Server, as shown in Figure 3.</span></span> <span data-ttu-id="27e97-118">你可以然后使用这些日志进行故障排除"即时上"、 技术分析问题，以及进行存档符合特定于行业的法规。</span><span class="sxs-lookup"><span data-stu-id="27e97-118">You can then use these logs for "on-the-fly" troubleshooting, for technical analysis of problems, and for archiving to comply with industry-specific regulations.</span></span>  
  
 <span data-ttu-id="27e97-119">![BizTalk 服务消息](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9 BizTalkServiceMessages")</span><span class="sxs-lookup"><span data-stu-id="27e97-119">![BizTalk Service Messages](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")</span></span>  
  
 <span data-ttu-id="27e97-120">**图 3**</span><span class="sxs-lookup"><span data-stu-id="27e97-120">**Figure 3**</span></span>  
  
 <span data-ttu-id="27e97-121">**BizTalk Server 服务消息日志文件**</span><span class="sxs-lookup"><span data-stu-id="27e97-121">**The log file for BizTalk Server service messages**</span></span>