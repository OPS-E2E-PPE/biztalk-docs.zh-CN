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
ms.openlocfilehash: 6b97a92ed1dd842f6b65b49d1c312ffd84eb8dac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357481"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="70559-102">平面文件组装器管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="70559-102">Character Encoding in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="70559-103">平面文件组装器可以生成用户指定的字符编码的消息。</span><span class="sxs-lookup"><span data-stu-id="70559-103">The Flat File Assembler can produce messages in user-specified character encoding.</span></span> <span data-ttu-id="70559-104">您可以指定在多个级别的字符编码：</span><span class="sxs-lookup"><span data-stu-id="70559-104">You can specify the character encoding at several levels:</span></span>  
  
- <span data-ttu-id="70559-105">**架构。**</span><span class="sxs-lookup"><span data-stu-id="70559-105">**Schema.**</span></span> <span data-ttu-id="70559-106">设置**代码页**文档的平面文件架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="70559-106">Set the **codepage** property in the flat file schema for the document.</span></span>  
  
- <span data-ttu-id="70559-107">**组件。**</span><span class="sxs-lookup"><span data-stu-id="70559-107">**Component.**</span></span> <span data-ttu-id="70559-108">设置**目标字符集**管道设计器中的组件属性。</span><span class="sxs-lookup"><span data-stu-id="70559-108">Set the **Target Charset** component property in Pipeline Designer.</span></span>  
  
- <span data-ttu-id="70559-109">**消息。**</span><span class="sxs-lookup"><span data-stu-id="70559-109">**Message.**</span></span> <span data-ttu-id="70559-110">设置**XMLNorm.TargetCharset**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="70559-110">Set the **XMLNorm.TargetCharset** property on the message context.</span></span>  
  
  <span data-ttu-id="70559-111">始终在消息上下文上设置的属性的值将覆盖在管道设计器中的一个集。</span><span class="sxs-lookup"><span data-stu-id="70559-111">The value of the property set on a message context always overrides the one set in Pipeline Designer.</span></span> <span data-ttu-id="70559-112">此外，始终在管道设计器中设置的值将覆盖设置为值**代码页**平面文件文档架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="70559-112">Also, the value set in Pipeline Designer always overwrites the value set as a **codepage** property in a flat file document schema.</span></span>  
  
  <span data-ttu-id="70559-113">平面文件组装器使用以下算法来确定要用于输出消息的编码：</span><span class="sxs-lookup"><span data-stu-id="70559-113">The Flat File Assembler uses the following algorithm to determine which encoding to use for an output message:</span></span>  
  
- <span data-ttu-id="70559-114">如果**XMLNorm.TargetCharset**上下文属性设置，则其值用于编码。</span><span class="sxs-lookup"><span data-stu-id="70559-114">If the **XMLNorm.TargetCharset** context property is set, its value is used for encoding.</span></span>  
  
- <span data-ttu-id="70559-115">否则为如果**目标字符集**指定管道设计器中的属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="70559-115">Otherwise, if the **Target charset** property in Pipeline Designer is specified, its value is used.</span></span>  
  
- <span data-ttu-id="70559-116">否则为如果**代码页**指定平面文件架构中的属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="70559-116">Otherwise, if the **codepage** property in the flat file schema is specified, its value is used.</span></span>  
  
- <span data-ttu-id="70559-117">否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="70559-117">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
- <span data-ttu-id="70559-118">否则，使用"utf-8"。</span><span class="sxs-lookup"><span data-stu-id="70559-118">Otherwise, "UTF-8" is used.</span></span> <span data-ttu-id="70559-119">请注意，平面文件组装器管道组件不会将字节顺序标记对传出消息时使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="70559-119">Note that the Flat File Assembler pipeline component does not put byte order mark on outgoing messages when UTF-8 encoding is used.</span></span>  
  
  <span data-ttu-id="70559-120">平面文件组装器将保存在中的 BizTalk 消息对象正文部分的信息进行编码**IBaseMessagePart.Charset**属性。</span><span class="sxs-lookup"><span data-stu-id="70559-120">The Flat File Assembler saves encoding information on the body part of the BizTalk message object in the **IBaseMessagePart.Charset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70559-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="70559-121">See Also</span></span>  
 <span data-ttu-id="70559-122">[平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="70559-122">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="70559-123">[如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="70559-123">[How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="70559-124">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="70559-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)