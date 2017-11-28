---
title: "在解析过程中遇到错误。 Edifact 交换了以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4585966de7ecb410f8f46fa675fa4eae0c6715a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="74403-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="74403-103">Error encountered during parsing.</span></span> <span data-ttu-id="74403-104">EDIFACT 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="74403-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="74403-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="74403-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74403-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="74403-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="74403-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="74403-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="74403-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="74403-108">Event ID</span></span>|-|  
|<span data-ttu-id="74403-109">事件源</span><span class="sxs-lookup"><span data-stu-id="74403-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="74403-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="74403-110"> EDI</span></span>|  
|<span data-ttu-id="74403-111">组件</span><span class="sxs-lookup"><span data-stu-id="74403-111">Component</span></span>|<span data-ttu-id="74403-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="74403-112">EDI Engine</span></span>|  
|<span data-ttu-id="74403-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="74403-113">Symbolic Name</span></span>|<span data-ttu-id="74403-114">EfactInterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="74403-114">EfactInterchangeReceiveError</span></span>|  
|<span data-ttu-id="74403-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="74403-115">Message Text</span></span>|<span data-ttu-id="74403-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="74403-116">Error encountered during parsing.</span></span> <span data-ttu-id="74403-117">Id 为"{0}"，发件人 id {1} Edifact 交换，接收方 id {2} 具有以下错误：</span><span class="sxs-lookup"><span data-stu-id="74403-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74403-118">解释</span><span class="sxs-lookup"><span data-stu-id="74403-118">Explanation</span></span>  
 <span data-ttu-id="74403-119">此错误/警告/信息事件表明由于在交换中指出的错误，在分析传入的 EDIFACT 交换时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="74403-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74403-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="74403-120">User Action</span></span>  
 <span data-ttu-id="74403-121">若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="74403-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>