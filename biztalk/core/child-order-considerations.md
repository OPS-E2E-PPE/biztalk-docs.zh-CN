---
title: 子顺序的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef7e2783bea6c67301c704319035ee0617296eed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977158"
---
# <a name="child-order-considerations"></a><span data-ttu-id="fa861-102">子顺序的注意事项</span><span class="sxs-lookup"><span data-stu-id="fa861-102">Child Order Considerations</span></span>

## <a name="requirements-for-header-in-a-flat-file"></a><span data-ttu-id="fa861-103">平面文件中的标头的要求</span><span class="sxs-lookup"><span data-stu-id="fa861-103">Requirements for header in a flat file</span></span>
<span data-ttu-id="fa861-104">有两种与分隔平面文件的特殊注意事项将应用设置时相关的方案**子顺序**属性。</span><span class="sxs-lookup"><span data-stu-id="fa861-104">There are two scenarios related to delimited flat files for which special considerations apply when setting the **Child Order** property.</span></span> <span data-ttu-id="fa861-105">第一种此类情况涉及平面文件文档包含头部、正文和尾部（可选）的情况。</span><span class="sxs-lookup"><span data-stu-id="fa861-105">The first such scenario concerns situations in which the flat file document has a header, a body, and optionally, a trailer.</span></span> <span data-ttu-id="fa861-106">在这些情况下，必须遵守以下要求：</span><span class="sxs-lookup"><span data-stu-id="fa861-106">In these scenarios, you must observe the following requirements:</span></span>  

- <span data-ttu-id="fa861-107">必须设置**子顺序**到标头的 （分隔） 根记录的属性**后缀**。</span><span class="sxs-lookup"><span data-stu-id="fa861-107">You must set the **Child Order** property of the (delimited) root record of the header to **Postfix**.</span></span>  

- <span data-ttu-id="fa861-108">如果存在尾部，则必须设置**子顺序**正文的 （分隔） 根记录的属性**后缀**。</span><span class="sxs-lookup"><span data-stu-id="fa861-108">If a trailer is present, you must set the **Child Order** property of the (delimited) root record of the body to **Postfix**.</span></span>  

- <span data-ttu-id="fa861-109">如果不存在尾部，则可以设置**子顺序**正文的 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.</span><span class="sxs-lookup"><span data-stu-id="fa861-109">If a trailer is not present, you may set the **Child Order** property of the (delimited) root record of the body to **Prefix**, **InFix**, or **Postfix**.</span></span>  

- <span data-ttu-id="fa861-110">如果存在尾部，则可以设置**子顺序**该尾部的 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.</span><span class="sxs-lookup"><span data-stu-id="fa861-110">If a trailer is present, you may set the **Child Order** property of the (delimited) root record of that trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  

- <span data-ttu-id="fa861-111">您可以设置**子顺序**属性的标头、 正文和尾部的分隔从属记录**前缀**，**中缀**，或**后缀**.</span><span class="sxs-lookup"><span data-stu-id="fa861-111">You may set the **Child Order** property of delimited subordinate records of the header, body, and trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  

  <span data-ttu-id="fa861-112">与第二个方案带分隔符的平面文件和**子顺序**属性是根据运行时组件预期节点必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="fa861-112">The second scenario related to delimited flat files and the **Child Order** property is that this property must be set according to what the runtime components expect for the nodes.</span></span> <span data-ttu-id="fa861-113">为正确的设置**子顺序**属性可能不是明显的根节点和组节点，如以下方案中所示：</span><span class="sxs-lookup"><span data-stu-id="fa861-113">The correct setting for the **Child Order** property may not be apparent for root and group nodes, as illustrated in the following scenarios:</span></span>  

