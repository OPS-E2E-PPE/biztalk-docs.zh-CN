---
title: 组件不能重复，因为它具有无效的重复计数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30f71ebf1ef6c0b48876c27e3f5212be42548f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998598"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a><span data-ttu-id="79ee6-102">组件不能重复，因为它的重复计数无效</span><span class="sxs-lookup"><span data-stu-id="79ee6-102">Component cannot repeat because it has an invalid repetition count</span></span>
## <a name="details"></a><span data-ttu-id="79ee6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="79ee6-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="79ee6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="79ee6-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="79ee6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="79ee6-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="79ee6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="79ee6-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="79ee6-107">事件源</span><span class="sxs-lookup"><span data-stu-id="79ee6-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="79ee6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="79ee6-108"> EDI</span></span> |
|    <span data-ttu-id="79ee6-109">组件</span><span class="sxs-lookup"><span data-stu-id="79ee6-109">Component</span></span>    |                                       <span data-ttu-id="79ee6-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="79ee6-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="79ee6-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="79ee6-111">Symbolic Name</span></span>  |                            <span data-ttu-id="79ee6-112">SchemaCode118EInvalidRepetition</span><span class="sxs-lookup"><span data-stu-id="79ee6-112">SchemaCode118EInvalidRepetition</span></span>                             |
|  <span data-ttu-id="79ee6-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="79ee6-113">Message Text</span></span>   |           <span data-ttu-id="79ee6-114">组件不能重复，它具有无效的重复计数 {0}</span><span class="sxs-lookup"><span data-stu-id="79ee6-114">Component cannot repeat, it has an invalid repetition count of {0}</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="79ee6-115">解释</span><span class="sxs-lookup"><span data-stu-id="79ee6-115">Explanation</span></span>  
 <span data-ttu-id="79ee6-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或者发送管道无法处理传出的交换，因为交换中的元素组件、元素、段或循环重复，而架构是不允许重复的。</span><span class="sxs-lookup"><span data-stu-id="79ee6-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because an element component, element, segment, or loop was repeated in the interchange while the schema does not allow the repetition.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79ee6-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="79ee6-117">User Action</span></span>  
 <span data-ttu-id="79ee6-118">若要解决此错误，请确保根据架构的需要，交换中的元素组件、元素、段或循环不重复，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="79ee6-118">To resolve this error, ensure that the element component, element, segment, or loop does not repeat in the interchange, as required by the schema, and have the message resent.</span></span>