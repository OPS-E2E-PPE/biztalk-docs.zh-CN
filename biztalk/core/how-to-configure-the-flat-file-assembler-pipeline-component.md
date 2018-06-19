---
title: 如何配置平面文件汇编管道组件 |Microsoft 文档
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
ms.openlocfilehash: 7fe9c7a0720db68d8e629410dd3f0a443a99d7a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248629"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="7645e-102">如何配置平面文件汇编管道组件</span><span class="sxs-lookup"><span data-stu-id="7645e-102">How to Configure the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="7645e-103">平面文件组装器管道组件用于在将 XML 文档发出服务器之前将其序列化为分隔的平面文件格式或位置平面文件格式。</span><span class="sxs-lookup"><span data-stu-id="7645e-103">The Flat File Assembler pipeline component is used to serialize an XML document into delimited or positional flat file format before sending it out of the server.</span></span>  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="7645e-104">若要配置平面文件汇编器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="7645e-104">To configure the properties for the Flat File Assembler pipeline component</span></span>  
  
1.  <span data-ttu-id="7645e-105">将平面文件组装器管道组件拖至发送管道的组装阶段中。</span><span class="sxs-lookup"><span data-stu-id="7645e-105">Drag the Flat File Assembler pipeline component into the Assemble stage of the send pipeline.</span></span>  
  
2.  <span data-ttu-id="7645e-106">在属性窗口中，在**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="7645e-106">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="7645e-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7645e-107">Use this</span></span>|<span data-ttu-id="7645e-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7645e-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7645e-109">**文档架构**</span><span class="sxs-lookup"><span data-stu-id="7645e-109">**Document schema**</span></span>|<span data-ttu-id="7645e-110">选择用于将消息从 XML 格式序列化为平面文件格式的平面文件文档架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-110">Select a flat file document schema to use for serializing the message from XML to the flat file format.</span></span> <span data-ttu-id="7645e-111">如果未指定任何架构，则会执行运行时架构发现操作。</span><span class="sxs-lookup"><span data-stu-id="7645e-111">If no schema is specified, run-time schema discovery is done.</span></span> <span data-ttu-id="7645e-112">可以在 BizTalk 编辑器中创建平面文件文档架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-112">You can create the flat file document schema in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="7645e-113">默认值： 无</span><span class="sxs-lookup"><span data-stu-id="7645e-113">Default value: None</span></span>|  
    |<span data-ttu-id="7645e-114">**标头架构**</span><span class="sxs-lookup"><span data-stu-id="7645e-114">**Header schema**</span></span>|<span data-ttu-id="7645e-115">为平面文件消息的头部部分选择架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-115">Select a schema for the header part of the flat file message.</span></span> <span data-ttu-id="7645e-116">此外可以在名为消息上下文属性中指定标头架构**HeaderSpecName** xmlnorm 命名空间下。</span><span class="sxs-lookup"><span data-stu-id="7645e-116">A header schema can also be specified in the message context property named **HeaderSpecName** under the xmlnorm namespace.</span></span> <span data-ttu-id="7645e-117">在这种情况下，该架构将会覆盖在管道设计器中指定的头部架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-117">In this case, it will override the header schema specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="7645e-118">可以使用 BizTalk 编辑器来为平面文件消息的头部部分创建架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-118">You can create the schema for the header part of the flat file message with BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="7645e-119">默认值： 无</span><span class="sxs-lookup"><span data-stu-id="7645e-119">Default value: None</span></span>|  
    |<span data-ttu-id="7645e-120">**保留字节顺序标记**</span><span class="sxs-lookup"><span data-stu-id="7645e-120">**Preserve byte order mark**</span></span>|<span data-ttu-id="7645e-121">指定是否将一个字节顺序标记 (BOM 到汇编程序组件生成的文档)。</span><span class="sxs-lookup"><span data-stu-id="7645e-121">Specifies whether to add a byte order mark (BOM) to the document produced by the assembler component.</span></span><br /><br /> <span data-ttu-id="7645e-122">默认值： **False**</span><span class="sxs-lookup"><span data-stu-id="7645e-122">Default Value: **False**</span></span>|  
    |<span data-ttu-id="7645e-123">**目标 charset**</span><span class="sxs-lookup"><span data-stu-id="7645e-123">**Target charset**</span></span>|<span data-ttu-id="7645e-124">指定用于传出消息编码的目标字符集。</span><span class="sxs-lookup"><span data-stu-id="7645e-124">Specifies the target character set used for encoding of outgoing messages.</span></span><br /><br /> <span data-ttu-id="7645e-125">默认值： 无</span><span class="sxs-lookup"><span data-stu-id="7645e-125">Default value: None</span></span>|  
    |<span data-ttu-id="7645e-126">**尾部架构**</span><span class="sxs-lookup"><span data-stu-id="7645e-126">**Trailer schema**</span></span>|<span data-ttu-id="7645e-127">为平面文件消息的尾部部分选择架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-127">Select a schema for the trailer part of the flat file message.</span></span> <span data-ttu-id="7645e-128">可以在 BizTalk 编辑器中为平面文件消息的尾部部分创建架构。</span><span class="sxs-lookup"><span data-stu-id="7645e-128">You can create the schema for the trailer part of the flat file message in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="7645e-129">默认值： 无</span><span class="sxs-lookup"><span data-stu-id="7645e-129">Default value: None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7645e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7645e-130">See Also</span></span>  
 <span data-ttu-id="7645e-131">[平面文件汇编管道组件](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7645e-131">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="7645e-132">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="7645e-132">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="7645e-133">[XML、 平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7645e-133">[XML and Flat File Property Schema and Properties](../core/xml-and-flat-file-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="7645e-134">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="7645e-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)