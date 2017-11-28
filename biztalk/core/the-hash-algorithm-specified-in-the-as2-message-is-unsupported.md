---
title: "AS2 消息中指定的哈希算法是不受支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6d16c7a3336a798c18b484bc50ff3e2f0c69764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a><span data-ttu-id="80b6f-102">不支持在 AS2 消息中指定的哈希算法</span><span class="sxs-lookup"><span data-stu-id="80b6f-102">The hash algorithm specified in the AS2 message is unsupported</span></span>
## <a name="details"></a><span data-ttu-id="80b6f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="80b6f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80b6f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="80b6f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="80b6f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="80b6f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="80b6f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="80b6f-106">Event ID</span></span>|-|  
|<span data-ttu-id="80b6f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="80b6f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="80b6f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="80b6f-108"> EDI</span></span>|  
|<span data-ttu-id="80b6f-109">组件</span><span class="sxs-lookup"><span data-stu-id="80b6f-109">Component</span></span>|<span data-ttu-id="80b6f-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="80b6f-110">AS2 Engine</span></span>|  
|<span data-ttu-id="80b6f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="80b6f-111">Symbolic Name</span></span>|<span data-ttu-id="80b6f-112">UnsupportedAS2HashAlgorithmError</span><span class="sxs-lookup"><span data-stu-id="80b6f-112">UnsupportedAS2HashAlgorithmError</span></span>|  
|<span data-ttu-id="80b6f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="80b6f-113">Message Text</span></span>|<span data-ttu-id="80b6f-114">不支持在 AS2 消息中指定的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="80b6f-114">The hash algorithm specified in the AS2 message is unsupported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="80b6f-115">解释</span><span class="sxs-lookup"><span data-stu-id="80b6f-115">Explanation</span></span>  
 <span data-ttu-id="80b6f-116">此错误/警告/信息事件表明接收管道无法生成指定的 MDN，因为所收到 AS2 消息的 signed-receipt-micalg 标头中指定的 MIC 哈希算法具有无效的值。</span><span class="sxs-lookup"><span data-stu-id="80b6f-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN as specified because the MIC hash algorithm specified in the signed-receipt-micalg header of the received AS2 message is not a valid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="80b6f-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="80b6f-117">User Action</span></span>  
 <span data-ttu-id="80b6f-118">若要解决此错误，请让消息的发送方将算法更改为 MD5 或 SHA1 并再次发送消息。</span><span class="sxs-lookup"><span data-stu-id="80b6f-118">To resolve this error, have the sender of the message change the algorithm to either MD5 or SHA1, and resend the message.</span></span>