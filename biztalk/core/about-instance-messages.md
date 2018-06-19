---
title: 有关实例消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de7fc3d3-57a7-4df9-b981-127e21941e22
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf956fb9f201697ac8c2b7da2135e469e03de55e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224773"
---
# <a name="about-instance-messages"></a><span data-ttu-id="07017-102">有关实例消息</span><span class="sxs-lookup"><span data-stu-id="07017-102">About Instance Messages</span></span>
<span data-ttu-id="07017-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收实例消息，每个实例消息通常表示诸如采购订单之类的一个或多个业务文档。</span><span class="sxs-lookup"><span data-stu-id="07017-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends and receives instance messages, each of which typically represents one or more business documents such as a purchase order.</span></span> <span data-ttu-id="07017-104">实例消息是由一个或多个架构定义的消息结构的实例。</span><span class="sxs-lookup"><span data-stu-id="07017-104">An instance message is an instance of a message structure defined by one or more schemas.</span></span> <span data-ttu-id="07017-105">一个架构或者一起使用的一组架构将定义有效实例消息的组成部分。</span><span class="sxs-lookup"><span data-stu-id="07017-105">A schema, or a set of schemas being used together, defines what constitutes a valid instance message.</span></span> <span data-ttu-id="07017-106">例如，采购订单可能定义为在其中具有若干记录（如 ShipTo 记录、BillTo 记录和 Items 记录等）。</span><span class="sxs-lookup"><span data-stu-id="07017-106">For example, a purchase order might be defined to have several records within it, such as a ShipTo record, a BillTo record, an Items record, and so on.</span></span> <span data-ttu-id="07017-107">这些记录中的每一个都可以定义为包含它们自己的子记录和字段。</span><span class="sxs-lookup"><span data-stu-id="07017-107">Each of these records can be defined to contain their own subrecords and fields.</span></span> <span data-ttu-id="07017-108">相应的架构定义这些记录和字段的潜在内容，相应的实例消息包含实际采购订单，这些采购订单又包含根据架构组织的采购订单数据。</span><span class="sxs-lookup"><span data-stu-id="07017-108">The corresponding schema defines the potential contents of these records and fields and the corresponding instance messages contain actual purchase orders that contain purchase order data structured according to the schema.</span></span>  
  
 <span data-ttu-id="07017-109">BizTalk Server 可以通过可扩展的各种格式发送和接收实例消息，但 XML 格式具有特别意义，因为所有消息格式都翻译为该格式以供内部处理。</span><span class="sxs-lookup"><span data-stu-id="07017-109">BizTalk Server can send and receive instance messages in an extensible variety of formats although one format, XML, has special significance as the format into which all message formats are translated for internal processing.</span></span> <span data-ttu-id="07017-110">特定的 XML 文档使用定义好的一组开始和结束标记（按层次结构排列）来组织消息中的数据，确定一个数据项结束、另一个数据项开始的位置。</span><span class="sxs-lookup"><span data-stu-id="07017-110">A particular XML document uses a well-defined set of starting and ending tags, arranged hierarchically, to organize the data within the message and determine where one data item ends and another begins.</span></span> <span data-ttu-id="07017-111">一个或多个相应 XML 架构将定义可在其他标记内使用的标记及其使用顺序，从而控制一致性消息的结构。</span><span class="sxs-lookup"><span data-stu-id="07017-111">One or more corresponding XML schemas define which tags are allowed within other tags, in what order, thereby governing the structure of conforming messages.</span></span>  
  
 <span data-ttu-id="07017-112">另一个格式大类（称为平面文件格式）常用于旧系统。</span><span class="sxs-lookup"><span data-stu-id="07017-112">Another broad category of formats, known as flat file formats, are commonly used by legacy systems.</span></span> <span data-ttu-id="07017-113">这些格式使用某些分隔符（例如制表符）和固定长度的字段的组合来确定一个数据项结束、另一个数据项开始的位置。</span><span class="sxs-lookup"><span data-stu-id="07017-113">These formats use some combination of delimiters (such as tabs) and fixed length fields to determine where one data item ends and another begins.</span></span>  
  
 <span data-ttu-id="07017-114">本部分提供了通常由 BizTalk Server 处理的这两种类型消息的结构的高级概述。</span><span class="sxs-lookup"><span data-stu-id="07017-114">This section provides a high-level overview of the structure of these two types of messages that are commonly handled by BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07017-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="07017-115">In This Section</span></span>  
  
-   [<span data-ttu-id="07017-116">XML 消息的结构</span><span class="sxs-lookup"><span data-stu-id="07017-116">Structure of an XML Message</span></span>](../core/structure-of-an-xml-message.md)  
  
-   [<span data-ttu-id="07017-117">平面文件消息的结构</span><span class="sxs-lookup"><span data-stu-id="07017-117">Structure of a Flat File Message</span></span>](../core/structure-of-a-flat-file-message.md)