---
title: "SWIFT 标头和预告片架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trailer schemas
- schemas, headers
- schemas, trailers
- header schemas
ms.assetid: 82cd33d4-6bbb-4124-9506-fd35b5dca8a4
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f3cb45e14a7c7e900fc26a4cbc8fcfb5d7b66e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-header-and-trailer-schemas"></a><span data-ttu-id="eae60-102">SWIFT 标头和预告片架构</span><span class="sxs-lookup"><span data-stu-id="eae60-102">SWIFT Header and Trailer Schemas</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="eae60-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供 SWIFT 标头和尾的架构。</span><span class="sxs-lookup"><span data-stu-id="eae60-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides the SWIFT header and trailer schemas.</span></span> <span data-ttu-id="eae60-104">A4SWIFT 已合并这些到各种 FIN 消息的交换架构。</span><span class="sxs-lookup"><span data-stu-id="eae60-104">A4SWIFT has already incorporated these into the interchange schemas for the various FIN messages.</span></span> <span data-ttu-id="eae60-105">如果你想要创建一个自定义的 SWIFT FIN 格式样式消息类型 （例如，N98 消息），你可以将标头和尾架构合并到你自己的格式。</span><span class="sxs-lookup"><span data-stu-id="eae60-105">If you want to create a custom SWIFT FIN format style message type (for example, an N98 message), you can incorporate the header and trailer schemas into your own format.</span></span>  
  
 <span data-ttu-id="eae60-106">SWIFT 标头架构 (SWIFT Header.xsd) 包含以下格式：</span><span class="sxs-lookup"><span data-stu-id="eae60-106">The SWIFT header schema (SWIFT Header.xsd) contains the formats for the following:</span></span>  
  
-   <span data-ttu-id="eae60-107">基本的标头</span><span class="sxs-lookup"><span data-stu-id="eae60-107">Basic Header</span></span>  
  
-   <span data-ttu-id="eae60-108">应用程序标头 （选择的输入或输出）</span><span class="sxs-lookup"><span data-stu-id="eae60-108">Application Header (choice of Input or Output)</span></span>  
  
-   <span data-ttu-id="eae60-109">用户标头</span><span class="sxs-lookup"><span data-stu-id="eae60-109">User Header</span></span>  
  