- <span data-ttu-id="fa861-114">**根节点。**</span><span class="sxs-lookup"><span data-stu-id="fa861-114">**Root node.**</span></span> <span data-ttu-id="fa861-115">假设一个典型的平面文件，其结构由后跟 CR/LF 组合的记录组成。</span><span class="sxs-lookup"><span data-stu-id="fa861-115">Consider a typical flat file whose structure consists of records followed by a CR/LF combination.</span></span> <span data-ttu-id="fa861-116">分隔符将文件中的记录隔开，并且顺序通常为记录、分隔符、记录、分隔符，以此类推。</span><span class="sxs-lookup"><span data-stu-id="fa861-116">The delimiter separates records in the file, and the sequence is typically record, delimiter, record, delimiter, and so on.</span></span> <span data-ttu-id="fa861-117">在这种情况下，分隔符始终遵循数据，这对应于**子顺序**属性设置为**后缀**。</span><span class="sxs-lookup"><span data-stu-id="fa861-117">In this situation, the delimiter always follows the data, which corresponds to a **Child Order** property setting of **Postfix**.</span></span>  

- <span data-ttu-id="fa861-118">**组节点。**</span><span class="sxs-lookup"><span data-stu-id="fa861-118">**Group nodes.**</span></span> <span data-ttu-id="fa861-119">架构的 BizTalk Server 和 XSD 表示形式中所显示的组节点不会显式存在于实例消息的平面文件表示形式中。</span><span class="sxs-lookup"><span data-stu-id="fa861-119">The group nodes shown in the BizTalk Server and XSD representation of the schema are not explicitly present in the flat file representation of the instance message.</span></span> <span data-ttu-id="fa861-120">假设一个采购订单 (PO) 包含每个行项目的记录集合，并且这些记录重复多次以表示单个 PO 中的多个行项目。</span><span class="sxs-lookup"><span data-stu-id="fa861-120">Consider a purchase order (PO) that contains a collection of records for each line item, and those records repeat numerous times to represent multiple line items in a single PO.</span></span> <span data-ttu-id="fa861-121">此类消息的架构可能包括名为 LineItems 充当重复集的 （有时概念） 容器的节点： 在平面文件表示的实例消息中，LineItems 容器本质上是概念性，由表示数据和分隔符; 的合适的规则在实例消息的 XML 表示中，LineItems 容器则以的形式显式存在于**LineItems**中 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="fa861-121">The schema for such a message would likely include a node named LineItems to serve as the (sometimes conceptual) container for the repeating set: in the flat file representation of the instance message, the LineItems container is conceptual in nature, represented by the appropriate sequence of data and delimiters; in the XML representation of the instance message, the LineItems container is explicitly present in the form of a **LineItems** element in XML.</span></span>  

  <span data-ttu-id="fa861-122">假设某消息包含一个根节点并且只有一个组节点。</span><span class="sxs-lookup"><span data-stu-id="fa861-122">Consider a message containing a root node and only one group node.</span></span> <span data-ttu-id="fa861-123">可以很容易地看出输入流中最后一个分隔符将属于根节点。</span><span class="sxs-lookup"><span data-stu-id="fa861-123">It is easy to see where the last delimiter in the input stream would belong to the root node.</span></span> <span data-ttu-id="fa861-124">因此，概念循环中的数据/分隔符序列只会是一个或多个行项目记录。</span><span class="sxs-lookup"><span data-stu-id="fa861-124">Therefore, the data/delimiter sequence in the conceptual loop would merely be one or more line item records.</span></span> <span data-ttu-id="fa861-125">只有当存在多个行项目记录时，才会使用分隔符将其隔开。</span><span class="sxs-lookup"><span data-stu-id="fa861-125">Only in the case where there are more than one line item records would there be a delimiter to separate them.</span></span> <span data-ttu-id="fa861-126">在这种情况下，分隔符数少于要分隔的对象总数，并且在称为中缀的结构中，分隔符位于所分隔的项目之间。</span><span class="sxs-lookup"><span data-stu-id="fa861-126">In that case, the number of delimiters is one less than the sets of things being delimited, and the delimiters are located between the delimited items in a structure known as Infix.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fa861-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa861-127">See Also</span></span>  
- [<span data-ttu-id="fa861-128">分隔记录注意事项</span><span class="sxs-lookup"><span data-stu-id="fa861-128">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="fa861-129">**子顺序 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fa861-129">**Child Order (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
