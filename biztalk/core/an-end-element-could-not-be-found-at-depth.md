---
title: "在深度找不到 End 元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a90265b4348e4d35b66099f426b6f6177851ccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-could-not-be-found-at-depth"></a><span data-ttu-id="f4d98-102">在深度找不到 End Element</span><span class="sxs-lookup"><span data-stu-id="f4d98-102">An End Element could not be found at depth</span></span>
## <a name="details"></a><span data-ttu-id="f4d98-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f4d98-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4d98-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f4d98-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f4d98-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f4d98-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f4d98-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4d98-106">Event ID</span></span>|-|  
|<span data-ttu-id="f4d98-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f4d98-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f4d98-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f4d98-108"> EDI</span></span>|  
|<span data-ttu-id="f4d98-109">组件</span><span class="sxs-lookup"><span data-stu-id="f4d98-109">Component</span></span>|<span data-ttu-id="f4d98-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="f4d98-110">EDI Engine</span></span>|  
|<span data-ttu-id="f4d98-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f4d98-111">Symbolic Name</span></span>|<span data-ttu-id="f4d98-112">EndElementNotFoundAtDepth</span><span class="sxs-lookup"><span data-stu-id="f4d98-112">EndElementNotFoundAtDepth</span></span>|  
|<span data-ttu-id="f4d98-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f4d98-113">Message Text</span></span>|<span data-ttu-id="f4d98-114">在深度 {0} 找不到 End Element</span><span class="sxs-lookup"><span data-stu-id="f4d98-114">An End Element at depth {0} could not be found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4d98-115">解释</span><span class="sxs-lookup"><span data-stu-id="f4d98-115">Explanation</span></span>  
 <span data-ttu-id="f4d98-116">此错误/警告/信息事件表明 BizTalk Server 无法处理传出的交换，因为 XML 消息未通过验证。</span><span class="sxs-lookup"><span data-stu-id="f4d98-116">This Error/Warning/Information event indicates that BizTalk Server could not process the outgoing interchange because the XML message failed validation.</span></span> <span data-ttu-id="f4d98-117">XML 消息不包含标头或数据元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="f4d98-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4d98-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="f4d98-118">User Action</span></span>  
 <span data-ttu-id="f4d98-119">若要解决此错误，请向 XML 消息中添加相应的结束标记或尾部，然后重新发送。</span><span class="sxs-lookup"><span data-stu-id="f4d98-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend.</span></span>