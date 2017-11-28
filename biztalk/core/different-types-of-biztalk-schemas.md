---
title: "不同类型的 BizTalk 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051cd8fb9824cece316ea6f56e318490eacf88c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="different-types-of-biztalk-schemas"></a><span data-ttu-id="ce7cd-102">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="ce7cd-102">Different Types of BizTalk Schemas</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ce7cd-103">支持以下四种类型的架构：</span><span class="sxs-lookup"><span data-stu-id="ce7cd-103"> supports the following four types of schemas:</span></span>  
  
-   <span data-ttu-id="ce7cd-104">**XML 架构**。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-104">**XML schema**.</span></span> <span data-ttu-id="ce7cd-105">XML 架构用于定义 XML 实例消息类的结构。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-105">An XML schema defines the structure of a class of XML instance messages.</span></span> <span data-ttu-id="ce7cd-106">由于此类架构使用 XML 架构定义 (XSD) 语言来定义 XML 实例消息的结构，并且 XSD 也专门用于此目的，因此这类架构以一种简便方式使用 XSD。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-106">Because this type of schema uses XML Schema definition (XSD) language to define the structure of an XML instance message, and this is the intended purpose of XSD, such schemas use XSD in a straightforward way.</span></span>  
  
-   <span data-ttu-id="ce7cd-107">**平面文件架构**。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-107">**Flat file schema**.</span></span> <span data-ttu-id="ce7cd-108">平面文件架构用于定义使用平面文件格式的实例消息类的结构，可以是分隔格式或位置格式，或者是两种格式的组合。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-108">A flat file schema defines the structure of a class of instance messages that use a flat file format, either delimited or positional or some combination thereof.</span></span> <span data-ttu-id="ce7cd-109">因为 XSD 的本机语义功能不适应所有定义的平面文件实例消息结构的要求，如可能用于不同的记录和平面文件中的字段的分隔符的各种类型-BizTalk Server 使用 XSD 的批注功能来存储在 XSD 架构中的此额外信息。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-109">Because the native semantic capabilities of XSD do not accommodate all of the requirements for defining the structure of flat file instance messages—such as the various types of delimiters that might be used for different records and fields within the flat file—BizTalk Server uses the annotation capabilities of XSD to store this extra information within an XSD schema.</span></span> <span data-ttu-id="ce7cd-110">BizTalk Server 定义了一组丰富的特定批注标记，可用于存储所需的所有其他信息。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-110">BizTalk Server defines a rich set of specific annotation tags that can be used to store all of the required additional information.</span></span>  
  
-   <span data-ttu-id="ce7cd-111">**信封架构**。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-111">**Envelope schema**.</span></span> <span data-ttu-id="ce7cd-112">信封架构是一种特殊类型的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-112">An envelope schema is a special type of XML schema.</span></span> <span data-ttu-id="ce7cd-113">信封架构用于定义 XML 信封的结构，以用于将一个或多个 XML 业务文档包装到单个 XML 实例消息中。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-113">Envelope schemas are used to define the structure of XML envelopes, which are used to wrap one or more XML business documents into a single XML instance message.</span></span> <span data-ttu-id="ce7cd-114">在将 XML 架构定义为信封架构时，根据是否在信封架构中定义了多个根记录，可能需要其他一些属性设置。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-114">When you define an XML schema to be an envelope schema, a couple of additional property settings are required, depending on such factors as whether there are more than one root record defined in the envelope schema.</span></span>  
  
-   <span data-ttu-id="ce7cd-115">**属性架构**。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-115">**Property schema**.</span></span> <span data-ttu-id="ce7cd-116">属性架构要结合 BizTalk Server 中存在的称为属性升级的两种机制之一来使用。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-116">A property schema is used with one of the two mechanisms that exist within BizTalk Server for what is known as property promotion.</span></span> <span data-ttu-id="ce7cd-117">属性升级是将特定的值从实例消息的深层复制到消息上下文的过程。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-117">Property promotion is the process of copying specific values from deep within an instance message to the message context.</span></span> <span data-ttu-id="ce7cd-118">这样，各种 BizTalk Server 组件可以更容易地从消息上下文访问这些值。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-118">From the message context, these values are more easily accessed by various BizTalk Server components.</span></span> <span data-ttu-id="ce7cd-119">这些组件使用这些值来执行诸如消息路由之类的各种操作。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-119">These components use the values to perform actions such as message routing.</span></span> <span data-ttu-id="ce7cd-120">您也可以按其他方向复制升级的属性值，例如，在实例消息发送到其目标之前，将其从更易于访问的消息上下文复制回实例消息的深层。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-120">Promoted property values can also be copied in the other direction, from the more easily accessible message context back into the depths of the instance message, just before the instance message is sent to its destination.</span></span> <span data-ttu-id="ce7cd-121">属性架构是 BizTalk 架构的简化版本，它在实例消息和消息上下文之间来回复制升级属性的过程中起到一定作用。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-121">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span>  
  
 <span data-ttu-id="ce7cd-122">本主题的其余部分介绍有关 BizTalk Server 中这四种类型架构的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ce7cd-122">The remainder of section provides additional information about these four types of schemas in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce7cd-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="ce7cd-123">In This Section</span></span>  
  
-   [<span data-ttu-id="ce7cd-124">XML 架构</span><span class="sxs-lookup"><span data-stu-id="ce7cd-124">XML Schemas</span></span>](../core/xml-schemas.md)  
  
-   [<span data-ttu-id="ce7cd-125">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="ce7cd-125">Flat File Schemas</span></span>](../core/flat-file-schemas.md)  
  
-   [<span data-ttu-id="ce7cd-126">信封架构</span><span class="sxs-lookup"><span data-stu-id="ce7cd-126">Envelope Schemas</span></span>](../core/envelope-schemas.md)  
  
-   [<span data-ttu-id="ce7cd-127">属性架构</span><span class="sxs-lookup"><span data-stu-id="ce7cd-127">Property Schemas</span></span>](../core/property-schemas.md)