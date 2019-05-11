---
title: SWIFT 标头和尾部架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailer schemas
- schemas, headers
- schemas, trailers
- header schemas
ms.assetid: 82cd33d4-6bbb-4124-9506-fd35b5dca8a4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2299ec3a45968cd0aaae2094ec892d03c70972f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529767"
---
# <a name="swift-header-and-trailer-schemas"></a><span data-ttu-id="f41a1-102">SWIFT 标头和尾部架构</span><span class="sxs-lookup"><span data-stu-id="f41a1-102">SWIFT Header and Trailer Schemas</span></span>
<span data-ttu-id="f41a1-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供 SWIFT 标头和尾部架构。</span><span class="sxs-lookup"><span data-stu-id="f41a1-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides the SWIFT header and trailer schemas.</span></span> <span data-ttu-id="f41a1-104">A4SWIFT 已合并到各种 FIN 消息的交换架构。</span><span class="sxs-lookup"><span data-stu-id="f41a1-104">A4SWIFT has already incorporated these into the interchange schemas for the various FIN messages.</span></span> <span data-ttu-id="f41a1-105">如果你想要创建一个自定义的 SWIFT FIN 格式样式消息类型 （例如，N98 消息），您可以将标头和尾部架构合并到您自己的格式。</span><span class="sxs-lookup"><span data-stu-id="f41a1-105">If you want to create a custom SWIFT FIN format style message type (for example, an N98 message), you can incorporate the header and trailer schemas into your own format.</span></span>  
  
 <span data-ttu-id="f41a1-106">SWIFT 标头架构 (SWIFT Header.xsd) 包含以下格式：</span><span class="sxs-lookup"><span data-stu-id="f41a1-106">The SWIFT header schema (SWIFT Header.xsd) contains the formats for the following:</span></span>  
  
- <span data-ttu-id="f41a1-107">基本的标头</span><span class="sxs-lookup"><span data-stu-id="f41a1-107">Basic Header</span></span>  
  
- <span data-ttu-id="f41a1-108">应用程序标头 （选择的输入或输出）</span><span class="sxs-lookup"><span data-stu-id="f41a1-108">Application Header (choice of Input or Output)</span></span>  
  
- <span data-ttu-id="f41a1-109">用户标头</span><span class="sxs-lookup"><span data-stu-id="f41a1-109">User Header</span></span>  
  
