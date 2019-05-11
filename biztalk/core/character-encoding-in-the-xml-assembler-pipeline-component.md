---
title: XML 组装器管道组件中的字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, XML Assembler
- XMLNorm.TargetCharset property
- Target Charset property
- XML Assembler [pipeline component], character encoding
ms.assetid: c031fbbf-f00f-41ba-8ac9-cec7d625cef6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e01bbf7224da9abda8700721c1de3dd7efefb8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357480"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="bed00-102">XML 组装器管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="bed00-102">Character Encoding in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="bed00-103">下表中所示，XML 组装器管道组件可以产生用户指定的字符编码两种方式中的消息。</span><span class="sxs-lookup"><span data-stu-id="bed00-103">The XML Assembler pipeline component can produce messages in user-specified character encoding in two ways, as shown in the following table.</span></span>  
  
|<span data-ttu-id="bed00-104">编码级别</span><span class="sxs-lookup"><span data-stu-id="bed00-104">Encoding level</span></span>|<span data-ttu-id="bed00-105">编码方法</span><span class="sxs-lookup"><span data-stu-id="bed00-105">Encoding method</span></span>|  
|--------------------|---------------------|  
|<span data-ttu-id="bed00-106">组件</span><span class="sxs-lookup"><span data-stu-id="bed00-106">Component</span></span>|<span data-ttu-id="bed00-107">设置**目标字符集**管道设计器中的组件属性。</span><span class="sxs-lookup"><span data-stu-id="bed00-107">Set the **Target charset** component property in Pipeline Designer.</span></span>|  
|<span data-ttu-id="bed00-108">消息</span><span class="sxs-lookup"><span data-stu-id="bed00-108">Message</span></span>|<span data-ttu-id="bed00-109">设置**XMLNorm.TargetCharset**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="bed00-109">Set the **XMLNorm.TargetCharset** property on the message context.</span></span> <span data-ttu-id="bed00-110">**注意：** 消息上下文属性将始终覆盖在管道设计器中设置的任何上下文属性。</span><span class="sxs-lookup"><span data-stu-id="bed00-110">**Note:**  A message context property always overrides any context property set in Pipeline Designer.</span></span>|  
  
 <span data-ttu-id="bed00-111">XML 组装器使用以下算法来确定输出消息编码：</span><span class="sxs-lookup"><span data-stu-id="bed00-111">The XML Assembler uses the following algorithm to determine output message encoding:</span></span>  
  
1. <span data-ttu-id="bed00-112">如果**XMLNorm.TargetCharset**设置上下文属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="bed00-112">If the **XMLNorm.TargetCharset** context property is set, its value is used.</span></span>  
  
2. <span data-ttu-id="bed00-113">否则为如果**目标字符集**属性指定管道设计器中使用它的值。</span><span class="sxs-lookup"><span data-stu-id="bed00-113">Otherwise, if the **Target charset** property is specified in Pipeline Designer, its value is used.</span></span>  
  
3. <span data-ttu-id="bed00-114">否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="bed00-114">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
4. <span data-ttu-id="bed00-115">如果以上属性未设置，则使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="bed00-115">If none of the preceding properties is set, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="bed00-116">XML 组装器将 BizTalk 消息对象中的编码信息保存`IBaseMessagePart.Charset`属性。</span><span class="sxs-lookup"><span data-stu-id="bed00-116">The XML Assembler saves the encoding information of a BizTalk message object in the `IBaseMessagePart.Charset` property.</span></span> <span data-ttu-id="bed00-117">在使用 Unicode 或 utf-8 编码时，XML 组装器始终将字节顺序标记 (BOM) 添加到传出消息。</span><span class="sxs-lookup"><span data-stu-id="bed00-117">When using Unicode or UTF-8 encoding, the XML Assembler always adds the byte order mark (BOM) to outgoing messages.</span></span>  
  
   <span data-ttu-id="bed00-118">请注意，使用 XML 发送管道，其中包含 XML 组装器组件，默认值时生成的文档可能他们已提交到服务器，或可能如果创建的文档使用 utf-8 编码时使用字符集编码在服务器和**XMLNorm.TargetCharset**未指定。</span><span class="sxs-lookup"><span data-stu-id="bed00-118">Note that when using the default XML send pipeline, which contains the XML Assembler component, the produced documents may be encoded by using the same charset as when they were submitted into the server, or they may be encoded by using UTF-8 if documents were created within the server and **XMLNorm.TargetCharset** was not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed00-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bed00-119">See Also</span></span>  
 <span data-ttu-id="bed00-120">[XML 组装器管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="bed00-120">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="bed00-121">[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="bed00-121">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="bed00-122">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="bed00-122">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)