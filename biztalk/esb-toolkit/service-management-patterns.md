---
title: 服务管理模式 |Microsoft 文档
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
ms.openlocfilehash: a48639fb2a540b5b2597b34ad95ee390b4382c34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294621"
---
# <a name="service-management-patterns"></a><span data-ttu-id="09ab6-102">服务管理模式</span><span class="sxs-lookup"><span data-stu-id="09ab6-102">Service Management Patterns</span></span>
## <a name="repair-and-resubmit"></a><span data-ttu-id="09ab6-103">修复并重新提交</span><span class="sxs-lookup"><span data-stu-id="09ab6-103">Repair and Resubmit</span></span>  
 <span data-ttu-id="09ab6-104">修复并重新提交模式定义一个解决方案，在其中一项服务无法处理消息，并需要正常外部化形式的失败的消息其状态，从而使消息内容才可用于修复，然后将其重新提交到服务若要继续处理消息。</span><span class="sxs-lookup"><span data-stu-id="09ab6-104">The Repair and Resubmit pattern defines a solution in which a service is unable to process a message and needs to gracefully externalize its state in the form of the failed message, enabling the message content to be available for repair and then resubmit it to a service to continue processing the message.</span></span>  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="09ab6-105">包括由哪些 Microsoft BizTalk 消息传送和业务流程的异常可以为规范化，并公开其他操作的机制。</span><span class="sxs-lookup"><span data-stu-id="09ab6-105"> includes mechanisms by which Microsoft BizTalk messaging and orchestration exceptions can be normalized and exposed for additional action.</span></span> <span data-ttu-id="09ab6-106">设计 ESB 解决方案时，务必将如何处理异常的帐户。</span><span class="sxs-lookup"><span data-stu-id="09ab6-106">When designing an ESB solution, it is important to account for how exceptions will be handled.</span></span> <span data-ttu-id="09ab6-107">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括的示例 ESB 管理门户应用程序演示了如何查看和管理异常。</span><span class="sxs-lookup"><span data-stu-id="09ab6-107">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a sample ESB Management Portal application that demonstrates how exceptions can be viewed and managed.</span></span> <span data-ttu-id="09ab6-108">有关修复和重新提交使用 ESB 管理门户示例应用程序的异常的详细信息，请参阅[修复和重新提交消息](../esb-toolkit/repairing-and-resubmitting-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="09ab6-108">For detailed information about repairing and resubmitting exceptions using the ESB Management Portal sample application, see [Repairing and Resubmitting Messages](../esb-toolkit/repairing-and-resubmitting-messages.md).</span></span>