- <span data-ttu-id="f41a1-110">从开始分隔符的文本块</span><span class="sxs-lookup"><span data-stu-id="f41a1-110">Beginning delimiter of the text block</span></span>  
  
  <span data-ttu-id="f41a1-111">基本的标头包含有关消息的源的信息。</span><span class="sxs-lookup"><span data-stu-id="f41a1-111">The Basic Header contains information about the source of the message.</span></span> <span data-ttu-id="f41a1-112">应用程序标头包含有关消息类型和消息的目标信息。</span><span class="sxs-lookup"><span data-stu-id="f41a1-112">The Application Header contains information about the message type and the destination of the message.</span></span> <span data-ttu-id="f41a1-113">SWIFT 反汇编程序的接收管道中的消息类型的解决方法取决于相应的应用程序标头中的字段的内容。</span><span class="sxs-lookup"><span data-stu-id="f41a1-113">The resolution of the message type by the SWIFT disassembler in a receive pipeline is based upon the contents of the field in the appropriate Application Header.</span></span> <span data-ttu-id="f41a1-114">用户标头是可选的并包含特殊的处理指令。</span><span class="sxs-lookup"><span data-stu-id="f41a1-114">The User Header is optional, and contains special processing instructions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f41a1-115">几种消息类型具有变量格式基于字段 119 用户标头中的内容。</span><span class="sxs-lookup"><span data-stu-id="f41a1-115">A few message types have variable formats based upon the contents of field 119 in the User Header.</span></span> <span data-ttu-id="f41a1-116">这些是在 A4SWIFT 中的"双消息类型"。</span><span class="sxs-lookup"><span data-stu-id="f41a1-116">These are "dual message types" in A4SWIFT.</span></span> <span data-ttu-id="f41a1-117">A4SWIFT 拆装器中的字段 119 内容与一起使用的应用程序标头中使用消息类型选择相应的架构的消息实例。</span><span class="sxs-lookup"><span data-stu-id="f41a1-117">The A4SWIFT disassembler uses the message type in the Application Header in conjunction with the contents of field 119 to select the appropriate schema for a message instance.</span></span>  
  
 <span data-ttu-id="f41a1-118">*SWIFT 用户手册*，这是查找服务的 SWIFT 文档的一部分介绍了所有这些标头。</span><span class="sxs-lookup"><span data-stu-id="f41a1-118">The *SWIFT User Handbook*, which is part of the SWIFT documentation for the FIN service, describes all of these headers.</span></span>  
  
 <span data-ttu-id="f41a1-119">文本块的开头是"{4:"后跟回车符和换行符。</span><span class="sxs-lookup"><span data-stu-id="f41a1-119">The beginning of the text block is "{4:" followed by a carriage return and line feed.</span></span> <span data-ttu-id="f41a1-120">文本块的开头是必需的。</span><span class="sxs-lookup"><span data-stu-id="f41a1-120">The beginning of the text block is required.</span></span>  
  
 <span data-ttu-id="f41a1-121">为了适应处理 （分析和验证） 包含仅 SWIFT 的交换的交换架构中的所有标头和尾部块的块 4，标记为可选。</span><span class="sxs-lookup"><span data-stu-id="f41a1-121">In order to accommodate processing (parsing and validation) of interchanges containing only SWIFT block 4, all header and trailer blocks in the interchange schemas are marked as optional.</span></span> <span data-ttu-id="f41a1-122">这背离基本标头块 1 和 2 的应用程序标头块是必需的 SWIFT FIN 规范。</span><span class="sxs-lookup"><span data-stu-id="f41a1-122">This deviates from the SWIFT FIN specification, where the Basic Header block 1 and the Application Header block 2 are mandatory.</span></span> <span data-ttu-id="f41a1-123">这使您可以使用交换架构来处理不需要标头的消息。</span><span class="sxs-lookup"><span data-stu-id="f41a1-123">This enables you to use the interchange schema to handle messages that do not require headers.</span></span> <span data-ttu-id="f41a1-124">例如，如果接受通过 FileAct 接收的消息，批处理标头可能包含消息，以及常见的消息类型的源。</span><span class="sxs-lookup"><span data-stu-id="f41a1-124">For example, if you are accepting messages received through FileAct, the batch header may contain the source of the messages as well as a common message type.</span></span>  
  
 <span data-ttu-id="f41a1-125">运行时架构 DLL 还包括标头架构。</span><span class="sxs-lookup"><span data-stu-id="f41a1-125">The RunTime schema DLL also includes the header schema.</span></span> <span data-ttu-id="f41a1-126">A4SWIFT 安装部署的运行时架构 DLL 和 A4SWIFT 属性架构。</span><span class="sxs-lookup"><span data-stu-id="f41a1-126">A4SWIFT installation deploys the RunTime schema DLL and the A4SWIFT property schema.</span></span> <span data-ttu-id="f41a1-127">如果您需要使用你自己的标头进行处理，可以定义和部署自定义标头架构，并将升级消息解析为相应的属性。</span><span class="sxs-lookup"><span data-stu-id="f41a1-127">If you need to use your own header for processing, you can define and deploy a custom header schema, and promote the appropriate properties for message resolution.</span></span> <span data-ttu-id="f41a1-128">如果这样做，还需要指定到 SWIFT 反汇编程序 (DASM) 的新标头。</span><span class="sxs-lookup"><span data-stu-id="f41a1-128">If you do so, you will also need to specify the new header to the SWIFT disassembler (DASM).</span></span> <span data-ttu-id="f41a1-129">自定义标头架构不应具有 SWIFT 标头架构的文档类型相同的 A4SWIFT 安装已部署在运行时架构 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="f41a1-129">The custom header schema should not have the same Document Type as the SWIFT header schema that A4SWIFT installation has deployed in the RunTime schemas DLL.</span></span> <span data-ttu-id="f41a1-130">请务必更改架构命名空间或根节点名称。</span><span class="sxs-lookup"><span data-stu-id="f41a1-130">Be sure to change the schema namespace, or root node name, or both.</span></span>  
  
 <span data-ttu-id="f41a1-131">SWIFT 尾部架构 (**SWIFT Trailer.xsd**) 包含以下格式：</span><span class="sxs-lookup"><span data-stu-id="f41a1-131">The SWIFT Trailer schema (**SWIFT Trailer.xsd**) contains the format for the following:</span></span>  
  
