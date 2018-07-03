---
title: Edifact 交换应该包含 TransactionSetGroup 或 FunctionalGroup Xml 标记 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34318133-211f-422d-acdf-b841ece5d2b0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5736a9146a88dd9c9dac6747e381fccc88f18d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979326"
---
# <a name="edifact-interchange-should-have-contained-transactionsetgroup-or-functionalgroup-xml-tags"></a><span data-ttu-id="40572-102">Edifact 交换应该包含 TransactionSetGroup 或 FunctionalGroup Xml 标记</span><span class="sxs-lookup"><span data-stu-id="40572-102">Edifact interchange should have contained TransactionSetGroup or FunctionalGroup Xml tags</span></span>
## <a name="details"></a><span data-ttu-id="40572-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="40572-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="40572-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="40572-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="40572-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="40572-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="40572-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="40572-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="40572-107">事件源</span><span class="sxs-lookup"><span data-stu-id="40572-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="40572-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="40572-108"> EDI</span></span>   |
|    <span data-ttu-id="40572-109">组件</span><span class="sxs-lookup"><span data-stu-id="40572-109">Component</span></span>    |                                        <span data-ttu-id="40572-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="40572-110">EDI Engine</span></span>                                         |
|  <span data-ttu-id="40572-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="40572-111">Symbolic Name</span></span>  |                                             -                                             |
|  <span data-ttu-id="40572-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="40572-112">Message Text</span></span>   | <span data-ttu-id="40572-113">Edifact 交换应该包含 TransactionSetGroup 或 FunctionalGroup Xml 标记</span><span class="sxs-lookup"><span data-stu-id="40572-113">Edifact interchange should have contained TransactionSetGroup or FunctionalGroup Xml tags</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="40572-114">解释</span><span class="sxs-lookup"><span data-stu-id="40572-114">Explanation</span></span>  
 <span data-ttu-id="40572-115">此错误/警告/信息事件表明发送管道无法处理保留的 EDIFACT 批处理交换，因为该交换的 XML 文件中不包含 TransactionSetGroup 或 FunctionalGroup 标记。</span><span class="sxs-lookup"><span data-stu-id="40572-115">This Error/Warning/Information event indicates that the send pipeline could not process an EDIFACT batched interchange that was preserved because the TransactionSetGroup or FunctionalGroup tags were not included in the interchange XML file.</span></span>  
  
 <span data-ttu-id="40572-116">当 BizTalk 处理保留的批处理交换时，为该交换的 XML 文件中的一组事务集或组给出了 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="40572-116">When BizTalk processes a batched interchange that is preserved, a group of transaction sets or a group of groups in the interchange's XML file are given an XML tag.</span></span> <span data-ttu-id="40572-117">为一组事务集给出了 TransactionSetGroup 标记。</span><span class="sxs-lookup"><span data-stu-id="40572-117">A group of transaction sets is given the TransactionSetGroup tag.</span></span> <span data-ttu-id="40572-118">为一组组给出了 FunctionalGroup 标记。</span><span class="sxs-lookup"><span data-stu-id="40572-118">A group of groups is given the FunctionalGroup tag.</span></span> <span data-ttu-id="40572-119">如果您使用接收管道和直通传输发送管道设置保留的批处理，则可能会出现此错误条件。</span><span class="sxs-lookup"><span data-stu-id="40572-119">This error condition occurs if you set up a preserved batch using a receive pipeline and a passthrough transmit send pipeline.</span></span> <span data-ttu-id="40572-120">这些标记是由接收管道设置的并且由发送管道删除。</span><span class="sxs-lookup"><span data-stu-id="40572-120">The tags are set by the receive pipeline and stripped out by the send pipeline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40572-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="40572-121">User Action</span></span>  
 <span data-ttu-id="40572-122">若要解决此错误，请确保为保留的批处理器生成的 XML 文件具有格式正确的 XML 结构，该结构具有 TransactionSetGroup 标记（对于一个具有多个事务集的组） 和/或 FunctionalGroup 标记（对于多个组）。</span><span class="sxs-lookup"><span data-stu-id="40572-122">To resolve this error, ensure that the XML file generated for the preserved batch has a well-formed XML structure with the TransactionSetGroup tag (for a group with multiple transaction sets) and/or the FunctionalGroup tag (for multiple groups).</span></span>