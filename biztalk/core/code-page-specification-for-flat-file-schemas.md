---
title: 代码页规范平面文件架构的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0ba2c19c3fc02ff0a72fcd8e93ec9f4b112996
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357176"
---
# <a name="code-page-specification-for-flat-file-schemas"></a><span data-ttu-id="565ad-102">平面文件架构的代码页规范</span><span class="sxs-lookup"><span data-stu-id="565ad-102">Code Page Specification for Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="565ad-103">概述</span><span class="sxs-lookup"><span data-stu-id="565ad-103">Overview</span></span>
<span data-ttu-id="565ad-104">中的值**代码页**属性用于创建在拆装和组装平面文件文档过程中使用的编码对象。</span><span class="sxs-lookup"><span data-stu-id="565ad-104">The value in the **Code Page** property is used to create an encoding object that is used during the disassembly and assembly of flat file documents.</span></span> <span data-ttu-id="565ad-105">此编码对象，平面文件分析器将转换为规范化 utf-8 编码的本机编码的入站平面文件文档由 Microsoft 在内部使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="565ad-105">This encoding object allows the flat file parser to convert the native encoding of an inbound flat file document into the normalized UTF-8 encoding that is used internally by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="565ad-106">编码的对象还允许将转换回本机编码的平面文件文档的内部 utf-8 编码的平面文件序列化程序。</span><span class="sxs-lookup"><span data-stu-id="565ad-106">The encoding object also allows the flat file serializer to convert the internal UTF-8 encoding back into the native encoding of the flat file document.</span></span>  
  
 <span data-ttu-id="565ad-107">设置**代码页**属性起着重要的是，但并非唯一作用在确定您的平面文件业务文档使用的字符编码方案。</span><span class="sxs-lookup"><span data-stu-id="565ad-107">The setting of the **Code Page** property plays an important, but not exclusive, role in determining the character encoding scheme used by your flat file business documents.</span></span> <span data-ttu-id="565ad-108">您必须考虑如何在平面文件组装器将对字符进行编码的出站消息转换为平面文件格式，平面文件拆装器将解释消息的入站平面文件。</span><span class="sxs-lookup"><span data-stu-id="565ad-108">You must consider how inbound flat file messages are interpreted by the flat file disassembler as well as how the flat file assembler will encode characters as outbound messages are translated into flat file format.</span></span>  

## <a name="character-encoding"></a><span data-ttu-id="565ad-109">字符编码</span><span class="sxs-lookup"><span data-stu-id="565ad-109">Character encoding</span></span>  
 <span data-ttu-id="565ad-110">有在确定如何为给定的实例消息的字符编码处理，按如下所示发挥作用的多个因素：</span><span class="sxs-lookup"><span data-stu-id="565ad-110">There are multiple factors that play a role in determining how character encoding for a given instance message is handled, as follows:</span></span>  
  
-   <span data-ttu-id="565ad-111">在拆装平面文件实例消息，使用以下算法来确定和保留编码信息：</span><span class="sxs-lookup"><span data-stu-id="565ad-111">When disassembling a flat file instance message, the following algorithm is used to determine and preserve encoding information:</span></span>  
  
    1.  <span data-ttu-id="565ad-112">如果**Charset**消息正文部分中，则使用它的值。</span><span class="sxs-lookup"><span data-stu-id="565ad-112">If the **Charset** in the Message body part is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="565ad-113">否则为如果信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。</span><span class="sxs-lookup"><span data-stu-id="565ad-113">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    3.  <span data-ttu-id="565ad-114">否则，如果存在字节顺序标记，则使用它的值。</span><span class="sxs-lookup"><span data-stu-id="565ad-114">Otherwise, if a byte order mark is present, its value is used.</span></span>  
  
    4.  <span data-ttu-id="565ad-115">否则，假定 utf-8。</span><span class="sxs-lookup"><span data-stu-id="565ad-115">Otherwise, assume UTF-8.</span></span>  
  
-   <span data-ttu-id="565ad-116">在组装平面文件实例消息，使用以下算法来确定要用于解码的字符集：</span><span class="sxs-lookup"><span data-stu-id="565ad-116">When assembling a flat file instance message, the following algorithm is used to determine the character set to use for decoding:</span></span>  
  
-   <span data-ttu-id="565ad-117">如果**XMLNorm.TargetCharset**消息上下文属性设置，则使用的值。</span><span class="sxs-lookup"><span data-stu-id="565ad-117">If the **XMLNorm.TargetCharset** message context property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="565ad-118">否则为如果**TargetCharset**组装器 （设计时） 属性设置，则使用的值。</span><span class="sxs-lookup"><span data-stu-id="565ad-118">Otherwise, if the **TargetCharset** assembler (design-time) property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="565ad-119">否则为如果信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。</span><span class="sxs-lookup"><span data-stu-id="565ad-119">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    1.  <span data-ttu-id="565ad-120">否则为如果**SourceCharset**消息上下文属性设置，则使用的值。</span><span class="sxs-lookup"><span data-stu-id="565ad-120">Otherwise, if the **SourceCharset** message context property is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="565ad-121">否则，使用 utf-8。</span><span class="sxs-lookup"><span data-stu-id="565ad-121">Otherwise, use UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565ad-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="565ad-122">See Also</span></span>  
 <span data-ttu-id="565ad-123">**考虑事项时创建平面文件消息架构**和**代码页 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="565ad-123">**Considerations When Creating Flat File Message Schemas** and **Code Page (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>