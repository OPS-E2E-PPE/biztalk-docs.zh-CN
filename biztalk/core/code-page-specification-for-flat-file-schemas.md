---
title: "代码页规范是平面文件架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d5cfbc960346e702ed0d4a39ca74bbc4b3634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="code-page-specification-for-flat-file-schemas"></a><span data-ttu-id="4cd88-102">平面文件架构的代码页规范</span><span class="sxs-lookup"><span data-stu-id="4cd88-102">Code Page Specification for Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="4cd88-103">概述</span><span class="sxs-lookup"><span data-stu-id="4cd88-103">Overview</span></span>
<span data-ttu-id="4cd88-104">中的值**代码页**属性用于创建反汇编和程序集的平面文件文档过程中使用的编码对象。</span><span class="sxs-lookup"><span data-stu-id="4cd88-104">The value in the **Code Page** property is used to create an encoding object that is used during the disassembly and assembly of flat file documents.</span></span> <span data-ttu-id="4cd88-105">此编码对象允许平面文件分析器要转换的入站平面文件文档本机编码为规范化的 utf-8 编码，供 Microsoft 内部使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4cd88-105">This encoding object allows the flat file parser to convert the native encoding of an inbound flat file document into the normalized UTF-8 encoding that is used internally by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4cd88-106">使用此编码对象，平面文件序列化程序还可以将内部 UTF-8 编码重新转换为平面文件文档的本机编码。</span><span class="sxs-lookup"><span data-stu-id="4cd88-106">The encoding object also allows the flat file serializer to convert the internal UTF-8 encoding back into the native encoding of the flat file document.</span></span>  
  
 <span data-ttu-id="4cd88-107">设置**代码页**属性在起着重要的是，但不是独占的作用确定你平面文件的业务文档所使用的字符编码方案。</span><span class="sxs-lookup"><span data-stu-id="4cd88-107">The setting of the **Code Page** property plays an important, but not exclusive, role in determining the character encoding scheme used by your flat file business documents.</span></span> <span data-ttu-id="4cd88-108">您必须考虑平面文件拆装器如何解释入站平面文件消息，以及在将出站消息转换为平面文件格式时平面文件组装器将如何对字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="4cd88-108">You must consider how inbound flat file messages are interpreted by the flat file disassembler as well as how the flat file assembler will encode characters as outbound messages are translated into flat file format.</span></span>  

## <a name="character-encoding"></a><span data-ttu-id="4cd88-109">字符编码</span><span class="sxs-lookup"><span data-stu-id="4cd88-109">Character encoding</span></span>  
 <span data-ttu-id="4cd88-110">在确定如何处理指定实例消息的字符编码时，有多种会影响处理方式的因素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4cd88-110">There are multiple factors that play a role in determining how character encoding for a given instance message is handled, as follows:</span></span>  
  
-   <span data-ttu-id="4cd88-111">在拆装平面文件实例消息时，使用以下算法来确定和保留编码信息：</span><span class="sxs-lookup"><span data-stu-id="4cd88-111">When disassembling a flat file instance message, the following algorithm is used to determine and preserve encoding information:</span></span>  
  
    1.  <span data-ttu-id="4cd88-112">如果**Charset**消息正文部分中，则使用它的值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-112">If the **Charset** in the Message body part is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="4cd88-113">否则为如果在信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-113">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    3.  <span data-ttu-id="4cd88-114">否则，如果存在字节顺序标记，则使用该标记的值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-114">Otherwise, if a byte order mark is present, its value is used.</span></span>  
  
    4.  <span data-ttu-id="4cd88-115">否则，假定为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="4cd88-115">Otherwise, assume UTF-8.</span></span>  
  
-   <span data-ttu-id="4cd88-116">装配时平面文件实例消息，以下算法用于确定要用于解码的字符集：</span><span class="sxs-lookup"><span data-stu-id="4cd88-116">When assembling a flat file instance message, the following algorithm is used to determine the character set to use for decoding:</span></span>  
  
-   <span data-ttu-id="4cd88-117">如果**XMLNorm.TargetCharset**消息上下文属性设置，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-117">If the **XMLNorm.TargetCharset** message context property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="4cd88-118">否则为如果**TargetCharset**汇编程序 （设计时） 属性设置，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-118">Otherwise, if the **TargetCharset** assembler (design-time) property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="4cd88-119">否则为如果在信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-119">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    1.  <span data-ttu-id="4cd88-120">否则为如果**SourceCharset**消息上下文属性设置，则使用其值。</span><span class="sxs-lookup"><span data-stu-id="4cd88-120">Otherwise, if the **SourceCharset** message context property is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="4cd88-121">否则，使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="4cd88-121">Otherwise, use UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd88-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd88-122">See Also</span></span>  
 <span data-ttu-id="4cd88-123">**注意事项时创建平面文件消息架构**和**代码页 （的平面文件架构的节点属性）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd88-123">**Considerations When Creating Flat File Message Schemas** and **Code Page (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>