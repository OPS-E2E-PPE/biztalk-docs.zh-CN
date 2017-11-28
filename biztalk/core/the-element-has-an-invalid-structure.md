---
title: "元素具有无效的结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb94843c-cd21-48e3-ba30-aed0518b4d78
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b825fb0d2f5b4fe985a2024b1c97e21f4308b58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-element-has-an-invalid-structure"></a><span data-ttu-id="25b36-102">该元素的结构无效</span><span class="sxs-lookup"><span data-stu-id="25b36-102">The element has an invalid structure</span></span>
## <a name="details"></a><span data-ttu-id="25b36-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="25b36-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25b36-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="25b36-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="25b36-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="25b36-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="25b36-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="25b36-106">Event ID</span></span>|-|  
|<span data-ttu-id="25b36-107">事件源</span><span class="sxs-lookup"><span data-stu-id="25b36-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="25b36-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="25b36-108"> EDI</span></span>|  
|<span data-ttu-id="25b36-109">组件</span><span class="sxs-lookup"><span data-stu-id="25b36-109">Component</span></span>|<span data-ttu-id="25b36-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="25b36-110">EDI Engine</span></span>|  
|<span data-ttu-id="25b36-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="25b36-111">Symbolic Name</span></span>|<span data-ttu-id="25b36-112">X12NseStructurallyInvalidElementDescription</span><span class="sxs-lookup"><span data-stu-id="25b36-112">X12NseStructurallyInvalidElementDescription</span></span>|  
|<span data-ttu-id="25b36-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="25b36-113">Message Text</span></span>|<span data-ttu-id="25b36-114">元素“{0}”具有无效的结构</span><span class="sxs-lookup"><span data-stu-id="25b36-114">The element '{0}' has an invalid structure</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25b36-115">解释</span><span class="sxs-lookup"><span data-stu-id="25b36-115">Explanation</span></span>  
 <span data-ttu-id="25b36-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，或者发送管道无法处理传出的交换，因为某个数据元素没有适用的架构指定的结构。</span><span class="sxs-lookup"><span data-stu-id="25b36-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, or the send pipeline could not process the outgoing interchange, because a data element did not have the structure specified by the applicable schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25b36-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="25b36-117">User Action</span></span>  
 <span data-ttu-id="25b36-118">若要解决此错误，请修复传出交换中该数据元素的结构，或者让交换的发送方修复传入交换中该数据元素的结构，以便它符合文档架构。</span><span class="sxs-lookup"><span data-stu-id="25b36-118">To resolve this error, fix the structure of the data element in the outgoing interchange, or have the sender of the interchange fix the structure of the data element in the incoming interchange, so that it conforms to the document schema.</span></span>