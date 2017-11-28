---
title: "在 HL7 2.X 汇编程序架构确定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50a430750846ae2567f063f9aa77221bad9c97e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a><span data-ttu-id="0bf07-102">架构确定在 HL7 2.X 汇编程序</span><span class="sxs-lookup"><span data-stu-id="0bf07-102">Schema Determination in the HL7 2.X Assembler</span></span>
<span data-ttu-id="0bf07-103">当一条消息都流向序列化程序，在序列化程序[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 MSH5 （目标方） 以确定要在消息上执行的操作的消息。</span><span class="sxs-lookup"><span data-stu-id="0bf07-103">When a message flows to the serializer, the serializer in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses MSH5 (destination party) of the message to determine the operations to be performed on the message.</span></span> <span data-ttu-id="0bf07-104">此类操作包括：</span><span class="sxs-lookup"><span data-stu-id="0bf07-104">Such operations include:</span></span>  
  
-   <span data-ttu-id="0bf07-105">是否为正文段执行 XML 验证</span><span class="sxs-lookup"><span data-stu-id="0bf07-105">Whether to perform XML validation for body segments</span></span>  
  
-   <span data-ttu-id="0bf07-106">是否要验证正文段的自定义数据类型</span><span class="sxs-lookup"><span data-stu-id="0bf07-106">Whether to validate custom data types for body segments</span></span>  
  
-   <span data-ttu-id="0bf07-107">是否允许尾随分隔符在正文中</span><span class="sxs-lookup"><span data-stu-id="0bf07-107">Whether to allow trailing delimiters in the body</span></span>  
  
-   <span data-ttu-id="0bf07-108">序列化程序将使用的架构目标命名空间</span><span class="sxs-lookup"><span data-stu-id="0bf07-108">Which schema target namespace the serializer will use</span></span>  
  
-   <span data-ttu-id="0bf07-109">序列化程序是否需要来映射的标题</span><span class="sxs-lookup"><span data-stu-id="0bf07-109">Whether the serializer needs to map the header</span></span>  
  
 <span data-ttu-id="0bf07-110">若要确定架构，序列化程序将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bf07-110">To determine the schema, the serializer does the following:</span></span>  
  
-   <span data-ttu-id="0bf07-111">设置的目标命名空间 (**TargetNS**) 为目标方配置的命名空间相同的值</span><span class="sxs-lookup"><span data-stu-id="0bf07-111">Sets the target namespace (**TargetNS**) to the same value as the namespace configured for the destination party</span></span>  
  
-   <span data-ttu-id="0bf07-112">提取**Rootnode**从**BTS。MessageType**提升属性</span><span class="sxs-lookup"><span data-stu-id="0bf07-112">Extracts **Rootnode** from the **BTS.MessageType** promoted property</span></span>  
  
 <span data-ttu-id="0bf07-113">**Doctype**变得**TargetNS +"#"+ Rootnode**。</span><span class="sxs-lookup"><span data-stu-id="0bf07-113">The **doctype** becomes **TargetNS + "#" + Rootnode**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf07-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf07-114">See Also</span></span>  
 <span data-ttu-id="0bf07-115">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="0bf07-115">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="0bf07-116">BTAHL72X 平面文件处理</span><span class="sxs-lookup"><span data-stu-id="0bf07-116">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)