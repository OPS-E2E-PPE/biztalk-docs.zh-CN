---
title: "SWIFT 反汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0024abe862f777e7ee798991d97845ec5098a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler"></a><span data-ttu-id="8f9c9-102">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="8f9c9-102">SWIFT Disassembler</span></span>
<span data-ttu-id="8f9c9-103">入站的接收管道处理所有消息提交到[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（在接收位置接收） 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-103">An inbound receive pipeline processes all messages submitted to an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (received at a receive location).</span></span>  
  
 <span data-ttu-id="8f9c9-104">与 BizTalk 的入站的处理构成的逻辑执行阶段接收管道。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-104">Logical execution stages related to inbound processing make up the BizTalk receive pipelines.</span></span> <span data-ttu-id="8f9c9-105">管道组件服务或实现的每个阶段。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="8f9c9-106">具体而言，拆装器服务中接收管道的拆装阶段。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-106">In particular, the disassembler services the disassemble stage in the receive pipeline.</span></span> <span data-ttu-id="8f9c9-107">A4SWIFT 提供 SWIFT 特定消息处理自定义反汇编程序组件中的功能。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-107">A4SWIFT provides SWIFT-specific message processing functionality in a custom disassembler component.</span></span>  
  
 <span data-ttu-id="8f9c9-108">SWIFT 拆装器，自定义的平面文件拆装器，用于处理 SWIFT 的入站的消息和批处理，提供功能，并执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="8f9c9-108">The SWIFT disassembler, a custom flat file disassembler, provides functionality for processing inbound SWIFT messages and batches, and performs the following functions:</span></span>  
  
-   <span data-ttu-id="8f9c9-109">动态发现消息类型，并解析文档架构</span><span class="sxs-lookup"><span data-stu-id="8f9c9-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="8f9c9-110">为 XML 分析 SWIFT 平面文件</span><span class="sxs-lookup"><span data-stu-id="8f9c9-110">Parses SWIFT flat files into XML</span></span>  
  
-   <span data-ttu-id="8f9c9-111">调用验证读取器执行 XML （架构） 验证的 XML</span><span class="sxs-lookup"><span data-stu-id="8f9c9-111">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
-   <span data-ttu-id="8f9c9-112">调用以执行 BRE 验证业务规则引擎 (BRE)</span><span class="sxs-lookup"><span data-stu-id="8f9c9-112">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
-   <span data-ttu-id="8f9c9-113">将已分析的 XML 消息发布到 MessageBox 数据库使用提升的上下文属性和序列化的错误集合 XML</span><span class="sxs-lookup"><span data-stu-id="8f9c9-113">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
-   <span data-ttu-id="8f9c9-114">处理并进行反汇编，入站的批处理</span><span class="sxs-lookup"><span data-stu-id="8f9c9-114">Processes and disassembles inbound batches</span></span>  
  
 <span data-ttu-id="8f9c9-115">下图显示了 SWIFT 反汇编程序数据流。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-115">The following figure shows the SWIFT disassembler data flow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
 <span data-ttu-id="8f9c9-116">SWIFT 反汇编程序有关的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。</span><span class="sxs-lookup"><span data-stu-id="8f9c9-116">For more information about the SWIFT disassembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9c9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f9c9-117">See Also</span></span>  
 [<span data-ttu-id="8f9c9-118">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="8f9c9-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)