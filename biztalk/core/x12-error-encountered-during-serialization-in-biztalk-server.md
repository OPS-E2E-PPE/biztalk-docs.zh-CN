---
title: "在序列化期间遇到错误。 X12 功能组具有以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6b74d713f0d182a07cc6a509cd7d06fc34b82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a><span data-ttu-id="776b2-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="776b2-103">Error encountered during serialization.</span></span> <span data-ttu-id="776b2-104">X 12 功能组发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="776b2-104">The X12 functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="776b2-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="776b2-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="776b2-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="776b2-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="776b2-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="776b2-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="776b2-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="776b2-108">Event ID</span></span>|-|  
|<span data-ttu-id="776b2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="776b2-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="776b2-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="776b2-110"> EDI</span></span>|  
|<span data-ttu-id="776b2-111">组件</span><span class="sxs-lookup"><span data-stu-id="776b2-111">Component</span></span>|<span data-ttu-id="776b2-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="776b2-112">EDI Engine</span></span>|  
|<span data-ttu-id="776b2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="776b2-113">Symbolic Name</span></span>|<span data-ttu-id="776b2-114">X12FunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="776b2-114">X12FunctionalGroupSendError</span></span>|  
|<span data-ttu-id="776b2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="776b2-115">Message Text</span></span>|<span data-ttu-id="776b2-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="776b2-116">Error encountered during serialization.</span></span> <span data-ttu-id="776b2-117">Id 为"{0}"中的交换 id {1} 的发件人 id {2} 接收方 X12 功能组 id {3} 出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="776b2-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="776b2-118">解释</span><span class="sxs-lookup"><span data-stu-id="776b2-118">Explanation</span></span>  
 <span data-ttu-id="776b2-119">此错误/警告/信息事件表明由于通过标识的功能指明的错误，在序列化传出的 X12 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="776b2-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="776b2-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="776b2-120">User Action</span></span>  
 <span data-ttu-id="776b2-121">若要解决此错误，请使用错误消息中的信息来标识功能组中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="776b2-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the product help.</span></span>