---
title: "编程 Guide1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, programming guide
- programming guide
ms.assetid: fb2d5e3b-1907-49c4-806d-a2604c702322
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 230ecf4cf9b735bdc2d4e68fc233799e95bb3182
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="programming-guide"></a><span data-ttu-id="e29d7-102">编程指南</span><span class="sxs-lookup"><span data-stu-id="e29d7-102">Programming Guide</span></span>
<span data-ttu-id="e29d7-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]编程指南为编写代码与 BTAHL7 的开发人员说明了概念和过程。</span><span class="sxs-lookup"><span data-stu-id="e29d7-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Programming Guide explains concepts and procedures for developers writing code with BTAHL7.</span></span> <span data-ttu-id="e29d7-104">将本指南中结合使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="e29d7-104">Use this guide in conjunction with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e29d7-105">阅读此指南之前，你应该熟悉[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]开发，BizTalk Server 中，和[了解 HL7 快捷键和提供的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。</span><span class="sxs-lookup"><span data-stu-id="e29d7-105">Before reading this guide, you should be familiar with [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] development, BizTalk Server, and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e29d7-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e29d7-106">In This Section</span></span>  
  
-   [<span data-ttu-id="e29d7-107">处理 HL7 消息</span><span class="sxs-lookup"><span data-stu-id="e29d7-107">Processing HL7 Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)  
  
-   [<span data-ttu-id="e29d7-108">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="e29d7-108">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)  
  
-   [<span data-ttu-id="e29d7-109">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="e29d7-109">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)  
  
-   [<span data-ttu-id="e29d7-110">处理用 MLLP 编码的消息</span><span class="sxs-lookup"><span data-stu-id="e29d7-110">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)  
  
-   [<span data-ttu-id="e29d7-111">创建和处理确认</span><span class="sxs-lookup"><span data-stu-id="e29d7-111">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)  
  
-   [<span data-ttu-id="e29d7-112">使用动态数据验证</span><span class="sxs-lookup"><span data-stu-id="e29d7-112">Using Dynamic Data Validation</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-dynamic-data-validation.md)  
  
-   [<span data-ttu-id="e29d7-113">为审核与记录事件创建 WMI 接收器</span><span class="sxs-lookup"><span data-stu-id="e29d7-113">Creating a WMI Sink for Auditing and Logging Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-a-wmi-sink-for-auditing-and-logging-events.md)  
  
-   [<span data-ttu-id="e29d7-114">Additional Resources</span><span class="sxs-lookup"><span data-stu-id="e29d7-114">Additional Resources</span></span>](../../adapters-and-accelerators/accelerator-hl7/additional-resources.md)