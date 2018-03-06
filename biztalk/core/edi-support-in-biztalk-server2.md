---
title: "EDI 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04cd9c14b9c3663bdf332155cc9824e1681ca7a6
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="edi-support-in-biztalk-server"></a><span data-ttu-id="7183b-102">BizTalk Server 中的 EDI 支持</span><span class="sxs-lookup"><span data-stu-id="7183b-102">EDI Support in BizTalk Server</span></span>
<span data-ttu-id="7183b-103">EDI 是内置于 BizTalk Server 中，安装和配置 BizTalk Server 时，一个可选组件。</span><span class="sxs-lookup"><span data-stu-id="7183b-103">EDI is built-in to BizTalk Server, and is an optional component when you install and configure BizTalk Server.</span></span> 
  
## <a name="feature-set-comparison-chart"></a><span data-ttu-id="7183b-104">功能集比较表</span><span class="sxs-lookup"><span data-stu-id="7183b-104">Feature Set Comparison Chart</span></span>  
 <span data-ttu-id="7183b-105">下表显示了包含与 BizTalk Server EDI 支持。</span><span class="sxs-lookup"><span data-stu-id="7183b-105">The following table shows the EDI support included with BizTalk Server.</span></span>
  
|<span data-ttu-id="7183b-106">功能</span><span class="sxs-lookup"><span data-stu-id="7183b-106">Feature</span></span>|<span data-ttu-id="7183b-107">注释</span><span class="sxs-lookup"><span data-stu-id="7183b-107">Comment</span></span>|  
|---|---|
|<span data-ttu-id="7183b-108">在事务集 ISA 段修改</span><span class="sxs-lookup"><span data-stu-id="7183b-108">ISA    Segment modification at transaction set</span></span>| <span data-ttu-id="7183b-109">创建 TransactionSet 特定协议</span><span class="sxs-lookup"><span data-stu-id="7183b-109">Create TransactionSet-specific agreements</span></span>|  
|<span data-ttu-id="7183b-110">ISA11︰ 美国或其他标准类型</span><span class="sxs-lookup"><span data-stu-id="7183b-110">ISA11:    US or other standard type</span></span>| |  
|<span data-ttu-id="7183b-111">ISA12︰ 交换控件版本</span><span class="sxs-lookup"><span data-stu-id="7183b-111">ISA12:    Interchange Control Version</span></span>| |  
|<span data-ttu-id="7183b-112">ISA13︰ 交换控制编号 （递增数）</span><span class="sxs-lookup"><span data-stu-id="7183b-112">ISA13:    Interchange Control Number (incrementing number)</span></span>| |  
|<span data-ttu-id="7183b-113">ISA15︰ 测试或生产</span><span class="sxs-lookup"><span data-stu-id="7183b-113">ISA15:    Test or Production</span></span>| |  
|<span data-ttu-id="7183b-114">文档/事务级别的 GS 段修改</span><span class="sxs-lookup"><span data-stu-id="7183b-114">GS    Segment modification at document/transaction level</span></span>| |  
|<span data-ttu-id="7183b-115">GS 发送者/接收者 Id 可以是不同于 ISA</span><span class="sxs-lookup"><span data-stu-id="7183b-115">GS    sender/receiver IDs allowed to be different than ISA</span></span>| |  
|<span data-ttu-id="7183b-116">入站文档 Id 不同于 ISA 和 GS 出站 Id</span><span class="sxs-lookup"><span data-stu-id="7183b-116">Inbound    Document IDs different than ISA & GS Outbound IDs</span></span>| |  
|<span data-ttu-id="7183b-117">GS01︰ 能够更改文档的类型</span><span class="sxs-lookup"><span data-stu-id="7183b-117">GS01:    Ability to change type of document</span></span>| |  
|<span data-ttu-id="7183b-118">GS04︰ 日期 （能够更改格式）</span><span class="sxs-lookup"><span data-stu-id="7183b-118">GS04:    Date (Ability to change format)</span></span>|<span data-ttu-id="7183b-119">包含用于为 CCYYMMDD 和 YYMMDD 选择格式的 UI</span><span class="sxs-lookup"><span data-stu-id="7183b-119">Contains UI to select format as CCYYMMDD and YYMMDD</span></span>|  
|<span data-ttu-id="7183b-120">GS05︰ 时间 （能够更改格式）</span><span class="sxs-lookup"><span data-stu-id="7183b-120">GS05:    Time (Ability to change format)</span></span>|<span data-ttu-id="7183b-121">包含用于选择 HHMM、 HHMMSS，和 HHMMSSdd 格式的 UI</span><span class="sxs-lookup"><span data-stu-id="7183b-121">Contains UI to select format as HHMM, HHMMSS, and HHMMSSdd</span></span>|  
|<span data-ttu-id="7183b-122">GS06︰ 更改控制编号</span><span class="sxs-lookup"><span data-stu-id="7183b-122">GS06:    Change the control number</span></span>| |  
|<span data-ttu-id="7183b-123">GS07︰ 代理代码</span><span class="sxs-lookup"><span data-stu-id="7183b-123">GS07:    Agency Code</span></span>| |  
|<span data-ttu-id="7183b-124">GS08︰ 能够将放入标准版本</span><span class="sxs-lookup"><span data-stu-id="7183b-124">GS08:    Able to put in standards version</span></span>| |  
|<span data-ttu-id="7183b-125">在运行时覆盖 EDI 信封的能力</span><span class="sxs-lookup"><span data-stu-id="7183b-125">Ability to override EDI envelope at runtime</span></span>| |  
|<span data-ttu-id="7183b-126">自定义的 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="7183b-126">Custom    EDI Schemas</span></span>| |  
|<span data-ttu-id="7183b-127">组织/参与方设置</span><span class="sxs-lookup"><span data-stu-id="7183b-127">Organization/Party Setting</span></span>|<span data-ttu-id="7183b-128">创建单独的方和协议。</span><span class="sxs-lookup"><span data-stu-id="7183b-128">Create separate party and agreements.</span></span> <span data-ttu-id="7183b-129">此外创建基于模板的协议。</span><span class="sxs-lookup"><span data-stu-id="7183b-129">Also create agreements based off templates.</span></span>|  
|<span data-ttu-id="7183b-130">通过文档定义路由的 EDI 文档</span><span class="sxs-lookup"><span data-stu-id="7183b-130">EDI    document routing via document definition</span></span>| |  
|<span data-ttu-id="7183b-131">自动向贸易合作伙伴发送 997</span><span class="sxs-lookup"><span data-stu-id="7183b-131">Automatic 997’s to trading partners</span></span>|<span data-ttu-id="7183b-132">配置特定于业务配置文件</span><span class="sxs-lookup"><span data-stu-id="7183b-132">Configuration specific to business profiles</span></span>|  
|<span data-ttu-id="7183b-133">可靠消息传递通过 997 的出站 EDI</span><span class="sxs-lookup"><span data-stu-id="7183b-133">Outbound    EDI reliable messaging via 997’s</span></span>| |  
|<span data-ttu-id="7183b-134">EDIFACT 支持</span><span class="sxs-lookup"><span data-stu-id="7183b-134">EDIFACT    Support</span></span>|<span data-ttu-id="7183b-135">每个 ISO 9735 v4.1 支持到 D05 D93</span><span class="sxs-lookup"><span data-stu-id="7183b-135">Supports D93 to D05 per ISO 9735 v4.1</span></span>|  
|<span data-ttu-id="7183b-136">X12 支持</span><span class="sxs-lookup"><span data-stu-id="7183b-136">X12    Support</span></span>|<span data-ttu-id="7183b-137">2040 到 5030</span><span class="sxs-lookup"><span data-stu-id="7183b-137">2040 to 5030</span></span>|  
|<span data-ttu-id="7183b-138">HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="7183b-138">HIPAA support</span></span>| <span data-ttu-id="7183b-139">Microsoft BizTalk 快捷键的 HIPAA (BTAHIPAA) 作为本机 EDI 功能的一部分</span><span class="sxs-lookup"><span data-stu-id="7183b-139">Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) as  part of native EDI functionality</span></span>|  
|<span data-ttu-id="7183b-140">枚举器/代码列表删除功能</span><span class="sxs-lookup"><span data-stu-id="7183b-140">Ability to remove enumerators/codelists</span></span>|<span data-ttu-id="7183b-141">使用 Visual Studio/BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="7183b-141">Use Visual Studio/BizTalk Editor</span></span>|  
|<span data-ttu-id="7183b-142">AS2 发送/接收</span><span class="sxs-lookup"><span data-stu-id="7183b-142">AS2    Send/Receive</span></span>| <span data-ttu-id="7183b-143">AS2 适用于多文件附件支持、 文件名保留支持和互操作性 Drummond 认证。</span><span class="sxs-lookup"><span data-stu-id="7183b-143">AS2 is Drummond Certified for multi-file attachment support, file name preservation support and interoperability.</span></span>|  
|<span data-ttu-id="7183b-144">AS2 文件名称保存</span><span class="sxs-lookup"><span data-stu-id="7183b-144">AS2 file name preservation</span></span>| |  
|<span data-ttu-id="7183b-145">AS2 可靠消息传递</span><span class="sxs-lookup"><span data-stu-id="7183b-145">AS2 reliable messaging</span></span>| |  
|<span data-ttu-id="7183b-146">（累积单个事务中的多个事务类型） 的出站批处理</span><span class="sxs-lookup"><span data-stu-id="7183b-146">Outbound    Batching (accumulating multiple transaction types in a single transaction)</span></span>|<span data-ttu-id="7183b-147">对于每个业务配置文件支持多个批处理配置</span><span class="sxs-lookup"><span data-stu-id="7183b-147">Supports multiple batch configurations for each business profile</span></span>|  
|<span data-ttu-id="7183b-148">入站批处理 – 交换 XML （保留将传入的批处理交换） 或基于配置选项的事务设置 XML</span><span class="sxs-lookup"><span data-stu-id="7183b-148">Inbound    Batching – Interchange XML (preserving an incoming ‘batched’ interchange) or Transaction Set XML based off configuration options</span></span>|<span data-ttu-id="7183b-149">此外支持入站-debatching，即，拆分成单个事务设置 Xml 的交换</span><span class="sxs-lookup"><span data-stu-id="7183b-149">Also supports inbound-debatching, i.e., splitting interchange into individual Transaction Set Xml</span></span>|  
|<span data-ttu-id="7183b-150">交换和事务设置生成和验证在 Visual Studio 中的设计时</span><span class="sxs-lookup"><span data-stu-id="7183b-150">Interchange    and Transaction Set Generation and Validation in Design Time in Visual Studio</span></span>| |  
|<span data-ttu-id="7183b-151">TA1 (技术 ACK) 生成和对帐</span><span class="sxs-lookup"><span data-stu-id="7183b-151">TA1    (Technical ACK) Generation and Reconciliation</span></span>| |  
|<span data-ttu-id="7183b-152">可选的 EDI 和 XSD 验证标志</span><span class="sxs-lookup"><span data-stu-id="7183b-152">Optional    EDI and XSD Validation flags</span></span>| |  
|<span data-ttu-id="7183b-153">文档的格式定义，可在 GS 级别</span><span class="sxs-lookup"><span data-stu-id="7183b-153">Document    format/definition at GS level</span></span>| |  
  
## <a name="see-also"></a><span data-ttu-id="7183b-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7183b-154">See Also</span></span>  
 <span data-ttu-id="7183b-155">[EDI 标准支持](../core/edi-standards-support.md) </span><span class="sxs-lookup"><span data-stu-id="7183b-155">[EDI Standards Support](../core/edi-standards-support.md) </span></span>  
 <span data-ttu-id="7183b-156">[EDI 文档架构支持](../core/edi-document-schema-support.md) </span><span class="sxs-lookup"><span data-stu-id="7183b-156">[EDI Document Schema Support](../core/edi-document-schema-support.md) </span></span>  
 [<span data-ttu-id="7183b-157">EDI 字符集支持</span><span class="sxs-lookup"><span data-stu-id="7183b-157">EDI Character Set Support</span></span>](../core/edi-character-set-support.md)