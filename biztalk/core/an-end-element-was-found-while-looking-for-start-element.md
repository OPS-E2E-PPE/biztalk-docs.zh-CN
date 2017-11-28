---
title: "查找启动元素时，发现结束元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dacaa096b15a6f2969ed56b5bac2138876a6095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a><span data-ttu-id="0037d-102">查找 Start 元素时发现一个 End 元素</span><span class="sxs-lookup"><span data-stu-id="0037d-102">An End Element was found while looking for Start Element</span></span>
## <a name="details"></a><span data-ttu-id="0037d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0037d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0037d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0037d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0037d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0037d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0037d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0037d-106">Event ID</span></span>|-|  
|<span data-ttu-id="0037d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0037d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0037d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0037d-108"> EDI</span></span>|  
|<span data-ttu-id="0037d-109">组件</span><span class="sxs-lookup"><span data-stu-id="0037d-109">Component</span></span>|<span data-ttu-id="0037d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0037d-110">EDI Engine</span></span>|  
|<span data-ttu-id="0037d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0037d-111">Symbolic Name</span></span>|<span data-ttu-id="0037d-112">EndElementFoundWhenLookingForStartElement</span><span class="sxs-lookup"><span data-stu-id="0037d-112">EndElementFoundWhenLookingForStartElement</span></span>|  
|<span data-ttu-id="0037d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0037d-113">Message Text</span></span>|<span data-ttu-id="0037d-114">名为 {0} EndElement 时，发现，寻找与名称 {1}，在深度 {2} StartElement</span><span class="sxs-lookup"><span data-stu-id="0037d-114">An EndElement with name {0} was found, while looking for StartElement with name {1}, at depth {2}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0037d-115">解释</span><span class="sxs-lookup"><span data-stu-id="0037d-115">Explanation</span></span>  
 <span data-ttu-id="0037d-116">此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 XML 消息（分析后）或传出的 XML 消息（序列化前），因为 XML 消息未通过验证。</span><span class="sxs-lookup"><span data-stu-id="0037d-116">This Error/Warning/Information event indicates that BizTalk Server could not process an incoming XML message (after parsing) or an outgoing XML message (before serialization) because the XML message failed validation.</span></span> <span data-ttu-id="0037d-117">XML 消息不包含标头或数据元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="0037d-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0037d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="0037d-118">User Action</span></span>  
 <span data-ttu-id="0037d-119">若要解决此错误，请向 XML 消息中添加相应的结束标记或尾部，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="0037d-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend the message.</span></span>