-   <span data-ttu-id="eae60-110">从文本块分隔符</span><span class="sxs-lookup"><span data-stu-id="eae60-110">Beginning delimiter of the text block</span></span>  
  
 <span data-ttu-id="eae60-111">基本的标头包含有关消息的源信息。</span><span class="sxs-lookup"><span data-stu-id="eae60-111">The Basic Header contains information about the source of the message.</span></span> <span data-ttu-id="eae60-112">应用程序标头包含有关消息类型和消息的目标的信息。</span><span class="sxs-lookup"><span data-stu-id="eae60-112">The Application Header contains information about the message type and the destination of the message.</span></span> <span data-ttu-id="eae60-113">SWIFT 拆装器接收管道中的消息类型的解析取决于相应的应用程序标头中的字段的内容。</span><span class="sxs-lookup"><span data-stu-id="eae60-113">The resolution of the message type by the SWIFT disassembler in a receive pipeline is based upon the contents of the field in the appropriate Application Header.</span></span> <span data-ttu-id="eae60-114">用户标头是可选的并包含特殊的处理指令。</span><span class="sxs-lookup"><span data-stu-id="eae60-114">The User Header is optional, and contains special processing instructions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eae60-115">几种消息类型具有基于字段 119 用户标头中的内容的变量格式。</span><span class="sxs-lookup"><span data-stu-id="eae60-115">A few message types have variable formats based upon the contents of field 119 in the User Header.</span></span> <span data-ttu-id="eae60-116">这些是 A4SWIFT 中的"双向消息类型"。</span><span class="sxs-lookup"><span data-stu-id="eae60-116">These are "dual message types" in A4SWIFT.</span></span> <span data-ttu-id="eae60-117">A4SWIFT 反汇编程序使用在结合字段 119 的内容应用程序标头中的消息类型选择消息实例的相应架构。</span><span class="sxs-lookup"><span data-stu-id="eae60-117">The A4SWIFT disassembler uses the message type in the Application Header in conjunction with the contents of field 119 to select the appropriate schema for a message instance.</span></span>  
  
 <span data-ttu-id="eae60-118">*SWIFT 用户手册*，FIN 服务中的 SWIFT 文档的一部分介绍了所有这些标头。</span><span class="sxs-lookup"><span data-stu-id="eae60-118">The *SWIFT User Handbook*, which is part of the SWIFT documentation for the FIN service, describes all of these headers.</span></span>  
  
 <span data-ttu-id="eae60-119">文本块的开头为"{4:"跟回车符和换行符。</span><span class="sxs-lookup"><span data-stu-id="eae60-119">The beginning of the text block is "{4:" followed by a carriage return and line feed.</span></span> <span data-ttu-id="eae60-120">文本块的开头是必需的。</span><span class="sxs-lookup"><span data-stu-id="eae60-120">The beginning of the text block is required.</span></span>  
  
 <span data-ttu-id="eae60-121">为了容纳处理 （分析和验证） 包含仅 SWIFT 的交换的交换的架构中的所有标头和尾块的块 4，被标记为可选。</span><span class="sxs-lookup"><span data-stu-id="eae60-121">In order to accommodate processing (parsing and validation) of interchanges containing only SWIFT block 4, all header and trailer blocks in the interchange schemas are marked as optional.</span></span> <span data-ttu-id="eae60-122">这偏离基本标头块 1 和 2 的应用程序标头块是必需的 SWIFT FIN 规范。</span><span class="sxs-lookup"><span data-stu-id="eae60-122">This deviates from the SWIFT FIN specification, where the Basic Header block 1 and the Application Header block 2 are mandatory.</span></span> <span data-ttu-id="eae60-123">这使你能够使用交换架构来处理不需要标头的消息。</span><span class="sxs-lookup"><span data-stu-id="eae60-123">This enables you to use the interchange schema to handle messages that do not require headers.</span></span> <span data-ttu-id="eae60-124">例如，如果接受通过 FileAct 接收的消息时，批处理标头可能包含的消息，以及常见的消息类型的源。</span><span class="sxs-lookup"><span data-stu-id="eae60-124">For example, if you are accepting messages received through FileAct, the batch header may contain the source of the messages as well as a common message type.</span></span>  
  
 <span data-ttu-id="eae60-125">运行时架构 DLL 还包括标头架构。</span><span class="sxs-lookup"><span data-stu-id="eae60-125">The RunTime schema DLL also includes the header schema.</span></span> <span data-ttu-id="eae60-126">A4SWIFT 安装部署运行时架构 DLL 和 A4SWIFT 属性架构。</span><span class="sxs-lookup"><span data-stu-id="eae60-126">A4SWIFT installation deploys the RunTime schema DLL and the A4SWIFT property schema.</span></span> <span data-ttu-id="eae60-127">如果你需要使用你自己的标头进行处理，可以定义和部署自定义标头架构，并将提升用于消息解析适当的属性。</span><span class="sxs-lookup"><span data-stu-id="eae60-127">If you need to use your own header for processing, you can define and deploy a custom header schema, and promote the appropriate properties for message resolution.</span></span> <span data-ttu-id="eae60-128">如果这样做，你将还需要指定 SWIFT 反汇编程序 (DASM) 到新的标头。</span><span class="sxs-lookup"><span data-stu-id="eae60-128">If you do so, you will also need to specify the new header to the SWIFT disassembler (DASM).</span></span> <span data-ttu-id="eae60-129">自定义标头架构不应有和 SWIFT 标头的架构相同的文档类型安装在运行时架构 DLL 中已部署该 A4SWIFT。</span><span class="sxs-lookup"><span data-stu-id="eae60-129">The custom header schema should not have the same Document Type as the SWIFT header schema that A4SWIFT installation has deployed in the RunTime schemas DLL.</span></span> <span data-ttu-id="eae60-130">请务必更改架构命名空间，和 / 或根节点名称。</span><span class="sxs-lookup"><span data-stu-id="eae60-130">Be sure to change the schema namespace, or root node name, or both.</span></span>  
  
 <span data-ttu-id="eae60-131">SWIFT 尾部架构 (**SWIFT Trailer.xsd**) 包含以下格式：</span><span class="sxs-lookup"><span data-stu-id="eae60-131">The SWIFT Trailer schema (**SWIFT Trailer.xsd**) contains the format for the following:</span></span>  
  
