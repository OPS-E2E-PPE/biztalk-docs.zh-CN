---
title: ESB 调度程序反汇编组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1f5e46b-8f41-47f8-b22b-b9e9eaac6475
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea0aadf4207d8486e7a7d55c878f7de99efb831
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399833"
---
# <a name="the-esb-dispatcher-disassemble-component"></a><span data-ttu-id="660a6-102">ESB 调度程序反汇编组件</span><span class="sxs-lookup"><span data-stu-id="660a6-102">The ESB Dispatcher Disassemble Component</span></span>
<span data-ttu-id="660a6-103">ESB 调度程序反汇编组件可以在类似于调度程序组件中动态设置终结点的出站消息的位置属性。</span><span class="sxs-lookup"><span data-stu-id="660a6-103">The ESB Dispatcher Disassemble component can dynamically set endpoint location properties for outbound messages in a similar way to the Dispatcher component.</span></span> <span data-ttu-id="660a6-104">此管道组件同时取消批处理功能的 Microsoft BizTalk 消息 (从 XML 拆装器类继承的名为**XmlDasmComp**) 与消息调度机制，可以执行 ESB 路线BizTalk 管道中的消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="660a6-104">This pipeline component combines Microsoft BizTalk message de-batching functionality (by inheriting from the XML disassembler class named **XmlDasmComp**) with the message dispatching mechanism that can execute ESB itinerary messaging services in a BizTalk pipeline.</span></span>