---
title: "在解析过程中遇到错误。 Edifact 功能组交换中出现以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6af00ae6500419fcb3ed687da89415e7594f1adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a><span data-ttu-id="d18bb-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d18bb-103">Error encountered during parsing.</span></span> <span data-ttu-id="d18bb-104">交换中的 EDIFACT 功能组发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="d18bb-104">The Edifact functional group in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="d18bb-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="d18bb-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d18bb-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="d18bb-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d18bb-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="d18bb-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d18bb-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d18bb-108">Event ID</span></span>|-|  
|<span data-ttu-id="d18bb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d18bb-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d18bb-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="d18bb-110"> EDI</span></span>|  
|<span data-ttu-id="d18bb-111">组件</span><span class="sxs-lookup"><span data-stu-id="d18bb-111">Component</span></span>|<span data-ttu-id="d18bb-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d18bb-112">EDI Engine</span></span>|  
|<span data-ttu-id="d18bb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d18bb-113">Symbolic Name</span></span>|<span data-ttu-id="d18bb-114">EfactFunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="d18bb-114">EfactFunctionalGroupReceiveError</span></span>|  
|<span data-ttu-id="d18bb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d18bb-115">Message Text</span></span>|<span data-ttu-id="d18bb-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d18bb-116">Error encountered during parsing.</span></span> <span data-ttu-id="d18bb-117">Edifact 功能组中 id 为"{0}"，与 id {1} 交换发件人 id {2} 接收方 id {3} 具有以下错误：</span><span class="sxs-lookup"><span data-stu-id="d18bb-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d18bb-118">解释</span><span class="sxs-lookup"><span data-stu-id="d18bb-118">Explanation</span></span>  
 <span data-ttu-id="d18bb-119">此错误/警告/信息事件表明由于通过标识的功能组指明的错误，在分析传入的 EDIFACT 交换时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d18bb-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d18bb-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="d18bb-120">User Action</span></span>  
 <span data-ttu-id="d18bb-121">若要解决此错误，请使用错误消息中的信息来标识组中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="d18bb-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>