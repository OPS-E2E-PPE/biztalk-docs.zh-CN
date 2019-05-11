---
title: 方案解决方案步骤 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77751c15-9b67-4587-8bc8-2be65f13d339
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd2f7623487670041ed2684fc096b669eaef1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394021"
---
# <a name="scenario-solution-steps"></a><span data-ttu-id="f0f22-102">方案解决方案步骤</span><span class="sxs-lookup"><span data-stu-id="f0f22-102">Scenario Solution Steps</span></span>
<span data-ttu-id="f0f22-103">ESB 异常管理框架提供用于处理异常时的发票消息包含无效数据的处理过程中，将导致错误，如本主题中前面所述的一个简单的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f0f22-103">The ESB Exception Management Framework provides a simple solution for handling an exception when an invoice message contains invalid data that causes an error during processing, as described earlier in this topic.</span></span> <span data-ttu-id="f0f22-104">下面是可能需要一种方法：</span><span class="sxs-lookup"><span data-stu-id="f0f22-104">The following is one approach you could take:</span></span>  
  
1.  <span data-ttu-id="f0f22-105">将最近部署财务报告的应用程序基于 Microsoft BizTalk 为你的团队的开发人员的责任分配。</span><span class="sxs-lookup"><span data-stu-id="f0f22-105">Assign responsibility for the recently deployed Financial Reporting application based on Microsoft BizTalk to a developer on your team.</span></span>  
  
2.  <span data-ttu-id="f0f22-106">新的 ESB 故障消息到达时在 ESB 管理门户中;该消息指示的财务报告 BizTalk 应用程序中的业务流程中的数据完整性问题。</span><span class="sxs-lookup"><span data-stu-id="f0f22-106">A new ESB fault message arrives in the ESB Management Portal; the message indicates a data integrity issue in an orchestration in the Financial Reporting BizTalk application.</span></span>  
  
3.  <span data-ttu-id="f0f22-107">发生异常时自动通知注册开发人员或管理员或操作员通知的新异常，开发人员。</span><span class="sxs-lookup"><span data-stu-id="f0f22-107">The administrator or operator notifies the developer of the new exception, or the developer registers for automatic notification when an exception occurs.</span></span> <span data-ttu-id="f0f22-108">此通知可能是由于以下原因之一：</span><span class="sxs-lookup"><span data-stu-id="f0f22-108">This notification may occur for one of the following reasons:</span></span>  
  
    -   <span data-ttu-id="f0f22-109">它可能会导致异常超出预定义在基于事件的业务活动监视 (BAM) 的阈值。</span><span class="sxs-lookup"><span data-stu-id="f0f22-109">It may occur because the exception exceeded a threshold predefined in event-based Business Activity Monitoring (BAM).</span></span>  
  
    -   <span data-ttu-id="f0f22-110">它可能会导致 BizTalk 订阅存在特定的应用程序、 服务、 范围和错误代码，它将异常转发给开发人员。</span><span class="sxs-lookup"><span data-stu-id="f0f22-110">It may occur because a BizTalk subscription exists for the specific application, service, scope, and fault code that forwards the exception to the developer.</span></span>  
  
4.  <span data-ttu-id="f0f22-111">开发人员检查错误消息、 单个业务流程消息和其持久化的上下文属性值。</span><span class="sxs-lookup"><span data-stu-id="f0f22-111">The developer examines the fault message, the individual orchestration messages, and their persisted context property values.</span></span> <span data-ttu-id="f0f22-112">开发人员可以查看此信息通过 ESB 管理门户或通过 BizTalk 订阅使用 Microsoft Outlook。</span><span class="sxs-lookup"><span data-stu-id="f0f22-112">Developers can view this information through the ESB Management Portal or by using Microsoft Outlook through a BizTalk subscription.</span></span>  
  
5.  <span data-ttu-id="f0f22-113">开发人员确定，这是一种常见错误。</span><span class="sxs-lookup"><span data-stu-id="f0f22-113">The developer determines that this is a common error.</span></span> <span data-ttu-id="f0f22-114">只有财务团队，然后重新提交到系统，它将需要手动干预和更正。</span><span class="sxs-lookup"><span data-stu-id="f0f22-114">It will require manual intervention and correction by the Finance team, followed by resubmission to the system.</span></span>  
  
6.  <span data-ttu-id="f0f22-115">开发人员创建和部署为独立的 BizTalk 业务流程项目的订阅的特定应用程序和异常类型。</span><span class="sxs-lookup"><span data-stu-id="f0f22-115">The developer creates and deploys an independent BizTalk orchestration project that subscribes to the specific application and exception type.</span></span>  
  
7.  <span data-ttu-id="f0f22-116">业务流程项目从 ESB 错误消息中检索无效的消息、 将消息发送到更正财务团队、 关联回业务流程中，更正后的消息并将其重新提交。</span><span class="sxs-lookup"><span data-stu-id="f0f22-116">The orchestration project retrieves the invalid message from the ESB fault message, sends the message to the Finance team for correction, correlates the corrected message back to the orchestration, and resubmits it.</span></span>  
  
8.  <span data-ttu-id="f0f22-117">一周后，开发人员将导航到 ESB 管理门户来发现由于此解决方案已部署，极大地降低无效消息的应用程序异常趋势。</span><span class="sxs-lookup"><span data-stu-id="f0f22-117">A week later, the developer navigates to the ESB Management Portal to discover that application exception trends for invalid messages have decreased dramatically since this solution was deployed.</span></span>