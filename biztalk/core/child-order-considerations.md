---
title: "子顺序注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0909a8d69f5079e493fbc579d6ef4b0ca56f9c61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="child-order-considerations"></a><span data-ttu-id="06d05-102">子顺序注意事项</span><span class="sxs-lookup"><span data-stu-id="06d05-102">Child Order Considerations</span></span>

## <a name="requirements-for-header-in-a-flat-file"></a><span data-ttu-id="06d05-103">平面文件中的标头的要求</span><span class="sxs-lookup"><span data-stu-id="06d05-103">Requirements for header in a flat file</span></span>
<span data-ttu-id="06d05-104">与分隔的平面文件，对于这种特殊的注意事项适用时设置相关的两种方案**子顺序**属性。</span><span class="sxs-lookup"><span data-stu-id="06d05-104">There are two scenarios related to delimited flat files for which special considerations apply when setting the **Child Order** property.</span></span> <span data-ttu-id="06d05-105">第一种此类情况涉及平面文件文档包含头部、正文和尾部（可选）的情况。</span><span class="sxs-lookup"><span data-stu-id="06d05-105">The first such scenario concerns situations in which the flat file document has a header, a body, and optionally, a trailer.</span></span> <span data-ttu-id="06d05-106">在这些情况下，必须遵守以下要求：</span><span class="sxs-lookup"><span data-stu-id="06d05-106">In these scenarios, you must observe the following requirements:</span></span>  
  
-   <span data-ttu-id="06d05-107">必须设置**子顺序**（分隔） 根记录的标头到属性**后缀**。</span><span class="sxs-lookup"><span data-stu-id="06d05-107">You must set the **Child Order** property of the (delimited) root record of the header to **Postfix**.</span></span>  
  
-   <span data-ttu-id="06d05-108">如果尾部不存在，则必须设置**子顺序**到正文 （分隔） 根记录的属性**后缀**。</span><span class="sxs-lookup"><span data-stu-id="06d05-108">If a trailer is present, you must set the **Child Order** property of the (delimited) root record of the body to **Postfix**.</span></span>  
  
-   <span data-ttu-id="06d05-109">如果尾部不存在，则可设置**子顺序**到正文 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.</span><span class="sxs-lookup"><span data-stu-id="06d05-109">If a trailer is not present, you may set the **Child Order** property of the (delimited) root record of the body to **Prefix**, **InFix**, or **Postfix**.</span></span>  
  
-   <span data-ttu-id="06d05-110">如果存在尾部，则可能会设置**子顺序**到该预告片 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.</span><span class="sxs-lookup"><span data-stu-id="06d05-110">If a trailer is present, you may set the **Child Order** property of the (delimited) root record of that trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  
  
-   <span data-ttu-id="06d05-111">您可以设置**子顺序**属性的标头、 正文和到预告片分隔从属记录**前缀**，**中缀**，或**后缀**.</span><span class="sxs-lookup"><span data-stu-id="06d05-111">You may set the **Child Order** property of delimited subordinate records of the header, body, and trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  
  
 <span data-ttu-id="06d05-112">与第二个方案分隔平面文件和**子顺序**属性是根据运行时组件针对各个节点的期望必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="06d05-112">The second scenario related to delimited flat files and the **Child Order** property is that this property must be set according to what the runtime components expect for the nodes.</span></span> <span data-ttu-id="06d05-113">正确设置**子顺序**属性不可以是明显的根和组节点，如以下方案中所示：</span><span class="sxs-lookup"><span data-stu-id="06d05-113">The correct setting for the **Child Order** property may not be apparent for root and group nodes, as illustrated in the following scenarios:</span></span>  
  
