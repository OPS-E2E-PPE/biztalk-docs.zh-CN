---
title: 平面文件组装器管道组件中的字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Assembler [pipeline component], character encoding
- IBaseMessagePart.Charset property
- pipeline components, Flat File Assembler
- Codepage property
- XMLNorm.SourceCharset property
- XMLNorm.TargetCharset property
- Target Charset property
ms.assetid: 0cf3c0fd-f036-4190-83ce-9064ef4e823c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47c1b85531a2efe13b91383a4bb5a8deb35b63e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986334"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="de78d-102">平面文件组装器管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="de78d-102">Character Encoding in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="de78d-103">平面文件组装器可以使用用户指定的字符编码生成消息。</span><span class="sxs-lookup"><span data-stu-id="de78d-103">The Flat File Assembler can produce messages in user-specified character encoding.</span></span> <span data-ttu-id="de78d-104">您可以在多个级别指定字符编码：</span><span class="sxs-lookup"><span data-stu-id="de78d-104">You can specify the character encoding at several levels:</span></span>  
  
- <span data-ttu-id="de78d-105">**架构。**</span><span class="sxs-lookup"><span data-stu-id="de78d-105">**Schema.**</span></span> <span data-ttu-id="de78d-106">设置**代码页**文档的平面文件架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="de78d-106">Set the **codepage** property in the flat file schema for the document.</span></span>  
  
- <span data-ttu-id="de78d-107">**组件。**</span><span class="sxs-lookup"><span data-stu-id="de78d-107">**Component.**</span></span> <span data-ttu-id="de78d-108">设置**目标字符集**管道设计器中的组件属性。</span><span class="sxs-lookup"><span data-stu-id="de78d-108">Set the **Target Charset** component property in Pipeline Designer.</span></span>  
  
- <span data-ttu-id="de78d-109">**消息。**</span><span class="sxs-lookup"><span data-stu-id="de78d-109">**Message.**</span></span> <span data-ttu-id="de78d-110">设置**XMLNorm.TargetCharset**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="de78d-110">Set the **XMLNorm.TargetCharset** property on the message context.</span></span>  
  
  <span data-ttu-id="de78d-111">对消息上下文设置的属性值将始终覆盖在管道设计器中设置的属性值。</span><span class="sxs-lookup"><span data-stu-id="de78d-111">The value of the property set on a message context always overrides the one set in Pipeline Designer.</span></span> <span data-ttu-id="de78d-112">此外，始终在管道设计器中设置的值将覆盖设置为值**代码页**平面文件文档架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="de78d-112">Also, the value set in Pipeline Designer always overwrites the value set as a **codepage** property in a flat file document schema.</span></span>  
  
  <span data-ttu-id="de78d-113">平面文件组装器使用以下算法来确定输出消息要使用的编码：</span><span class="sxs-lookup"><span data-stu-id="de78d-113">The Flat File Assembler uses the following algorithm to determine which encoding to use for an output message:</span></span>  
  
- <span data-ttu-id="de78d-114">如果**XMLNorm.TargetCharset**上下文属性设置，则其值用于编码。</span><span class="sxs-lookup"><span data-stu-id="de78d-114">If the **XMLNorm.TargetCharset** context property is set, its value is used for encoding.</span></span>  
  
- <span data-ttu-id="de78d-115">否则为如果**目标字符集**指定管道设计器中的属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="de78d-115">Otherwise, if the **Target charset** property in Pipeline Designer is specified, its value is used.</span></span>  
  
- <span data-ttu-id="de78d-116">否则为如果**代码页**指定平面文件架构中的属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="de78d-116">Otherwise, if the **codepage** property in the flat file schema is specified, its value is used.</span></span>  
  
- <span data-ttu-id="de78d-117">否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="de78d-117">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
- <span data-ttu-id="de78d-118">否则，将使用“UTF-8”。</span><span class="sxs-lookup"><span data-stu-id="de78d-118">Otherwise, "UTF-8" is used.</span></span> <span data-ttu-id="de78d-119">请注意，使用 UTF-8 编码时，平面文件组装器管道组件不会在传出消息上添加字节顺序标记。</span><span class="sxs-lookup"><span data-stu-id="de78d-119">Note that the Flat File Assembler pipeline component does not put byte order mark on outgoing messages when UTF-8 encoding is used.</span></span>  
  
  <span data-ttu-id="de78d-120">平面文件组装器将保存在中的 BizTalk 消息对象正文部分的信息进行编码**IBaseMessagePart.Charset**属性。</span><span class="sxs-lookup"><span data-stu-id="de78d-120">The Flat File Assembler saves encoding information on the body part of the BizTalk message object in the **IBaseMessagePart.Charset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de78d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="de78d-121">See Also</span></span>  
 <span data-ttu-id="de78d-122">[平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="de78d-122">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="de78d-123">[如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="de78d-123">[How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="de78d-124">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="de78d-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)