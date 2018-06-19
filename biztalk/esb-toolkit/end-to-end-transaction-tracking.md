---
title: 端到端事务跟踪 |Microsoft 文档
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
ms.openlocfilehash: ffa49372c54dc526f45e04317e002604ac0914d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294109"
---
# <a name="end-to-end-transaction-tracking"></a><span data-ttu-id="40445-102">端到端事务跟踪</span><span class="sxs-lookup"><span data-stu-id="40445-102">End-to-End Transaction Tracking</span></span>
<span data-ttu-id="40445-103">对运算符和用户能够监视通过运行时环境的通信流相关业务可见性。</span><span class="sxs-lookup"><span data-stu-id="40445-103">Business visibility relates to the ability of operators and users to monitor the flow of traffic through the run-time environment.</span></span> <span data-ttu-id="40445-104">企业必须能够跟踪的进程和流经其系统在每个步骤，以确保它们播放导致收入生成其参与的事务。</span><span class="sxs-lookup"><span data-stu-id="40445-104">Enterprises must be able to track the processes and transactions flowing through their systems at each step to ensure that they play their part in contributing to revenue generation.</span></span> <span data-ttu-id="40445-105">AmberPoint SMS 简化了的度量和 Microsoft BizTalk Server 中的这些消息的跟踪。</span><span class="sxs-lookup"><span data-stu-id="40445-105">AmberPoint SMS simplifies the measurement and tracking of these messages in Microsoft BizTalk Server.</span></span> <span data-ttu-id="40445-106">系统允许用户定义新的管理单元，它们与端到端业务流程、 而不是所需以符合开发人员选择打包和部署单个服务组件的方式保持一致。</span><span class="sxs-lookup"><span data-stu-id="40445-106">The system allows users to define new units of management that align with end-to-end business process flows, instead of being required to conform to the way developers chose to package and deploy individual service components.</span></span> <span data-ttu-id="40445-107">图 1 显示了用于定义管理单位的屏幕。</span><span class="sxs-lookup"><span data-stu-id="40445-107">Figure 1 shows the screen for defining management units.</span></span>  
  
 <span data-ttu-id="40445-108">![定义事务的 BizTalk](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9 BizTalkDefiningTransaction")</span><span class="sxs-lookup"><span data-stu-id="40445-108">![BizTalk Defining Transaction](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")</span></span>  
  
 <span data-ttu-id="40445-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="40445-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="40445-110">**作为新的管理单元中定义事务**</span><span class="sxs-lookup"><span data-stu-id="40445-110">**Defining a transaction as a new unit of management**</span></span>  
  
 <span data-ttu-id="40445-111">后定义的事务，用户还可以检测和跟踪消息与使用相同的工具，提供到单个服务的可见性的每个事务相关联。</span><span class="sxs-lookup"><span data-stu-id="40445-111">After defining transactions, users can instrument and track messages associated with each transaction using the same tools that provide visibility into a single service.</span></span> <span data-ttu-id="40445-112">这些工具可以公开性能度量值、 监视服务级别协议针对性能和生成消息日志，如图 2 中所示。</span><span class="sxs-lookup"><span data-stu-id="40445-112">These tools can expose performance metrics, monitor performance against service level agreements, and generate message logs, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="40445-113">![BizTalk 监视](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9 BizTalkMonitoring")</span><span class="sxs-lookup"><span data-stu-id="40445-113">![BizTalk Monitoring](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")</span></span>  
  
 <span data-ttu-id="40445-114">**图 2**</span><span class="sxs-lookup"><span data-stu-id="40445-114">**Figure 2**</span></span>  
  
 <span data-ttu-id="40445-115">**监视的管道的端到端性能**</span><span class="sxs-lookup"><span data-stu-id="40445-115">**Monitoring the end-to-end performance of a pipeline**</span></span>  
  
 <span data-ttu-id="40445-116">成功的运行时管理和监视系统的主要要求是重要的业务事件，包括异常及可能会中断业务事务流的逻辑处理的应用程序错误的检测工具。</span><span class="sxs-lookup"><span data-stu-id="40445-116">A major requirement for successful run-time governance and system monitoring is the detection of important business events, such as exceptions and application errors that may disrupt the logical processing of business transaction flows.</span></span> <span data-ttu-id="40445-117">AmberPoint SMS 允许操作员和用户，以获得深入了解操作和业务事件，并监视这些事件对依赖于生成问题的服务的所有组件产生的影响。</span><span class="sxs-lookup"><span data-stu-id="40445-117">AmberPoint SMS allows operators and users to gain insight into operational and business events and to monitor the impact these events have on all components that depend on the service that generated the problem.</span></span> <span data-ttu-id="40445-118">此外，则操作员和用户可以快速诊断整个系统以确定问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="40445-118">In addition, operators and users can quickly troubleshoot the entire system to identify the root-cause of a problem.</span></span>