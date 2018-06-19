---
title: 模块 6： 部署业务规则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e890456b7ff3e467a0f513a261d12a52f92689f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207989"
---
# <a name="module-6-deploying-the-business-rules"></a><span data-ttu-id="2b507-102">模块 6： 部署业务规则</span><span class="sxs-lookup"><span data-stu-id="2b507-102">Module 6: Deploying the Business Rules</span></span>
<span data-ttu-id="2b507-103">在此模块中，你部署的业务规则，确认你的安装日志，并确认使用业务规则编辑器工具部署。</span><span class="sxs-lookup"><span data-stu-id="2b507-103">In this module, you deploy the business rules, confirm your installation log, and confirm your deployment using the Business Rule Composer tool.</span></span>  
  
 <span data-ttu-id="2b507-104">使用业务规则以确保[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]消息遵循格式规范、 字段规范和验证的网络规则全球 Interbank 财务电信 (SWIFT) 标准互联网协会中定义。</span><span class="sxs-lookup"><span data-stu-id="2b507-104">You use business rules to ensure that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] messages adhere to format specifications, field specifications, and network validated rules as defined in the Society for Worldwide Interbank Financial Telecommunication (SWIFT) standards.</span></span> <span data-ttu-id="2b507-105">格式规范适用于整个消息的结构和字段规范详细信息消息中的每个字段。</span><span class="sxs-lookup"><span data-stu-id="2b507-105">Format specifications pertain to the structure of the message as a whole and field specifications detail each field in the message.</span></span> <span data-ttu-id="2b507-106">网络验证规则应用于跨字段验证和复杂本质。</span><span class="sxs-lookup"><span data-stu-id="2b507-106">Network validated rules apply to cross-field validations and are complex in nature.</span></span>  
  
 <span data-ttu-id="2b507-107">A4SWIFT 提供 XSD 架构规范，为每个消息。</span><span class="sxs-lookup"><span data-stu-id="2b507-107">A4SWIFT provides XSD schema specifications for each message.</span></span> <span data-ttu-id="2b507-108">A4SWIFT 反汇编程序 (DASM) 和汇编程序 (ASM) 使用架构来分析或序列化和验证本机平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="2b507-108">The A4SWIFT disassembler (DASM) and assembler (ASM) use the schema to parse or serialize and validate native flat-file messages.</span></span> <span data-ttu-id="2b507-109">验证仅限于格式规范和字段规范架构进行编码。</span><span class="sxs-lookup"><span data-stu-id="2b507-109">Validations are limited to format specifications and field specifications that the schema encodes.</span></span> <span data-ttu-id="2b507-110">但是，不能对某些格式进行编码，并且字段相关的规则，架构中。</span><span class="sxs-lookup"><span data-stu-id="2b507-110">However, you cannot encode some formats and field related rules within the schema.</span></span>  
  
 <span data-ttu-id="2b507-111">A4SWIFT 还包括一套按照 SWIFT 标准版本指南 (SRG) 的业务规则。</span><span class="sxs-lookup"><span data-stu-id="2b507-111">A4SWIFT also includes a set of business rules that follow the SWIFT Standards Release Guides (SRG).</span></span> <span data-ttu-id="2b507-112">BizTalk Server 业务规则引擎 (BRE) 调用 A4SWIFT 策略，并强制执行 A4SWIFT 业务规则。</span><span class="sxs-lookup"><span data-stu-id="2b507-112">The BizTalk Server Business Rule Engine (BRE) calls the A4SWIFT policies and enforces the A4SWIFT business rules.</span></span>  
  
 <span data-ttu-id="2b507-113">这些业务规则是包含由于复杂的验证与格式和字段，和将超出架构的自然功能的网络验证规则。</span><span class="sxs-lookup"><span data-stu-id="2b507-113">These business rules are included due to the complex validations relating to format and fields, and network-validated rules that are beyond the natural capability of the schema.</span></span> <span data-ttu-id="2b507-114">在接收或发送管道中的 SWIFT DASM 或 ASM 组件调用 BRE。</span><span class="sxs-lookup"><span data-stu-id="2b507-114">The SWIFT DASM or ASM components within a receive or send pipeline call the BRE.</span></span>  
  
 <span data-ttu-id="2b507-115">通过更改将验证打开或关闭**BREValidation** DASM 在你的管道中的属性。</span><span class="sxs-lookup"><span data-stu-id="2b507-115">You turn the validations on or off by changing the **BREValidation** property for the DASM within your pipeline.</span></span>  
  
 <span data-ttu-id="2b507-116">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="2b507-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="2b507-117">第 1 课： 部署相关的业务规则</span><span class="sxs-lookup"><span data-stu-id="2b507-117">Lesson 1: Deploying the Related Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [<span data-ttu-id="2b507-118">第 2 课： 确认使用业务规则 Composer 工具部署</span><span class="sxs-lookup"><span data-stu-id="2b507-118">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)