- <span data-ttu-id="f41a1-132">结束的分隔符的文本块</span><span class="sxs-lookup"><span data-stu-id="f41a1-132">Ending delimiter of the text block</span></span>  
  
- <span data-ttu-id="f41a1-133">用户尾部 （用户和系统信息）</span><span class="sxs-lookup"><span data-stu-id="f41a1-133">User trailers (user and system information)</span></span>  
  
- <span data-ttu-id="f41a1-134">系统尾部</span><span class="sxs-lookup"><span data-stu-id="f41a1-134">System trailers</span></span>  
  
  <span data-ttu-id="f41a1-135">文本块的结束分隔符是"--}"。</span><span class="sxs-lookup"><span data-stu-id="f41a1-135">The ending delimiter of the text block is "-}".</span></span> <span data-ttu-id="f41a1-136">尾部块开头"{5:"。</span><span class="sxs-lookup"><span data-stu-id="f41a1-136">The trailer block begins with "{5:".</span></span> <span data-ttu-id="f41a1-137">尾部块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用，可能的重复消息等）。</span><span class="sxs-lookup"><span data-stu-id="f41a1-137">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on) and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="f41a1-138">添加的 SWIFT 尾部还提供第三个块中，分隔"{s:"。</span><span class="sxs-lookup"><span data-stu-id="f41a1-138">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="f41a1-139">*SWIFT 用户手册*，在"查找服务说明"下详细地介绍了块 5 的内容。</span><span class="sxs-lookup"><span data-stu-id="f41a1-139">The *SWIFT User Handbook*, under "FIN Service Description", describes in detail the contents of block 5.</span></span> <span data-ttu-id="f41a1-140">A4SWIFT 不会验证内容块 s。</span><span class="sxs-lookup"><span data-stu-id="f41a1-140">A4SWIFT does not validate the contents of block S.</span></span>  
  
  <span data-ttu-id="f41a1-141">实际 FIN 接口或 SWIFT 网络将追加尾部。</span><span class="sxs-lookup"><span data-stu-id="f41a1-141">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="f41a1-142">如果消息中包含尾部 A4SWIFT 接收消息时，A4SWIFT 携带消息尾部。</span><span class="sxs-lookup"><span data-stu-id="f41a1-142">If a message contains a trailer when A4SWIFT receives the message, A4SWIFT carries the trailer with the message.</span></span> <span data-ttu-id="f41a1-143">如果消息不包含尾部 A4SWIFT 接收消息时，A4SWIFT 不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="f41a1-143">A4SWIFT does not raise an error if a message does not contain a trailer when A4SWIFT receives the message.</span></span> <span data-ttu-id="f41a1-144">作为使用标头，所有尾部项，包括块本身是可选的 A4SWIFT 中。</span><span class="sxs-lookup"><span data-stu-id="f41a1-144">As with headers, all of the trailer entries, including the blocks themselves, are optional in A4SWIFT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41a1-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="f41a1-145">See Also</span></span>  
 [<span data-ttu-id="f41a1-146">处理架构</span><span class="sxs-lookup"><span data-stu-id="f41a1-146">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)