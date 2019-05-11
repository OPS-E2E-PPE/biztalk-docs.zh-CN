---
title: 如何配置平面文件组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], configuring
- messages, flat files
ms.assetid: 5af61bba-4eb2-4bb9-a655-394a76d08d3b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0db8ce0e52ec4dfc5368f172747dc51ef7704626
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340868"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="763ca-102">如何配置平面文件组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="763ca-102">How to Configure the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="763ca-103">平面文件组装器管道组件用于将其发送占服务器之前序列化为分隔或位置平面文件格式的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="763ca-103">The Flat File Assembler pipeline component is used to serialize an XML document into delimited or positional flat file format before sending it out of the server.</span></span>  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="763ca-104">若要配置平面文件组装器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="763ca-104">To configure the properties for the Flat File Assembler pipeline component</span></span>  
  
1.  <span data-ttu-id="763ca-105">将平面文件组装器管道组件拖至发送管道的组装阶段。</span><span class="sxs-lookup"><span data-stu-id="763ca-105">Drag the Flat File Assembler pipeline component into the Assemble stage of the send pipeline.</span></span>  
  
2.  <span data-ttu-id="763ca-106">在属性窗口中**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="763ca-106">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="763ca-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="763ca-107">Use this</span></span>|<span data-ttu-id="763ca-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="763ca-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="763ca-109">**文档架构**</span><span class="sxs-lookup"><span data-stu-id="763ca-109">**Document schema**</span></span>|<span data-ttu-id="763ca-110">选择要用于序列化到平面文件格式从 XML 消息的平面文件文档架构。</span><span class="sxs-lookup"><span data-stu-id="763ca-110">Select a flat file document schema to use for serializing the message from XML to the flat file format.</span></span> <span data-ttu-id="763ca-111">如果不指定任何架构，进行运行时架构发现。</span><span class="sxs-lookup"><span data-stu-id="763ca-111">If no schema is specified, run-time schema discovery is done.</span></span> <span data-ttu-id="763ca-112">您可以在 BizTalk 编辑器创建平面文件文档架构。</span><span class="sxs-lookup"><span data-stu-id="763ca-112">You can create the flat file document schema in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="763ca-113">默认值：None</span><span class="sxs-lookup"><span data-stu-id="763ca-113">Default value: None</span></span>|  
    |<span data-ttu-id="763ca-114">**标头架构**</span><span class="sxs-lookup"><span data-stu-id="763ca-114">**Header schema**</span></span>|<span data-ttu-id="763ca-115">选择平面文件消息的头部部分的架构。</span><span class="sxs-lookup"><span data-stu-id="763ca-115">Select a schema for the header part of the flat file message.</span></span> <span data-ttu-id="763ca-116">此外可以在名为消息上下文属性中指定的标头架构**HeaderSpecName** xmlnorm 命名空间下。</span><span class="sxs-lookup"><span data-stu-id="763ca-116">A header schema can also be specified in the message context property named **HeaderSpecName** under the xmlnorm namespace.</span></span> <span data-ttu-id="763ca-117">在这种情况下，它将覆盖在管道设计器中指定的标头架构。</span><span class="sxs-lookup"><span data-stu-id="763ca-117">In this case, it will override the header schema specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="763ca-118">您可以使用 BizTalk 编辑器创建平面文件消息的标头部分的架构。</span><span class="sxs-lookup"><span data-stu-id="763ca-118">You can create the schema for the header part of the flat file message with BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="763ca-119">默认值：None</span><span class="sxs-lookup"><span data-stu-id="763ca-119">Default value: None</span></span>|  
    |<span data-ttu-id="763ca-120">**保留字节顺序标记**</span><span class="sxs-lookup"><span data-stu-id="763ca-120">**Preserve byte order mark**</span></span>|<span data-ttu-id="763ca-121">指定是否添加字节顺序标记 (BOM) 到组装器组件生成的文档。</span><span class="sxs-lookup"><span data-stu-id="763ca-121">Specifies whether to add a byte order mark (BOM) to the document produced by the assembler component.</span></span><br /><br /> <span data-ttu-id="763ca-122">默认值：**False**</span><span class="sxs-lookup"><span data-stu-id="763ca-122">Default Value: **False**</span></span>|  
    |<span data-ttu-id="763ca-123">**目标字符集**</span><span class="sxs-lookup"><span data-stu-id="763ca-123">**Target charset**</span></span>|<span data-ttu-id="763ca-124">指定用于编码的传出消息的目标字符集。</span><span class="sxs-lookup"><span data-stu-id="763ca-124">Specifies the target character set used for encoding of outgoing messages.</span></span><br /><br /> <span data-ttu-id="763ca-125">默认值：None</span><span class="sxs-lookup"><span data-stu-id="763ca-125">Default value: None</span></span>|  
    |<span data-ttu-id="763ca-126">**尾部架构**</span><span class="sxs-lookup"><span data-stu-id="763ca-126">**Trailer schema**</span></span>|<span data-ttu-id="763ca-127">选择平面文件消息的尾部部分架构。</span><span class="sxs-lookup"><span data-stu-id="763ca-127">Select a schema for the trailer part of the flat file message.</span></span> <span data-ttu-id="763ca-128">您可以创建用于平面文件消息尾部部分的架构在 BizTalk 编辑器中。</span><span class="sxs-lookup"><span data-stu-id="763ca-128">You can create the schema for the trailer part of the flat file message in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="763ca-129">默认值：None</span><span class="sxs-lookup"><span data-stu-id="763ca-129">Default value: None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="763ca-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="763ca-130">See Also</span></span>  
 <span data-ttu-id="763ca-131">[平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="763ca-131">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="763ca-132">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="763ca-132">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="763ca-133">[XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="763ca-133">[XML and Flat File Property Schema and Properties](../core/xml-and-flat-file-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="763ca-134">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="763ca-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)