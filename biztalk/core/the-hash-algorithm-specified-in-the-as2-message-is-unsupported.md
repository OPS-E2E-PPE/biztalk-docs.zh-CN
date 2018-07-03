---
title: 不支持 AS2 消息中指定的哈希算法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c3c46f65fb71ef810fc4e657df01e0065757cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008590"
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a><span data-ttu-id="9cd77-102">不支持在 AS2 消息中指定的哈希算法</span><span class="sxs-lookup"><span data-stu-id="9cd77-102">The hash algorithm specified in the AS2 message is unsupported</span></span>
## <a name="details"></a><span data-ttu-id="9cd77-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9cd77-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9cd77-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9cd77-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9cd77-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9cd77-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9cd77-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9cd77-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9cd77-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9cd77-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9cd77-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9cd77-108"> EDI</span></span> |
|    <span data-ttu-id="9cd77-109">组件</span><span class="sxs-lookup"><span data-stu-id="9cd77-109">Component</span></span>    |                                       <span data-ttu-id="9cd77-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="9cd77-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9cd77-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9cd77-111">Symbolic Name</span></span>  |                            <span data-ttu-id="9cd77-112">UnsupportedAS2HashAlgorithmError</span><span class="sxs-lookup"><span data-stu-id="9cd77-112">UnsupportedAS2HashAlgorithmError</span></span>                            |
|  <span data-ttu-id="9cd77-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9cd77-113">Message Text</span></span>   |            <span data-ttu-id="9cd77-114">不支持在 AS2 消息中指定的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="9cd77-114">The hash algorithm specified in the AS2 message is unsupported.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="9cd77-115">解释</span><span class="sxs-lookup"><span data-stu-id="9cd77-115">Explanation</span></span>  
 <span data-ttu-id="9cd77-116">此错误/警告/信息事件表明接收管道无法生成指定的 MDN，因为所收到 AS2 消息的 signed-receipt-micalg 标头中指定的 MIC 哈希算法具有无效的值。</span><span class="sxs-lookup"><span data-stu-id="9cd77-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN as specified because the MIC hash algorithm specified in the signed-receipt-micalg header of the received AS2 message is not a valid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9cd77-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="9cd77-117">User Action</span></span>  
 <span data-ttu-id="9cd77-118">若要解决此错误，请让消息的发送方将算法更改为 MD5 或 SHA1 并再次发送消息。</span><span class="sxs-lookup"><span data-stu-id="9cd77-118">To resolve this error, have the sender of the message change the algorithm to either MD5 or SHA1, and resend the message.</span></span>