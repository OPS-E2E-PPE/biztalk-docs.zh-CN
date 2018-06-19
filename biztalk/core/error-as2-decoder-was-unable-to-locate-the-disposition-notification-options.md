---
title: AS2 解码器找不到处置通知选项 HTTP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6de4b9a6-17b2-4455-9dbd-a6bb69fac1d5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966860c7f2b7b47187b861ed6b81fb14a4753872
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240013"
---
# <a name="the-as2-decoder-was-unable-to-locate-the-disposition-notification-options-http-header"></a><span data-ttu-id="dc833-102">AS2 解码器无法定位 Disposition-Notification-Options HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="dc833-102">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header</span></span>
## <a name="details"></a><span data-ttu-id="dc833-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dc833-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc833-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dc833-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="dc833-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="dc833-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="dc833-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dc833-106">Event ID</span></span>|-|  
|<span data-ttu-id="dc833-107">事件源</span><span class="sxs-lookup"><span data-stu-id="dc833-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="dc833-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="dc833-108"> EDI</span></span>|  
|<span data-ttu-id="dc833-109">组件</span><span class="sxs-lookup"><span data-stu-id="dc833-109">Component</span></span>|<span data-ttu-id="dc833-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="dc833-110">AS2 Engine</span></span>|  
|<span data-ttu-id="dc833-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="dc833-111">Symbolic Name</span></span>|<span data-ttu-id="dc833-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span><span class="sxs-lookup"><span data-stu-id="dc833-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span></span>|  
|<span data-ttu-id="dc833-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="dc833-113">Message Text</span></span>|<span data-ttu-id="dc833-114">AS2 解码器无法定位生成 MDN 所必需的 Disposition-Notification-Options HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="dc833-114">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header which is required for MDN generation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc833-115">解释</span><span class="sxs-lookup"><span data-stu-id="dc833-115">Explanation</span></span>  
 <span data-ttu-id="dc833-116">此错误/警告/信息事件表明接收管道无法生成 MDN，因为传入的 AS2 消息不包含 Disposition-Notification-Options 标头，该标头指出是否必须对 MDN 进行签名以及必须使用哪个 MIC 算法。</span><span class="sxs-lookup"><span data-stu-id="dc833-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN because the incoming AS2 message did not include the Disposition-Notification-Options header that indicates whether the MDN must be signed and which MIC algorithm must be used.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc833-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="dc833-117">User Action</span></span>  
 <span data-ttu-id="dc833-118">若要解决此错误，请让 AS2 消息的发送方在消息中包含 Disposition-Notification-Options 标头，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="dc833-118">To resolve this error, have the sender of the AS2 message include the Disposition-Notification-Options header in the message and then resend the message.</span></span>