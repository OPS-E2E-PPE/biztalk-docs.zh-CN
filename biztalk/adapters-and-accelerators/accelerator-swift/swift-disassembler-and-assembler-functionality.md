---
title: "SWIFT 反汇编程序和汇编程序功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0109979fbb9bf61fc0e1be833061b2a15b470690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-and-assembler-functionality"></a><span data-ttu-id="888a2-102">SWIFT 反汇编程序和汇编程序功能</span><span class="sxs-lookup"><span data-stu-id="888a2-102">SWIFT Disassembler and Assembler Functionality</span></span>
<span data-ttu-id="888a2-103">SWIFT 反汇编程序可以执行以下任务中调用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：</span><span class="sxs-lookup"><span data-stu-id="888a2-103">The SWIFT disassembler can perform the following tasks when invoked in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
-   <span data-ttu-id="888a2-104">动态发现消息类型和解决文档架构。</span><span class="sxs-lookup"><span data-stu-id="888a2-104">Dynamically discover the message type and resolve document schema.</span></span> <span data-ttu-id="888a2-105">这使单个接收端口和管道来处理多个 SWIFT 消息类型。</span><span class="sxs-lookup"><span data-stu-id="888a2-105">This enables a single receive port and pipeline to handle multiple SWIFT message types.</span></span>  
  
-   <span data-ttu-id="888a2-106">为 XML 分析 SWIFT 平面文件。</span><span class="sxs-lookup"><span data-stu-id="888a2-106">Parse a SWIFT flat file into XML.</span></span>  
  
-   <span data-ttu-id="888a2-107">调用验证读取器以执行 XML （架构） 验证，例如数据类型有效性、 数据格式或长度一致性检查的 XML。</span><span class="sxs-lookup"><span data-stu-id="888a2-107">Invoke the XML validating reader to perform XML (schema) validation, such as checking data type validity, data format, or length conformance.</span></span>  
  
-   <span data-ttu-id="888a2-108">调用以执行 BRE 验证，例如检查符合 SWIFT 网络规则或执行其他复杂的验证架构不实现业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="888a2-108">Invoke the Business Rule Engine (BRE) to perform BRE validation, such as checking conformance to SWIFT network rules or performing other complex validation that the schema does not implement.</span></span>  
  
-   <span data-ttu-id="888a2-109">将已分析的 XML 消息发布到 MessageBox 数据库使用提升的上下文属性和序列化的错误集合 XML （提供有关在分析或验证过程中遇到任何错误的信息）。</span><span class="sxs-lookup"><span data-stu-id="888a2-109">Publish a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML (providing information about any errors encountered during parsing or validation).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="888a2-110">如果反汇编程序在分析过程中遇到严重故障，拆装器将将消息发布到 MessageBox 数据库在本机平面文件格式，而不是 XML。</span><span class="sxs-lookup"><span data-stu-id="888a2-110">If the disassembler encounters fatal failures during parsing, the disassembler will publish the message to the MessageBox database in native flat file format rather than XML.</span></span>  
  
-   <span data-ttu-id="888a2-111">处理入站的批处理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="888a2-111">Process inbound batches, as follows:</span></span>  
  
    -   <span data-ttu-id="888a2-112">分析并保留批处理信封 （批处理标头，批处理尾）</span><span class="sxs-lookup"><span data-stu-id="888a2-112">Parse and preserve batch envelopes (batch header, batch trailer)</span></span>  
  
    -   <span data-ttu-id="888a2-113">分析并保留消息信封 （消息标头、 消息尾部）</span><span class="sxs-lookup"><span data-stu-id="888a2-113">Parse and preserve message envelopes (message header, message trailer)</span></span>  
  
    -   <span data-ttu-id="888a2-114">分析和单独验证 SWIFT 批处理中的消息</span><span class="sxs-lookup"><span data-stu-id="888a2-114">Parse and validate SWIFT messages in the batch individually</span></span>  
  
    -   <span data-ttu-id="888a2-115">单独将 SWIFT 消息发布到 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="888a2-115">Publish SWIFT messages to the MessageBox database individually</span></span>  
  
    -   <span data-ttu-id="888a2-116">将整个的入站的批处理发布到 MessageBox 数据库中，为一条消息 （输入的准确副本）</span><span class="sxs-lookup"><span data-stu-id="888a2-116">Publish the entire inbound batch to the MessageBox database as a single message (exact copy of input)</span></span>  
  
    -   <span data-ttu-id="888a2-117">提升排序或关联从同一个批处理发出的消息的批处理相关的上下文属性</span><span class="sxs-lookup"><span data-stu-id="888a2-117">Promote batch-related context properties for sorting or correlating messages originating from the same batch</span></span>  
  
 <span data-ttu-id="888a2-118">SWIFT 汇编程序可以执行以下任务时 BizTalk 发送管道中进行调用：</span><span class="sxs-lookup"><span data-stu-id="888a2-118">The SWIFT assembler can perform the following tasks when invoked in a BizTalk send pipeline:</span></span>  
  
-   <span data-ttu-id="888a2-119">动态发现消息类型和解决的文档架构。</span><span class="sxs-lookup"><span data-stu-id="888a2-119">Dynamically discover the message type and resolve the document schema.</span></span> <span data-ttu-id="888a2-120">这样，一个发送端口和管道来处理多个 SWIFT 消息类型。</span><span class="sxs-lookup"><span data-stu-id="888a2-120">This allows a single send port and pipeline to handle multiple SWIFT message types.</span></span>  
  
-   <span data-ttu-id="888a2-121">已分析的 XML 序列化为 SWIFT 平面文件。</span><span class="sxs-lookup"><span data-stu-id="888a2-121">Serialize parsed XML into a SWIFT flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888a2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="888a2-122">See Also</span></span>  
 [<span data-ttu-id="888a2-123">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="888a2-123">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)