-   <span data-ttu-id="eae60-132">结束分隔符的文本块</span><span class="sxs-lookup"><span data-stu-id="eae60-132">Ending delimiter of the text block</span></span>  
  
-   <span data-ttu-id="eae60-133">用户拖车安排 （用户和系统信息）</span><span class="sxs-lookup"><span data-stu-id="eae60-133">User trailers (user and system information)</span></span>  
  
-   <span data-ttu-id="eae60-134">系统拖车安排</span><span class="sxs-lookup"><span data-stu-id="eae60-134">System trailers</span></span>  
  
 <span data-ttu-id="eae60-135">结束分隔符的文本块是"-}"。</span><span class="sxs-lookup"><span data-stu-id="eae60-135">The ending delimiter of the text block is "-}".</span></span> <span data-ttu-id="eae60-136">电影预告片块开头"{5:"。</span><span class="sxs-lookup"><span data-stu-id="eae60-136">The trailer block begins with "{5:".</span></span> <span data-ttu-id="eae60-137">电影预告片块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用、 可能的重复消息和等等）。</span><span class="sxs-lookup"><span data-stu-id="eae60-137">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on) and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="eae60-138">拖车安排添加 SWIFT 还提供分隔的第三个块"{s:"。</span><span class="sxs-lookup"><span data-stu-id="eae60-138">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="eae60-139">*SWIFT 用户手册*，在"FIN 服务说明"下详细地介绍了块 5 的内容。</span><span class="sxs-lookup"><span data-stu-id="eae60-139">The *SWIFT User Handbook*, under "FIN Service Description", describes in detail the contents of block 5.</span></span> <span data-ttu-id="eae60-140">A4SWIFT 不会验证内容块 s。</span><span class="sxs-lookup"><span data-stu-id="eae60-140">A4SWIFT does not validate the contents of block S.</span></span>  
  
 <span data-ttu-id="eae60-141">实际的 FIN 接口或 SWIFT 网络追加拖车安排。</span><span class="sxs-lookup"><span data-stu-id="eae60-141">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="eae60-142">如果消息包含尾部 A4SWIFT 收到消息时，A4SWIFT 会带来的尾部，并显示消息。</span><span class="sxs-lookup"><span data-stu-id="eae60-142">If a message contains a trailer when A4SWIFT receives the message, A4SWIFT carries the trailer with the message.</span></span> <span data-ttu-id="eae60-143">如果消息不包含尾部 A4SWIFT 收到消息时，A4SWIFT 不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="eae60-143">A4SWIFT does not raise an error if a message does not contain a trailer when A4SWIFT receives the message.</span></span> <span data-ttu-id="eae60-144">作为标头，与所有预告片项，包括块本身，是可选的 A4SWIFT 中。</span><span class="sxs-lookup"><span data-stu-id="eae60-144">As with headers, all of the trailer entries, including the blocks themselves, are optional in A4SWIFT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae60-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eae60-145">See Also</span></span>  
 [<span data-ttu-id="eae60-146">使用架构</span><span class="sxs-lookup"><span data-stu-id="eae60-146">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)