---
title: SWIFT 反汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25c389e10a48287ef87495b32fe2d69644a8259e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010918"
---
# <a name="swift-disassembler"></a><span data-ttu-id="8b581-102">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="8b581-102">SWIFT Disassembler</span></span>
<span data-ttu-id="8b581-103">入站的接收管道处理所有消息提交到[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（在接收位置收到） 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b581-103">An inbound receive pipeline processes all messages submitted to an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (received at a receive location).</span></span>  
  
 <span data-ttu-id="8b581-104">与 BizTalk 的入站的处理构成的逻辑执行阶段接收管道。</span><span class="sxs-lookup"><span data-stu-id="8b581-104">Logical execution stages related to inbound processing make up the BizTalk receive pipelines.</span></span> <span data-ttu-id="8b581-105">管道组件服务，或实现每个阶段。</span><span class="sxs-lookup"><span data-stu-id="8b581-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="8b581-106">具体而言，拆装器服务在接收管道的拆装阶段。</span><span class="sxs-lookup"><span data-stu-id="8b581-106">In particular, the disassembler services the disassemble stage in the receive pipeline.</span></span> <span data-ttu-id="8b581-107">A4SWIFT 提供特定于 SWIFT 的消息处理中的自定义拆装器组件的功能。</span><span class="sxs-lookup"><span data-stu-id="8b581-107">A4SWIFT provides SWIFT-specific message processing functionality in a custom disassembler component.</span></span>  
  
 <span data-ttu-id="8b581-108">SWIFT 反汇编程序，自定义的平面文件拆装器提供功能，用于处理入站 SWIFT 消息和批处理，并执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="8b581-108">The SWIFT disassembler, a custom flat file disassembler, provides functionality for processing inbound SWIFT messages and batches, and performs the following functions:</span></span>  
  
- <span data-ttu-id="8b581-109">动态发现消息类型和解析文档架构</span><span class="sxs-lookup"><span data-stu-id="8b581-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="8b581-110">将 SWIFT 平面文件分析为 XML</span><span class="sxs-lookup"><span data-stu-id="8b581-110">Parses SWIFT flat files into XML</span></span>  
  
- <span data-ttu-id="8b581-111">调用验证读取器执行 XML （架构） 验证 XML</span><span class="sxs-lookup"><span data-stu-id="8b581-111">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
- <span data-ttu-id="8b581-112">调用业务规则引擎 (BRE) 执行 BRE 验证</span><span class="sxs-lookup"><span data-stu-id="8b581-112">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
- <span data-ttu-id="8b581-113">将已分析的 XML 消息发布到 MessageBox 数据库使用已升级的上下文属性和序列化的错误集合 XML</span><span class="sxs-lookup"><span data-stu-id="8b581-113">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
- <span data-ttu-id="8b581-114">处理和反汇编入站的批处理</span><span class="sxs-lookup"><span data-stu-id="8b581-114">Processes and disassembles inbound batches</span></span>  
  
  <span data-ttu-id="8b581-115">下图显示了 SWIFT 反汇编程序数据流。</span><span class="sxs-lookup"><span data-stu-id="8b581-115">The following figure shows the SWIFT disassembler data flow.</span></span>  
  
  <span data-ttu-id="8b581-116">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")</span><span class="sxs-lookup"><span data-stu-id="8b581-116">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")</span></span>  
  
  <span data-ttu-id="8b581-117">SWIFT 反汇编程序有关的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。</span><span class="sxs-lookup"><span data-stu-id="8b581-117">For more information about the SWIFT disassembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b581-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b581-118">See Also</span></span>  
 [<span data-ttu-id="8b581-119">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="8b581-119">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)