-   <span data-ttu-id="06d05-114">**根节点。**</span><span class="sxs-lookup"><span data-stu-id="06d05-114">**Root node.**</span></span> <span data-ttu-id="06d05-115">假设一个典型的平面文件，其结构由后跟 CR/LF 组合的记录组成。</span><span class="sxs-lookup"><span data-stu-id="06d05-115">Consider a typical flat file whose structure consists of records followed by a CR/LF combination.</span></span> <span data-ttu-id="06d05-116">分隔符将文件中的记录隔开，并且顺序通常为记录、分隔符、记录、分隔符，以此类推。</span><span class="sxs-lookup"><span data-stu-id="06d05-116">The delimiter separates records in the file, and the sequence is typically record, delimiter, record, delimiter, and so on.</span></span> <span data-ttu-id="06d05-117">在此情况下，分隔符始终遵循的数据，它对应于**子顺序**属性设置的**后缀**。</span><span class="sxs-lookup"><span data-stu-id="06d05-117">In this situation, the delimiter always follows the data, which corresponds to a **Child Order** property setting of **Postfix**.</span></span>  
  
-   <span data-ttu-id="06d05-118">**组节点。**</span><span class="sxs-lookup"><span data-stu-id="06d05-118">**Group nodes.**</span></span> <span data-ttu-id="06d05-119">架构的 BizTalk Server 和 XSD 表示形式中所显示的组节点不会显式存在于实例消息的平面文件表示形式中。</span><span class="sxs-lookup"><span data-stu-id="06d05-119">The group nodes shown in the BizTalk Server and XSD representation of the schema are not explicitly present in the flat file representation of the instance message.</span></span> <span data-ttu-id="06d05-120">假设一个采购订单 (PO) 包含每个行项目的记录集合，并且这些记录重复多次以表示单个 PO 中的多个行项目。</span><span class="sxs-lookup"><span data-stu-id="06d05-120">Consider a purchase order (PO) that contains a collection of records for each line item, and those records repeat numerous times to represent multiple line items in a single PO.</span></span> <span data-ttu-id="06d05-121">此类消息的架构可能包含名为 LineItems 以用作重复组 （有时概念） 容器的节点： 在平面文件表示的实例消息中，LineItems 容器是在本质，由表示概念相应的序列的数据和分隔符;实例消息的 XML 表达形式，LineItems 容器位于显式的窗体**LineItems**中 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="06d05-121">The schema for such a message would likely include a node named LineItems to serve as the (sometimes conceptual) container for the repeating set: in the flat file representation of the instance message, the LineItems container is conceptual in nature, represented by the appropriate sequence of data and delimiters; in the XML representation of the instance message, the LineItems container is explicitly present in the form of a **LineItems** element in XML.</span></span>  
  
 <span data-ttu-id="06d05-122">假设某消息包含一个根节点并且只有一个组节点。</span><span class="sxs-lookup"><span data-stu-id="06d05-122">Consider a message containing a root node and only one group node.</span></span> <span data-ttu-id="06d05-123">可以很容易地看出输入流中最后一个分隔符将属于根节点。</span><span class="sxs-lookup"><span data-stu-id="06d05-123">It is easy to see where the last delimiter in the input stream would belong to the root node.</span></span> <span data-ttu-id="06d05-124">因此，概念循环中的数据/分隔符序列只会是一个或多个行项目记录。</span><span class="sxs-lookup"><span data-stu-id="06d05-124">Therefore, the data/delimiter sequence in the conceptual loop would merely be one or more line item records.</span></span> <span data-ttu-id="06d05-125">只有当存在多个行项目记录时，才会使用分隔符将其隔开。</span><span class="sxs-lookup"><span data-stu-id="06d05-125">Only in the case where there are more than one line item records would there be a delimiter to separate them.</span></span> <span data-ttu-id="06d05-126">在这种情况下，分隔符数少于要分隔的对象总数，并且在称为中缀的结构中，分隔符位于所分隔的项目之间。</span><span class="sxs-lookup"><span data-stu-id="06d05-126">In that case, the number of delimiters is one less than the sets of things being delimited, and the delimiters are located between the delimited items in a structure known as Infix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d05-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06d05-127">See Also</span></span>  
-  [<span data-ttu-id="06d05-128">分隔记录的注意事项</span><span class="sxs-lookup"><span data-stu-id="06d05-128">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
-  <span data-ttu-id="06d05-129">**子顺序 （从节点属性的平面文件架构）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="06d05-129">**Child Order (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>