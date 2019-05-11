---
title: EDI 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b1c7ba658d3f7921fb0a96b25c06d18e45e81d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350211"
---
# <a name="edi-support-in-biztalk-server"></a><span data-ttu-id="638aa-102">BizTalk Server 中的 EDI 支持</span><span class="sxs-lookup"><span data-stu-id="638aa-102">EDI Support in BizTalk Server</span></span>
<span data-ttu-id="638aa-103">EDI 内置于 BizTalk Server，安装和配置 BizTalk Server 时是一个可选组件。</span><span class="sxs-lookup"><span data-stu-id="638aa-103">EDI is built-in to BizTalk Server, and is an optional component when you install and configure BizTalk Server.</span></span> 
  
## <a name="feature-set-comparison-chart"></a><span data-ttu-id="638aa-104">功能集比较表</span><span class="sxs-lookup"><span data-stu-id="638aa-104">Feature Set Comparison Chart</span></span>  
 <span data-ttu-id="638aa-105">下表显示了 BizTalk Server 附带的 EDI 支持。</span><span class="sxs-lookup"><span data-stu-id="638aa-105">The following table shows the EDI support included with BizTalk Server.</span></span>
  
|<span data-ttu-id="638aa-106">功能</span><span class="sxs-lookup"><span data-stu-id="638aa-106">Feature</span></span>|<span data-ttu-id="638aa-107">注释</span><span class="sxs-lookup"><span data-stu-id="638aa-107">Comment</span></span>|  
|---|---|
|<span data-ttu-id="638aa-108">事务集级别的 ISA 段修改</span><span class="sxs-lookup"><span data-stu-id="638aa-108">ISA    Segment modification at transaction set</span></span>| <span data-ttu-id="638aa-109">创建特定于事务集的协议</span><span class="sxs-lookup"><span data-stu-id="638aa-109">Create TransactionSet-specific agreements</span></span>|  
|<span data-ttu-id="638aa-110">ISA11:  美国或其他标准类型</span><span class="sxs-lookup"><span data-stu-id="638aa-110">ISA11:    US or other standard type</span></span>| |  
|<span data-ttu-id="638aa-111">ISA12:  交换控制版本</span><span class="sxs-lookup"><span data-stu-id="638aa-111">ISA12:    Interchange Control Version</span></span>| |  
|<span data-ttu-id="638aa-112">ISA13:  交换控制编号 （递增编号）</span><span class="sxs-lookup"><span data-stu-id="638aa-112">ISA13:    Interchange Control Number (incrementing number)</span></span>| |  
|<span data-ttu-id="638aa-113">ISA15:  测试或生产</span><span class="sxs-lookup"><span data-stu-id="638aa-113">ISA15:    Test or Production</span></span>| |  
|<span data-ttu-id="638aa-114">文档/事务级别的 GS 段修改</span><span class="sxs-lookup"><span data-stu-id="638aa-114">GS    Segment modification at document/transaction level</span></span>| |  
|<span data-ttu-id="638aa-115">GS 发送方/接收方 Id 可以是不同于 ISA</span><span class="sxs-lookup"><span data-stu-id="638aa-115">GS    sender/receiver IDs allowed to be different than ISA</span></span>| |  
|<span data-ttu-id="638aa-116">入站的文档 Id 不同于 ISA & GS 出站 Id</span><span class="sxs-lookup"><span data-stu-id="638aa-116">Inbound    Document IDs different than ISA & GS Outbound IDs</span></span>| |  
|<span data-ttu-id="638aa-117">GS01:  若要更改的文档类型的功能</span><span class="sxs-lookup"><span data-stu-id="638aa-117">GS01:    Ability to change type of document</span></span>| |  
|<span data-ttu-id="638aa-118">GS04:  日期 （格式更改功能）</span><span class="sxs-lookup"><span data-stu-id="638aa-118">GS04:    Date (Ability to change format)</span></span>|<span data-ttu-id="638aa-119">包含用于选择 CCYYMMDD 和 YYMMDD 格式的 UI</span><span class="sxs-lookup"><span data-stu-id="638aa-119">Contains UI to select format as CCYYMMDD and YYMMDD</span></span>|  
|<span data-ttu-id="638aa-120">GS05:  时间 （格式更改功能）</span><span class="sxs-lookup"><span data-stu-id="638aa-120">GS05:    Time (Ability to change format)</span></span>|<span data-ttu-id="638aa-121">包含用于选择 HHMM、 HHMMSS 和 HHMMSSdd 格式的 UI</span><span class="sxs-lookup"><span data-stu-id="638aa-121">Contains UI to select format as HHMM, HHMMSS, and HHMMSSdd</span></span>|  
|<span data-ttu-id="638aa-122">GS06:  更改控制编号</span><span class="sxs-lookup"><span data-stu-id="638aa-122">GS06:    Change the control number</span></span>| |  
|<span data-ttu-id="638aa-123">GS07:  机构代码</span><span class="sxs-lookup"><span data-stu-id="638aa-123">GS07:    Agency Code</span></span>| |  
|<span data-ttu-id="638aa-124">GS08:  能够插入标准版本</span><span class="sxs-lookup"><span data-stu-id="638aa-124">GS08:    Able to put in standards version</span></span>| |  
|<span data-ttu-id="638aa-125">用于重写在运行时的 EDI 信封功能</span><span class="sxs-lookup"><span data-stu-id="638aa-125">Ability to override EDI envelope at runtime</span></span>| |  
|<span data-ttu-id="638aa-126">自定义 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="638aa-126">Custom    EDI Schemas</span></span>| |  
|<span data-ttu-id="638aa-127">组织/参与方设置</span><span class="sxs-lookup"><span data-stu-id="638aa-127">Organization/Party Setting</span></span>|<span data-ttu-id="638aa-128">创建单独的参与方和协议。</span><span class="sxs-lookup"><span data-stu-id="638aa-128">Create separate party and agreements.</span></span> <span data-ttu-id="638aa-129">此外创建协议模板为基础。</span><span class="sxs-lookup"><span data-stu-id="638aa-129">Also create agreements based off templates.</span></span>|  
|<span data-ttu-id="638aa-130">通过文档定义路由 EDI 文档</span><span class="sxs-lookup"><span data-stu-id="638aa-130">EDI    document routing via document definition</span></span>| |  
|<span data-ttu-id="638aa-131">自动发送 997 向贸易合作伙伴</span><span class="sxs-lookup"><span data-stu-id="638aa-131">Automatic 997’s to trading partners</span></span>|<span data-ttu-id="638aa-132">特定于业务配置文件配置</span><span class="sxs-lookup"><span data-stu-id="638aa-132">Configuration specific to business profiles</span></span>|  
|<span data-ttu-id="638aa-133">可靠消息传送通过 997 实现的出站 EDI</span><span class="sxs-lookup"><span data-stu-id="638aa-133">Outbound    EDI reliable messaging via 997’s</span></span>| |  
|<span data-ttu-id="638aa-134">EDIFACT 支持</span><span class="sxs-lookup"><span data-stu-id="638aa-134">EDIFACT    Support</span></span>|<span data-ttu-id="638aa-135">支持为 D93 到 D05 ISO 9735 4.1 版</span><span class="sxs-lookup"><span data-stu-id="638aa-135">Supports D93 to D05 per ISO 9735 v4.1</span></span>|  
|<span data-ttu-id="638aa-136">X12 支持</span><span class="sxs-lookup"><span data-stu-id="638aa-136">X12    Support</span></span>|<span data-ttu-id="638aa-137">2040 到 5030</span><span class="sxs-lookup"><span data-stu-id="638aa-137">2040 to 5030</span></span>|  
|<span data-ttu-id="638aa-138">HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="638aa-138">HIPAA support</span></span>| <span data-ttu-id="638aa-139">Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) 作为本机 EDI 功能的一部分</span><span class="sxs-lookup"><span data-stu-id="638aa-139">Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) as  part of native EDI functionality</span></span>|  
|<span data-ttu-id="638aa-140">删除/代码列表枚举器的功能</span><span class="sxs-lookup"><span data-stu-id="638aa-140">Ability to remove enumerators/codelists</span></span>|<span data-ttu-id="638aa-141">使用 Visual Studio/BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="638aa-141">Use Visual Studio/BizTalk Editor</span></span>|  
|<span data-ttu-id="638aa-142">AS2    Send/Receive</span><span class="sxs-lookup"><span data-stu-id="638aa-142">AS2    Send/Receive</span></span>| <span data-ttu-id="638aa-143">AS2 是多文件附件支持、 文件名保存支持和互操作性的 Drummond 认证。</span><span class="sxs-lookup"><span data-stu-id="638aa-143">AS2 is Drummond Certified for multi-file attachment support, file name preservation support and interoperability.</span></span>|  
|<span data-ttu-id="638aa-144">AS2 文件名称保存</span><span class="sxs-lookup"><span data-stu-id="638aa-144">AS2 file name preservation</span></span>| |  
|<span data-ttu-id="638aa-145">AS2 可靠消息传送</span><span class="sxs-lookup"><span data-stu-id="638aa-145">AS2 reliable messaging</span></span>| |  
|<span data-ttu-id="638aa-146">出站批处理 （累积在单个事务中的多个事务类型）</span><span class="sxs-lookup"><span data-stu-id="638aa-146">Outbound    Batching (accumulating multiple transaction types in a single transaction)</span></span>|<span data-ttu-id="638aa-147">为每个业务配置文件支持多个批处理配置</span><span class="sxs-lookup"><span data-stu-id="638aa-147">Supports multiple batch configurations for each business profile</span></span>|  
|<span data-ttu-id="638aa-148">入站批处理 – 交换 XML （保留传入批交换） 或根据配置选项的事务集 XML</span><span class="sxs-lookup"><span data-stu-id="638aa-148">Inbound    Batching – Interchange XML (preserving an incoming ‘batched’ interchange) or Transaction Set XML based off configuration options</span></span>|<span data-ttu-id="638aa-149">此外支持入站解除，交换拆分为单独的事务集 Xml</span><span class="sxs-lookup"><span data-stu-id="638aa-149">Also supports inbound-debatching, i.e., splitting interchange into individual Transaction Set Xml</span></span>|  
|<span data-ttu-id="638aa-150">交换及事务集生成和验证在 Visual Studio 中的设计时</span><span class="sxs-lookup"><span data-stu-id="638aa-150">Interchange    and Transaction Set Generation and Validation in Design Time in Visual Studio</span></span>| |  
|<span data-ttu-id="638aa-151">TA1 （技术确认） 生成和协调</span><span class="sxs-lookup"><span data-stu-id="638aa-151">TA1    (Technical ACK) Generation and Reconciliation</span></span>| |  
|<span data-ttu-id="638aa-152">可选的 EDI 和 XSD 验证标志</span><span class="sxs-lookup"><span data-stu-id="638aa-152">Optional    EDI and XSD Validation flags</span></span>| |  
|<span data-ttu-id="638aa-153">GS 级别的文档格式/定义</span><span class="sxs-lookup"><span data-stu-id="638aa-153">Document    format/definition at GS level</span></span>| |  
  
## <a name="see-also"></a><span data-ttu-id="638aa-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="638aa-154">See Also</span></span>  
 <span data-ttu-id="638aa-155">[EDI 标准支持](../core/edi-standards-support.md) </span><span class="sxs-lookup"><span data-stu-id="638aa-155">[EDI Standards Support](../core/edi-standards-support.md) </span></span>  
 <span data-ttu-id="638aa-156">[EDI 文档架构支持](../core/edi-document-schema-support.md) </span><span class="sxs-lookup"><span data-stu-id="638aa-156">[EDI Document Schema Support](../core/edi-document-schema-support.md) </span></span>  
 [<span data-ttu-id="638aa-157">EDI 字符集支持</span><span class="sxs-lookup"><span data-stu-id="638aa-157">EDI Character Set Support</span></span>](../core/edi-character-set-support.md)