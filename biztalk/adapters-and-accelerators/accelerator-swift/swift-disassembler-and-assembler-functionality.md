---
title: SWIFT 反汇编程序和汇编程序功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc3fa8b96b03d4bd3376f090e5e4436e70da945a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529813"
---
# <a name="swift-disassembler-and-assembler-functionality"></a><span data-ttu-id="fa395-102">SWIFT 反汇编程序和汇编程序功能</span><span class="sxs-lookup"><span data-stu-id="fa395-102">SWIFT Disassembler and Assembler Functionality</span></span>
<span data-ttu-id="fa395-103">SWIFT 反汇编程序可以执行以下任务中调用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：</span><span class="sxs-lookup"><span data-stu-id="fa395-103">The SWIFT disassembler can perform the following tasks when invoked in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
- <span data-ttu-id="fa395-104">动态地发现消息类型和解决文档架构。</span><span class="sxs-lookup"><span data-stu-id="fa395-104">Dynamically discover the message type and resolve document schema.</span></span> <span data-ttu-id="fa395-105">这样的单个接收端口和管道来处理多个 SWIFT 消息类型。</span><span class="sxs-lookup"><span data-stu-id="fa395-105">This enables a single receive port and pipeline to handle multiple SWIFT message types.</span></span>  
  
- <span data-ttu-id="fa395-106">解析为 XML SWIFT 的平面文件。</span><span class="sxs-lookup"><span data-stu-id="fa395-106">Parse a SWIFT flat file into XML.</span></span>  
  
- <span data-ttu-id="fa395-107">调用验证读取器以执行 XML （架构） 验证，例如数据类型有效性、 数据格式或长度一致性检查的 XML。</span><span class="sxs-lookup"><span data-stu-id="fa395-107">Invoke the XML validating reader to perform XML (schema) validation, such as checking data type validity, data format, or length conformance.</span></span>  
  
- <span data-ttu-id="fa395-108">调用业务规则引擎 (BRE)，以执行 BRE 验证，例如检查符合性的 SWIFT 网络规则或执行其他复杂的验证未实现架构。</span><span class="sxs-lookup"><span data-stu-id="fa395-108">Invoke the Business Rule Engine (BRE) to perform BRE validation, such as checking conformance to SWIFT network rules or performing other complex validation that the schema does not implement.</span></span>  
  
- <span data-ttu-id="fa395-109">将已分析的 XML 消息发布到 MessageBox 数据库使用已升级的上下文属性和序列化的错误集合 XML （提供有关在分析或验证过程中遇到任何错误的信息）。</span><span class="sxs-lookup"><span data-stu-id="fa395-109">Publish a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML (providing information about any errors encountered during parsing or validation).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fa395-110">如果拆装器在分析过程中遇到致命故障，拆装器会将消息发布到 MessageBox 数据库中本机平面文件格式而不是 XML。</span><span class="sxs-lookup"><span data-stu-id="fa395-110">If the disassembler encounters fatal failures during parsing, the disassembler will publish the message to the MessageBox database in native flat file format rather than XML.</span></span>  
  
- <span data-ttu-id="fa395-111">按如下所示处理入站的批处理：</span><span class="sxs-lookup"><span data-stu-id="fa395-111">Process inbound batches, as follows:</span></span>  
  
  -   <span data-ttu-id="fa395-112">分析和保留批的信封 （批处理标头，批处理尾部）</span><span class="sxs-lookup"><span data-stu-id="fa395-112">Parse and preserve batch envelopes (batch header, batch trailer)</span></span>  
  
  -   <span data-ttu-id="fa395-113">分析并保留消息信封 （消息标头，消息尾部）</span><span class="sxs-lookup"><span data-stu-id="fa395-113">Parse and preserve message envelopes (message header, message trailer)</span></span>  
  
  -   <span data-ttu-id="fa395-114">分析和单独验证批中的 SWIFT 消息</span><span class="sxs-lookup"><span data-stu-id="fa395-114">Parse and validate SWIFT messages in the batch individually</span></span>  
  
  -   <span data-ttu-id="fa395-115">将 SWIFT 消息单独发布到 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="fa395-115">Publish SWIFT messages to the MessageBox database individually</span></span>  
  
  -   <span data-ttu-id="fa395-116">将整个入站的批处理发布到 MessageBox 数据库，作为单个消息 （输入的精确副本）</span><span class="sxs-lookup"><span data-stu-id="fa395-116">Publish the entire inbound batch to the MessageBox database as a single message (exact copy of input)</span></span>  
  
  -   <span data-ttu-id="fa395-117">升级对排序或关联来自同一个批处理的消息批处理相关的上下文属性</span><span class="sxs-lookup"><span data-stu-id="fa395-117">Promote batch-related context properties for sorting or correlating messages originating from the same batch</span></span>  
  
  <span data-ttu-id="fa395-118">SWIFT 汇编程序可以执行以下任务时在 BizTalk 发送管道中调用：</span><span class="sxs-lookup"><span data-stu-id="fa395-118">The SWIFT assembler can perform the following tasks when invoked in a BizTalk send pipeline:</span></span>  
  
- <span data-ttu-id="fa395-119">动态地发现消息类型和解决文档架构。</span><span class="sxs-lookup"><span data-stu-id="fa395-119">Dynamically discover the message type and resolve the document schema.</span></span> <span data-ttu-id="fa395-120">这允许单个发送端口和管道来处理多个 SWIFT 消息类型。</span><span class="sxs-lookup"><span data-stu-id="fa395-120">This allows a single send port and pipeline to handle multiple SWIFT message types.</span></span>  
  
- <span data-ttu-id="fa395-121">已分析的 XML 序列化为 SWIFT 的平面文件。</span><span class="sxs-lookup"><span data-stu-id="fa395-121">Serialize parsed XML into a SWIFT flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa395-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa395-122">See Also</span></span>  
 [<span data-ttu-id="fa395-123">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="fa395-123">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)