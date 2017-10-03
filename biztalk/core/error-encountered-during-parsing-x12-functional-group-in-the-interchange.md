---
title: "在解析过程中遇到错误。 X12 功能组交换中出现以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2229c83-89bd-491f-9504-4afbf0084297
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e519e8f89f00574ad2b51c1f9884889077c902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a><span data-ttu-id="96e0a-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="96e0a-103">Error encountered during parsing.</span></span> <span data-ttu-id="96e0a-104">交换中的 x12 功能组发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="96e0a-104">The X12 functional group in the interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="96e0a-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="96e0a-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96e0a-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="96e0a-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="96e0a-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="96e0a-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="96e0a-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="96e0a-108">Event ID</span></span>|-|  
|<span data-ttu-id="96e0a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="96e0a-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="96e0a-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="96e0a-110"> EDI</span></span>|  
|<span data-ttu-id="96e0a-111">组件</span><span class="sxs-lookup"><span data-stu-id="96e0a-111">Component</span></span>|<span data-ttu-id="96e0a-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="96e0a-112">EDI Engine</span></span>|  
|<span data-ttu-id="96e0a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="96e0a-113">Symbolic Name</span></span>|<span data-ttu-id="96e0a-114">X12FunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="96e0a-114">X12FunctionalGroupReceiveError</span></span>|  
|<span data-ttu-id="96e0a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="96e0a-115">Message Text</span></span>|<span data-ttu-id="96e0a-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="96e0a-116">Error encountered during parsing.</span></span> <span data-ttu-id="96e0a-117">Id 为"{0}"中的交换 id {1} 的发件人 id {2} 接收方 X12 功能组 id {3} 出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="96e0a-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="96e0a-118">解释</span><span class="sxs-lookup"><span data-stu-id="96e0a-118">Explanation</span></span>  
 <span data-ttu-id="96e0a-119">此错误/警告/信息事件表明由于通过标识的功能组指明的错误，在分析传入的 X12 交换时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="96e0a-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96e0a-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="96e0a-120">User Action</span></span>  
 <span data-ttu-id="96e0a-121">若要解决此错误，请使用错误消息中的信息来标识组中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="96e0a-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>