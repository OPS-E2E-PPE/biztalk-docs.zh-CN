---
title: BizTalk Framework 反汇编程序管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ab54ddb9ef0b5fa389e6716fc4426978dcbd7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230581"
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="f0c3b-102">BizTalk Framework 反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="f0c3b-102">BizTalk Framework Disassembler Pipeline Component</span></span>
<span data-ttu-id="f0c3b-103">BizTalk 框架拆装器管道组件可以解析 XML 数据并确定其是否包含基于 BizTalk 框架的消息传送负载。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-103">The BizTalk Framework Disassembler pipeline component parses XML data and determines whether it contains a BizTalk Framework-based messaging payload.</span></span> <span data-ttu-id="f0c3b-104">该管道组件将保存消息上下文，并使用 BizTalk 框架属性创建需要生成的新的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-104">The pipeline component saves the message context, and a new message context is created with the BizTalk Framework property that needs to be generated.</span></span> <span data-ttu-id="f0c3b-105">此属性用于将消息路由到 BizTalk 框架入站处理程序，因此它可以接收要处理的消息。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-105">This property is used to route the message to the BizTalk Framework inbound handler, so it can receive the message to process.</span></span>  
  
 <span data-ttu-id="f0c3b-106">如果发送方在 BizTalk 框架信封中使用 deliverReceiptRequest 头部来请求确认，则 BizTalk 框架拆装器管道组件将为所生成的消息生成确认。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-106">The BizTalk Framework Disassembler pipeline component generates an acknowledgment for the generated message if the sender requested one using the deliverReceiptRequest header within the BizTalk Framework envelope.</span></span> <span data-ttu-id="f0c3b-107">这由 BizTalk 框架拆装器管道组件中的生成送达回执属性控制。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-107">This is controlled by the generate delivery receipt property in the BizTalk Framework Assembler pipeline component.</span></span> <span data-ttu-id="f0c3b-108">有关 BizTalk Framework 的详细信息，请参阅[BizTalk Framework 汇编程序管道组件](../core/biztalk-framework-assembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-108">For more information about the BizTalk Framework, see [BizTalk Framework Assembler Pipeline Component](../core/biztalk-framework-assembler-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="f0c3b-109">有关配置 BizTalk Framework 反汇编程序管道组件以及创建业务流程的信息，请参阅[如何配置 BizTalk Framework 反汇编程序管道组件](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c3b-109">For information about configuring the BizTalk Framework Disassembler pipeline component and creating the orchestration, see [How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c3b-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0c3b-110">See Also</span></span>  
 <span data-ttu-id="f0c3b-111">[如何将 BizTalk Framework 反汇编程序管道组件配置](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f0c3b-111">[How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="f0c3b-112">管道组件</span><span class="sxs-lookup"><span data-stu-id="f0c3b-112">Pipeline Components</span></span>](../core/pipeline-components.md)