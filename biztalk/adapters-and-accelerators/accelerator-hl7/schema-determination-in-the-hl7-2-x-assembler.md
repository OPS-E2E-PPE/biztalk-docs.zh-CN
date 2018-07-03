---
title: HL7 2.X 汇编程序的架构确定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 962f9576032ec8b42542111502c2b6d6698f98d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983646"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a><span data-ttu-id="a8633-102">HL7 2.X 汇编程序的架构确定</span><span class="sxs-lookup"><span data-stu-id="a8633-102">Schema Determination in the HL7 2.X Assembler</span></span>
<span data-ttu-id="a8633-103">一条消息到序列化程序的流时，Microsoft BizTalk Accelerator for HL7 中的序列化程序 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 MSH5 （目标参与方） 的消息，以确定要对消息执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a8633-103">When a message flows to the serializer, the serializer in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses MSH5 (destination party) of the message to determine the operations to be performed on the message.</span></span> <span data-ttu-id="a8633-104">此类操作包括：</span><span class="sxs-lookup"><span data-stu-id="a8633-104">Such operations include:</span></span>  
  
- <span data-ttu-id="a8633-105">是否为正文段执行 XML 验证</span><span class="sxs-lookup"><span data-stu-id="a8633-105">Whether to perform XML validation for body segments</span></span>  
  
- <span data-ttu-id="a8633-106">是否要验证主体段的自定义数据类型</span><span class="sxs-lookup"><span data-stu-id="a8633-106">Whether to validate custom data types for body segments</span></span>  
  
- <span data-ttu-id="a8633-107">是否允许尾部分隔符在正文中</span><span class="sxs-lookup"><span data-stu-id="a8633-107">Whether to allow trailing delimiters in the body</span></span>  
  
- <span data-ttu-id="a8633-108">序列化程序将使用哪些架构目标命名空间</span><span class="sxs-lookup"><span data-stu-id="a8633-108">Which schema target namespace the serializer will use</span></span>  
  
- <span data-ttu-id="a8633-109">序列化程序是否需要映射的标题</span><span class="sxs-lookup"><span data-stu-id="a8633-109">Whether the serializer needs to map the header</span></span>  
  
  <span data-ttu-id="a8633-110">若要确定架构，序列化程序将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8633-110">To determine the schema, the serializer does the following:</span></span>  
  
- <span data-ttu-id="a8633-111">设置目标命名空间 (**TargetNS**) 到相同的值为目标参与方配置的命名空间</span><span class="sxs-lookup"><span data-stu-id="a8633-111">Sets the target namespace (**TargetNS**) to the same value as the namespace configured for the destination party</span></span>  
  
- <span data-ttu-id="a8633-112">提取**Rootnode**从**BTS。MessageType**升级的属性</span><span class="sxs-lookup"><span data-stu-id="a8633-112">Extracts **Rootnode** from the **BTS.MessageType** promoted property</span></span>  
  
  <span data-ttu-id="a8633-113">**Doctype**变得**TargetNS +"#"+ Rootnode**。</span><span class="sxs-lookup"><span data-stu-id="a8633-113">The **doctype** becomes **TargetNS + "#" + Rootnode**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8633-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8633-114">See Also</span></span>  
 <span data-ttu-id="a8633-115">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="a8633-115">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="a8633-116">BTAHL72X 平面文件处理</span><span class="sxs-lookup"><span data-stu-id="a8633-116">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)