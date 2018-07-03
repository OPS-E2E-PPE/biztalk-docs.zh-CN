---
title: 使用 SWIFT 反汇编程序和汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, assembler
- developing, disassembler
- assembler, developing
- disassembler, developing
ms.assetid: cc88ed4c-baed-4efa-b54f-9fe079df9ba4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1942e6648311c65acc2bb1cd91406904906cc8f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005734"
---
# <a name="working-with-the-swift-disassembler-and-assembler"></a><span data-ttu-id="66d4b-102">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="66d4b-102">Working with the SWIFT Disassembler and Assembler</span></span>
<span data-ttu-id="66d4b-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供自定义管道组件、 SWIFT 反汇编程序和功能专门用于处理 SWIFT 平面文件消息的 SWIFT 汇编程序。</span><span class="sxs-lookup"><span data-stu-id="66d4b-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides custom pipeline components, the SWIFT disassembler, and SWIFT assembler that have features designed specifically for processing SWIFT flat-file messages.</span></span> <span data-ttu-id="66d4b-104">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送和接收管道使用 A4SWIFT 管道组件来执行特定任务，在定义阶段的入站 （接收） 和出站 （发送） 处理。</span><span class="sxs-lookup"><span data-stu-id="66d4b-104">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send and receive pipelines use the A4SWIFT pipeline components to perform specific tasks during defined stages of inbound (receive) and outbound (send) processing.</span></span> <span data-ttu-id="66d4b-105">有关消息处理、 管道和管道组件的更多详细信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="66d4b-105">For further details about message processing, pipelines, and pipeline components, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="66d4b-106">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="66d4b-106">This section contains:</span></span>  
  
-   [<span data-ttu-id="66d4b-107">SWIFT 反汇编程序和汇编程序功能</span><span class="sxs-lookup"><span data-stu-id="66d4b-107">SWIFT Disassembler and Assembler Functionality</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-and-assembler-functionality.md)  
  
-   [<span data-ttu-id="66d4b-108">将 SWIFT 反汇编程序或汇编程序添加到管道</span><span class="sxs-lookup"><span data-stu-id="66d4b-108">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-the-swift-disassembler-or-assembler-to-a-pipeline.md)  
  
-   [<span data-ttu-id="66d4b-109">配置 SWIFT 反汇编程序或汇编程序</span><span class="sxs-lookup"><span data-stu-id="66d4b-109">Configuring the SWIFT Disassembler or Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler-or-assembler.md)  
  
-   [<span data-ttu-id="66d4b-110">动态消息类型发现和架构解析</span><span class="sxs-lookup"><span data-stu-id="66d4b-110">Dynamic Message Type Discovery and Schema Resolution</span></span>](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)  
  
-   [<span data-ttu-id="66d4b-111">为动态消息类型发现创建自定义标头架构</span><span class="sxs-lookup"><span data-stu-id="66d4b-111">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-custom-header-schemas-for-dynamic-message-type-discovery.md)  
  
-   [<span data-ttu-id="66d4b-112">反汇编入站批处理</span><span class="sxs-lookup"><span data-stu-id="66d4b-112">Disassembling Inbound Batches</span></span>](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)