---
title: "ESB 调度程序反汇编组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1f5e46b-8f41-47f8-b22b-b9e9eaac6475
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846ca716aef72d43e4f4a6ed75a2b20a81c351a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-dispatcher-disassemble-component"></a><span data-ttu-id="32df3-102">ESB 调度程序反汇编组件</span><span class="sxs-lookup"><span data-stu-id="32df3-102">The ESB Dispatcher Disassemble Component</span></span>
<span data-ttu-id="32df3-103">ESB 调度程序反汇编组件可以动态设置到调度程序组件的方式类似的出站消息的终结点位置属性。</span><span class="sxs-lookup"><span data-stu-id="32df3-103">The ESB Dispatcher Disassemble component can dynamically set endpoint location properties for outbound messages in a similar way to the Dispatcher component.</span></span> <span data-ttu-id="32df3-104">此管道组件将组合取消批处理功能的 Microsoft BizTalk 消息 (通过继承 XML 反汇编程序类名为**XmlDasmComp**) 与消息调度机制，可以执行 ESB 路线在 BizTalk 管道中的消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="32df3-104">This pipeline component combines Microsoft BizTalk message de-batching functionality (by inheriting from the XML disassembler class named **XmlDasmComp**) with the message dispatching mechanism that can execute ESB itinerary messaging services in a BizTalk pipeline.</span></span>