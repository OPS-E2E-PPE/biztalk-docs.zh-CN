---
title: 端到端事务跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7d19c4ce9bc30d60144ed69fc14f2323b4379d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306192"
---
# <a name="end-to-end-transaction-tracking"></a><span data-ttu-id="d4aff-102">端到端事务跟踪</span><span class="sxs-lookup"><span data-stu-id="d4aff-102">End-to-End Transaction Tracking</span></span>
<span data-ttu-id="d4aff-103">业务可见性与操作员和用户的能力，若要监视的流量通过在运行时环境的流。</span><span class="sxs-lookup"><span data-stu-id="d4aff-103">Business visibility relates to the ability of operators and users to monitor the flow of traffic through the run-time environment.</span></span> <span data-ttu-id="d4aff-104">企业必须能够跟踪的进程和事务中通过他们在每个步骤以确保它们完成的贡献创收到其相应的系统。</span><span class="sxs-lookup"><span data-stu-id="d4aff-104">Enterprises must be able to track the processes and transactions flowing through their systems at each step to ensure that they play their part in contributing to revenue generation.</span></span> <span data-ttu-id="d4aff-105">AmberPoint SMS 简化了度量和 Microsoft BizTalk Server 中的这些消息的跟踪。</span><span class="sxs-lookup"><span data-stu-id="d4aff-105">AmberPoint SMS simplifies the measurement and tracking of these messages in Microsoft BizTalk Server.</span></span> <span data-ttu-id="d4aff-106">系统允许用户定义新的管理单元的端到端业务流程，而不是要求开发人员选择用来打包和部署单个服务组件的方式符合与保持一致。</span><span class="sxs-lookup"><span data-stu-id="d4aff-106">The system allows users to define new units of management that align with end-to-end business process flows, instead of being required to conform to the way developers chose to package and deploy individual service components.</span></span> <span data-ttu-id="d4aff-107">图 1 显示了用于定义管理单位的屏幕。</span><span class="sxs-lookup"><span data-stu-id="d4aff-107">Figure 1 shows the screen for defining management units.</span></span>  
  
 <span data-ttu-id="d4aff-108">![BizTalk 定义事务](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")</span><span class="sxs-lookup"><span data-stu-id="d4aff-108">![BizTalk Defining Transaction](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")</span></span>  
  
 <span data-ttu-id="d4aff-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="d4aff-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="d4aff-110">**定义一个事务作为一个新的管理单元**</span><span class="sxs-lookup"><span data-stu-id="d4aff-110">**Defining a transaction as a new unit of management**</span></span>  
  
 <span data-ttu-id="d4aff-111">定义的事务之后, 用户还可以检测和跟踪消息与使用相同的工具提供可见性，单个服务的每个事务相关联。</span><span class="sxs-lookup"><span data-stu-id="d4aff-111">After defining transactions, users can instrument and track messages associated with each transaction using the same tools that provide visibility into a single service.</span></span> <span data-ttu-id="d4aff-112">这些工具可以公开性能指标、 监视服务级别协议，对性能和生成消息日志，如图 2 中所示。</span><span class="sxs-lookup"><span data-stu-id="d4aff-112">These tools can expose performance metrics, monitor performance against service level agreements, and generate message logs, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="d4aff-113">![BizTalk 监视](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")</span><span class="sxs-lookup"><span data-stu-id="d4aff-113">![BizTalk Monitoring](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")</span></span>  
  
 <span data-ttu-id="d4aff-114">**图 2**</span><span class="sxs-lookup"><span data-stu-id="d4aff-114">**Figure 2**</span></span>  
  
 <span data-ttu-id="d4aff-115">**监视管道的端到端性能**</span><span class="sxs-lookup"><span data-stu-id="d4aff-115">**Monitoring the end-to-end performance of a pipeline**</span></span>  
  
 <span data-ttu-id="d4aff-116">成功运行时管理和监视系统的一个主要要求是重要的业务事件，如异常和可能会中断业务事务流的逻辑处理的应用程序错误的检测。</span><span class="sxs-lookup"><span data-stu-id="d4aff-116">A major requirement for successful run-time governance and system monitoring is the detection of important business events, such as exceptions and application errors that may disrupt the logical processing of business transaction flows.</span></span> <span data-ttu-id="d4aff-117">AmberPoint SMS 允许操作员和用户，以获得深入了解操作和业务事件并监视这些事件对生成问题的服务所依赖的所有组件的影响。</span><span class="sxs-lookup"><span data-stu-id="d4aff-117">AmberPoint SMS allows operators and users to gain insight into operational and business events and to monitor the impact these events have on all components that depend on the service that generated the problem.</span></span> <span data-ttu-id="d4aff-118">此外，操作员和用户可以快速解决整个系统识别问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="d4aff-118">In addition, operators and users can quickly troubleshoot the entire system to identify the root-cause of a problem.</span></span>