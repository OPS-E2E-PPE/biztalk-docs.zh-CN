---
title: 向外扩展处理主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- hosts, processing
- hosts, high availability
- scaling, hosts
- hosts, planning
- hosts, scaling
- clustering
ms.assetid: c72ce8fc-7593-4700-8398-23d1a20515c3
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93959c75a786d9f6df69913aa233205d414ee5b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309342"
---
# <a name="scaled-out-processing-hosts"></a><span data-ttu-id="c9994-102">向外扩展处理主机</span><span class="sxs-lookup"><span data-stu-id="c9994-102">Scaled-Out Processing Hosts</span></span>
<span data-ttu-id="c9994-103">向外扩展处理主机可以提高性能，并隔离到两个或多个单独的主机计算机上的业务流程功能，从而提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="c9994-103">A scaled-out processing host improves performance and provides high availability by isolating orchestration functionality onto two or more separate host computers.</span></span> <span data-ttu-id="c9994-104">这种隔离可让你将多台计算机添加到冗余的处理主机。</span><span class="sxs-lookup"><span data-stu-id="c9994-104">This isolation lets you add multiple computers to a processing host for redundancy.</span></span> <span data-ttu-id="c9994-105">在 Microsoft 中的处理主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行一个或多个主机实例的坐标各种业务流程并创建为业务流程的编程对象的实例。</span><span class="sxs-lookup"><span data-stu-id="c9994-105">A processing host in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runs one or more host instances that coordinate various business processes and creates an instance of programmatic objects for orchestrations.</span></span>  
  
 <span data-ttu-id="c9994-106">下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机上运行的处理主机实例的处理主机提供高可用性的部署。</span><span class="sxs-lookup"><span data-stu-id="c9994-106">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the processing host by having two computers that are running instances of the processing host.</span></span> <span data-ttu-id="c9994-107">请注意，在此图中的接收和发送主机并不高度可用。</span><span class="sxs-lookup"><span data-stu-id="c9994-107">Note that in this figure the receiving and sending hosts are not highly available.</span></span>  
  
 <span data-ttu-id="c9994-108">![向外扩展处理主机](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")</span><span class="sxs-lookup"><span data-stu-id="c9994-108">![Scaled Out Processing Host](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")</span></span>  
  
 <span data-ttu-id="c9994-109">在此配置中，用于处理业务流程的工作是两个之间的负载平衡[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有处理主机的实例，均可独立运行的计算机。</span><span class="sxs-lookup"><span data-stu-id="c9994-109">In this configuration, the work for processing orchestrations is load balanced between two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers that have instances of the processing host and run independently of each other.</span></span> <span data-ttu-id="c9994-110">如果一台计算机遇到错误或失败，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动使用在另一台计算机上的主机实例来处理剩余的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c9994-110">If one computer encounters errors or fails, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically uses the host instance on the other computer to process remaining orchestrations.</span></span>  
  
## <a name="maintaining-orchestration-state"></a><span data-ttu-id="c9994-111">维护业务流程的状态</span><span class="sxs-lookup"><span data-stu-id="c9994-111">Maintaining Orchestration State</span></span>  
 <span data-ttu-id="c9994-112">BizTalk Server 业务流程中维护状态集中 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，并不是本地上每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="c9994-112">BizTalk Server maintains orchestration state centrally in Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and not locally on each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="c9994-113">通过保持在 MessageBox 数据库中，状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从而克服了依赖于单个处理主机实例来处理该业务流程的限制，并允许处理业务流程的任何处理主机实例。</span><span class="sxs-lookup"><span data-stu-id="c9994-113">By persisting the state in the MessageBox database, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] overcomes the limitation of relying on a single processing host instance to process the orchestration, and lets any processing host instance process the orchestration.</span></span> <span data-ttu-id="c9994-114">如果发生错误时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]某一业务流程，相同的处理主机的另一个实例的进程可以完成最后保存的状态从业务流程。</span><span class="sxs-lookup"><span data-stu-id="c9994-114">If an error occurs while [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes an orchestration, another instance of the same processing host can complete the orchestration from the last persisted state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9994-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9994-115">See Also</span></span>  
 [<span data-ttu-id="c9994-116">为 BizTalk 主机提供高可用性</span><span class="sxs-lookup"><span data-stu-id="c9994-116">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)