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
ms.openlocfilehash: e8ac08333b5506e342fe84a2e7a950610bcdd1b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258617"
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a><span data-ttu-id="ea6dc-102">不支持 AS2 消息中指定的哈希算法</span><span class="sxs-lookup"><span data-stu-id="ea6dc-102">The hash algorithm specified in the AS2 message is unsupported</span></span>
## <a name="details"></a><span data-ttu-id="ea6dc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ea6dc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea6dc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ea6dc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ea6dc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ea6dc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ea6dc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ea6dc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ea6dc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ea6dc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ea6dc-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ea6dc-108">EDI</span></span> |
|    <span data-ttu-id="ea6dc-109">组件</span><span class="sxs-lookup"><span data-stu-id="ea6dc-109">Component</span></span>    |                                       <span data-ttu-id="ea6dc-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="ea6dc-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="ea6dc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ea6dc-111">Symbolic Name</span></span>  |                            <span data-ttu-id="ea6dc-112">UnsupportedAS2HashAlgorithmError</span><span class="sxs-lookup"><span data-stu-id="ea6dc-112">UnsupportedAS2HashAlgorithmError</span></span>                            |
|  <span data-ttu-id="ea6dc-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ea6dc-113">Message Text</span></span>   |            <span data-ttu-id="ea6dc-114">不支持在 AS2 消息中指定的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="ea6dc-114">The hash algorithm specified in the AS2 message is unsupported.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="ea6dc-115">解释</span><span class="sxs-lookup"><span data-stu-id="ea6dc-115">Explanation</span></span>  
 <span data-ttu-id="ea6dc-116">此错误/警告/信息事件表明接收管道无法生成指定的 MDN，因为所收到 AS2 消息的 signed-receipt-micalg 标头中指定的 MIC 哈希算法具有无效的值。</span><span class="sxs-lookup"><span data-stu-id="ea6dc-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN as specified because the MIC hash algorithm specified in the signed-receipt-micalg header of the received AS2 message is not a valid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea6dc-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ea6dc-117">User Action</span></span>  
 <span data-ttu-id="ea6dc-118">若要解决此错误，请让消息的发送方将算法更改为 MD5 或 SHA1 并再次发送消息。</span><span class="sxs-lookup"><span data-stu-id="ea6dc-118">To resolve this error, have the sender of the message change the algorithm to either MD5 or SHA1, and resend the message.</span></span>