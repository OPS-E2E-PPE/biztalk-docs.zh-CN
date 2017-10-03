---
title: "消息类型不允许作为协议的一部分 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979aa43d23d2fca95c244e10cb9d4768d76cf3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a><span data-ttu-id="9d450-102">不允许将消息类型作为协议的一部分</span><span class="sxs-lookup"><span data-stu-id="9d450-102">Message Type is not allowed as part of the Agreement</span></span>
## <a name="details"></a><span data-ttu-id="9d450-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9d450-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d450-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9d450-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9d450-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9d450-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9d450-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9d450-106">Event ID</span></span>|-|  
|<span data-ttu-id="9d450-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9d450-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9d450-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9d450-108"> EDI</span></span>|  
|<span data-ttu-id="9d450-109">组件</span><span class="sxs-lookup"><span data-stu-id="9d450-109">Component</span></span>|<span data-ttu-id="9d450-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9d450-110">EDI Engine</span></span>|  
|<span data-ttu-id="9d450-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9d450-111">Symbolic Name</span></span>|<span data-ttu-id="9d450-112">TransactionSetNotAllowedDescription</span><span class="sxs-lookup"><span data-stu-id="9d450-112">TransactionSetNotAllowedDescription</span></span>|  
|<span data-ttu-id="9d450-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9d450-113">Message Text</span></span>|<span data-ttu-id="9d450-114">消息类型 {0} 不允许作为协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d450-114">Message Type {0} is not allowed as part of the Agreement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d450-115">解释</span><span class="sxs-lookup"><span data-stu-id="9d450-115">Explanation</span></span>  
 <span data-ttu-id="9d450-116">此错误/警告/信息事件表明 BizTalk Server 能够处理文档，因为不允许该文档的消息类型是协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d450-116">This Error/Warning/Information event indicates BizTalk Server was able to process the document because the message type of the document is not allowed as part of the agreement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d450-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="9d450-117">User Action</span></span>  
 <span data-ttu-id="9d450-118">若要解决此错误，请查看允许是协议的一部分以及不允许是协议的一部分的消息类型。</span><span class="sxs-lookup"><span data-stu-id="9d450-118">To resolve this error, please look at the message types that are allowed and not allowed as part of the agreement.</span></span>