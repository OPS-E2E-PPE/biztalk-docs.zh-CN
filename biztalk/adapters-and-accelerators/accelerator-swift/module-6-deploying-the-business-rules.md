---
title: 模块 6： 部署业务规则 |Microsoft Docs
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
ms.openlocfilehash: 389d8038b5a216f90d85399eeefaebde86284c71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972838"
---
# <a name="module-6-deploying-the-business-rules"></a><span data-ttu-id="04525-102">模块 6： 部署业务规则</span><span class="sxs-lookup"><span data-stu-id="04525-102">Module 6: Deploying the Business Rules</span></span>
<span data-ttu-id="04525-103">在此模块中部署的业务规则、 确认你安装的日志，并确认您使用业务规则编辑器工具的部署。</span><span class="sxs-lookup"><span data-stu-id="04525-103">In this module, you deploy the business rules, confirm your installation log, and confirm your deployment using the Business Rule Composer tool.</span></span>  
  
 <span data-ttu-id="04525-104">使用业务规则以确保 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]消息符合格式规范、 字段规范和验证的网络规则对全球范围内 Interbank 金融电信 (SWIFT) 标准协会中定义。</span><span class="sxs-lookup"><span data-stu-id="04525-104">You use business rules to ensure that Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] messages adhere to format specifications, field specifications, and network validated rules as defined in the Society for Worldwide Interbank Financial Telecommunication (SWIFT) standards.</span></span> <span data-ttu-id="04525-105">格式规范适用于整个消息的结构和字段规范详细信息消息中的每个字段。</span><span class="sxs-lookup"><span data-stu-id="04525-105">Format specifications pertain to the structure of the message as a whole and field specifications detail each field in the message.</span></span> <span data-ttu-id="04525-106">验证的网络规则适用于跨字段验证，并在本质上复杂。</span><span class="sxs-lookup"><span data-stu-id="04525-106">Network validated rules apply to cross-field validations and are complex in nature.</span></span>  
  
 <span data-ttu-id="04525-107">A4SWIFT 提供了为每个消息的 XSD 架构规范。</span><span class="sxs-lookup"><span data-stu-id="04525-107">A4SWIFT provides XSD schema specifications for each message.</span></span> <span data-ttu-id="04525-108">A4SWIFT 拆装器 (DASM) 和组装器 (ASM) 使用架构来分析或序列化和验证本机平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="04525-108">The A4SWIFT disassembler (DASM) and assembler (ASM) use the schema to parse or serialize and validate native flat-file messages.</span></span> <span data-ttu-id="04525-109">验证被限制为格式规范和字段规范架构进行编码。</span><span class="sxs-lookup"><span data-stu-id="04525-109">Validations are limited to format specifications and field specifications that the schema encodes.</span></span> <span data-ttu-id="04525-110">但是，无法对某些格式进行编码和字段架构中的相关的规则。</span><span class="sxs-lookup"><span data-stu-id="04525-110">However, you cannot encode some formats and field related rules within the schema.</span></span>  
  
 <span data-ttu-id="04525-111">A4SWIFT 还包括一组按照 SWIFT 标准发布指南 (SRG) 的业务规则。</span><span class="sxs-lookup"><span data-stu-id="04525-111">A4SWIFT also includes a set of business rules that follow the SWIFT Standards Release Guides (SRG).</span></span> <span data-ttu-id="04525-112">BizTalk Server 业务规则引擎 (BRE) 调用 A4SWIFT 策略，并强制执行 A4SWIFT 业务规则。</span><span class="sxs-lookup"><span data-stu-id="04525-112">The BizTalk Server Business Rule Engine (BRE) calls the A4SWIFT policies and enforces the A4SWIFT business rules.</span></span>  
  
 <span data-ttu-id="04525-113">由于与格式和字段和超出了该架构的自然功能的网络验证规则相关的复杂验证中包含这些业务规则。</span><span class="sxs-lookup"><span data-stu-id="04525-113">These business rules are included due to the complex validations relating to format and fields, and network-validated rules that are beyond the natural capability of the schema.</span></span> <span data-ttu-id="04525-114">SWIFT DASM 或 ASM 组件在接收或发送管道中的调用 BRE。</span><span class="sxs-lookup"><span data-stu-id="04525-114">The SWIFT DASM or ASM components within a receive or send pipeline call the BRE.</span></span>  
  
 <span data-ttu-id="04525-115">通过更改将验证打开或关闭**BREValidation** DASM 在管道中的属性。</span><span class="sxs-lookup"><span data-stu-id="04525-115">You turn the validations on or off by changing the **BREValidation** property for the DASM within your pipeline.</span></span>  
  
 <span data-ttu-id="04525-116">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="04525-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="04525-117">第 1 课：部署相关业务规则</span><span class="sxs-lookup"><span data-stu-id="04525-117">Lesson 1: Deploying the Related Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [<span data-ttu-id="04525-118">第 2 课：使用业务规则编辑器工具确认部署</span><span class="sxs-lookup"><span data-stu-id="04525-118">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)