---
title: 不同类型的 BizTalk 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cabbfc889b4a07616012dc85c6763e1444ed8f43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351079"
---
# <a name="different-types-of-biztalk-schemas"></a><span data-ttu-id="20073-102">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="20073-102">Different Types of BizTalk Schemas</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="20073-103">支持以下四种类型的架构：</span><span class="sxs-lookup"><span data-stu-id="20073-103">supports the following four types of schemas:</span></span>  
  
- <span data-ttu-id="20073-104">**XML 架构**。</span><span class="sxs-lookup"><span data-stu-id="20073-104">**XML schema**.</span></span> <span data-ttu-id="20073-105">XML 架构定义 XML 实例消息的类的结构。</span><span class="sxs-lookup"><span data-stu-id="20073-105">An XML schema defines the structure of a class of XML instance messages.</span></span> <span data-ttu-id="20073-106">由于这种类型的架构使用 XML 架构定义 (XSD) 语言来定义 XML 实例消息的结构，这是 XSD 的预期的用途，此类架构使用 XSD 中一种简单方式。</span><span class="sxs-lookup"><span data-stu-id="20073-106">Because this type of schema uses XML Schema definition (XSD) language to define the structure of an XML instance message, and this is the intended purpose of XSD, such schemas use XSD in a straightforward way.</span></span>  
  
- <span data-ttu-id="20073-107">**平面文件架构**。</span><span class="sxs-lookup"><span data-stu-id="20073-107">**Flat file schema**.</span></span> <span data-ttu-id="20073-108">平面文件架构将定义使用平面文件格式，分隔或位置的实例消息或它们的某种组合的类的结构。</span><span class="sxs-lookup"><span data-stu-id="20073-108">A flat file schema defines the structure of a class of instance messages that use a flat file format, either delimited or positional or some combination thereof.</span></span> <span data-ttu-id="20073-109">由于 XSD 的本地语义功能不适应所有用于定义平面文件实例消息的结构要求 — 例如可能用于不同的记录和平面文件中的字段的分隔符的各种类型-BizTalk Server 使用 XSD 的批注功能来存储此 XSD 架构中的附加信息。</span><span class="sxs-lookup"><span data-stu-id="20073-109">Because the native semantic capabilities of XSD do not accommodate all of the requirements for defining the structure of flat file instance messages—such as the various types of delimiters that might be used for different records and fields within the flat file—BizTalk Server uses the annotation capabilities of XSD to store this extra information within an XSD schema.</span></span> <span data-ttu-id="20073-110">BizTalk Server 定义一组丰富的特定批注标记，可用于存储所有所需的其他信息。</span><span class="sxs-lookup"><span data-stu-id="20073-110">BizTalk Server defines a rich set of specific annotation tags that can be used to store all of the required additional information.</span></span>  
  
- <span data-ttu-id="20073-111">**信封架构**。</span><span class="sxs-lookup"><span data-stu-id="20073-111">**Envelope schema**.</span></span> <span data-ttu-id="20073-112">信封架构是一种特殊的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="20073-112">An envelope schema is a special type of XML schema.</span></span> <span data-ttu-id="20073-113">信封架构用于定义 XML 信封，用于将一个或多个 XML 业务文档包装到单个 XML 实例消息的结构。</span><span class="sxs-lookup"><span data-stu-id="20073-113">Envelope schemas are used to define the structure of XML envelopes, which are used to wrap one or more XML business documents into a single XML instance message.</span></span> <span data-ttu-id="20073-114">在定义为信封架构的 XML 架构时，所需的几个其他属性设置，具体取决于有信封架构中定义的多个根记录。</span><span class="sxs-lookup"><span data-stu-id="20073-114">When you define an XML schema to be an envelope schema, a couple of additional property settings are required, depending on such factors as whether there are more than one root record defined in the envelope schema.</span></span>  
  
- <span data-ttu-id="20073-115">**属性架构**。</span><span class="sxs-lookup"><span data-stu-id="20073-115">**Property schema**.</span></span> <span data-ttu-id="20073-116">属性架构要结合 BizTalk Server 中存在的称为属性升级的两个机制之一。</span><span class="sxs-lookup"><span data-stu-id="20073-116">A property schema is used with one of the two mechanisms that exist within BizTalk Server for what is known as property promotion.</span></span> <span data-ttu-id="20073-117">属性升级是将特定的值从实例消息的深层复制到消息上下文的过程。</span><span class="sxs-lookup"><span data-stu-id="20073-117">Property promotion is the process of copying specific values from deep within an instance message to the message context.</span></span> <span data-ttu-id="20073-118">从消息上下文中，更轻松地通过各种 BizTalk Server 组件访问这些值。</span><span class="sxs-lookup"><span data-stu-id="20073-118">From the message context, these values are more easily accessed by various BizTalk Server components.</span></span> <span data-ttu-id="20073-119">这些组件使用的值来执行操作，例如消息路由。</span><span class="sxs-lookup"><span data-stu-id="20073-119">These components use the values to perform actions such as message routing.</span></span> <span data-ttu-id="20073-120">升级的属性值还可以复制另一个方向，从恢复到的实例消息中，可更轻松地访问消息上下文中的实例消息发送到其目标之前。</span><span class="sxs-lookup"><span data-stu-id="20073-120">Promoted property values can also be copied in the other direction, from the more easily accessible message context back into the depths of the instance message, just before the instance message is sent to its destination.</span></span> <span data-ttu-id="20073-121">属性架构是 BizTalk 架构所扮演的角色过程中复制的实例消息和消息上下文之间来回升级的属性的简单版本。</span><span class="sxs-lookup"><span data-stu-id="20073-121">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span>  
  
  <span data-ttu-id="20073-122">部分的其余部分提供有关 BizTalk Server 中的架构这四种类型的其他信息。</span><span class="sxs-lookup"><span data-stu-id="20073-122">The remainder of section provides additional information about these four types of schemas in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20073-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="20073-123">In This Section</span></span>  
  
-   [<span data-ttu-id="20073-124">XML 架构</span><span class="sxs-lookup"><span data-stu-id="20073-124">XML Schemas</span></span>](../core/xml-schemas.md)  
  
-   [<span data-ttu-id="20073-125">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="20073-125">Flat File Schemas</span></span>](../core/flat-file-schemas.md)  
  
-   [<span data-ttu-id="20073-126">信封架构</span><span class="sxs-lookup"><span data-stu-id="20073-126">Envelope Schemas</span></span>](../core/envelope-schemas.md)  
  
-   [<span data-ttu-id="20073-127">属性架构</span><span class="sxs-lookup"><span data-stu-id="20073-127">Property Schemas</span></span>](../core/property-schemas.md)