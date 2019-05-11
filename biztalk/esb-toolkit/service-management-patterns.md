---
title: 服务管理模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fea915c-0074-472e-909b-fbbd88d7359c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ec777e46dada4a47f00cff666b6924e448ef8b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392034"
---
# <a name="service-management-patterns"></a><span data-ttu-id="f8b29-102">服务管理模式</span><span class="sxs-lookup"><span data-stu-id="f8b29-102">Service Management Patterns</span></span>
## <a name="repair-and-resubmit"></a><span data-ttu-id="f8b29-103">修复和重新提交</span><span class="sxs-lookup"><span data-stu-id="f8b29-103">Repair and Resubmit</span></span>  
 <span data-ttu-id="f8b29-104">修复和重新提交模式定义在其中一项服务无法处理消息并且需要正常外部化其在失败消息的窗体中状态，从而使消息内容为可用于修复，然后将其重新提交到服务的解决方案若要继续处理消息。</span><span class="sxs-lookup"><span data-stu-id="f8b29-104">The Repair and Resubmit pattern defines a solution in which a service is unable to process a message and needs to gracefully externalize its state in the form of the failed message, enabling the message content to be available for repair and then resubmit it to a service to continue processing the message.</span></span>  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] <span data-ttu-id="f8b29-105">包括以下哪些 Microsoft biztalk 消息传送和业务流程的异常可以规范化和公开其他操作的机制。</span><span class="sxs-lookup"><span data-stu-id="f8b29-105">includes mechanisms by which Microsoft BizTalk messaging and orchestration exceptions can be normalized and exposed for additional action.</span></span> <span data-ttu-id="f8b29-106">设计 ESB 解决方案时，时，重要的帐户将如何处理异常。</span><span class="sxs-lookup"><span data-stu-id="f8b29-106">When designing an ESB solution, it is important to account for how exceptions will be handled.</span></span> <span data-ttu-id="f8b29-107">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括 ESB 管理门户应用程序示例演示如何查看和管理异常。</span><span class="sxs-lookup"><span data-stu-id="f8b29-107">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a sample ESB Management Portal application that demonstrates how exceptions can be viewed and managed.</span></span> <span data-ttu-id="f8b29-108">有关修复和重新提交使用 ESB 管理门户示例应用程序的异常的详细信息，请参阅[正在修复和重新提交消息](../esb-toolkit/repairing-and-resubmitting-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f8b29-108">For detailed information about repairing and resubmitting exceptions using the ESB Management Portal sample application, see [Repairing and Resubmitting Messages](../esb-toolkit/repairing-and-resubmitting-messages.md).</span></span>