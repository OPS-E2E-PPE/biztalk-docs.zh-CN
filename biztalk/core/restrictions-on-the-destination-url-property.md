---
title: 对目标 URL 属性的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98220fbc5ec99780d230c46751b903cf34167d8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254873"
---
# <a name="restrictions-on-the-destination-url-property"></a><span data-ttu-id="13918-102">对目标 URL 属性的限制</span><span class="sxs-lookup"><span data-stu-id="13918-102">Restrictions on the Destination URL Property</span></span>
<span data-ttu-id="13918-103">目标 URL 是一个字符串，指定你想要使用 HTTP 协议发送消息的 HTTP 服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="13918-103">The destination URL is a string that specifies the address of the HTTP server where you want to send messages using the HTTP protocol.</span></span>  
  
 <span data-ttu-id="13918-104">目标 URL 属性适用以下规则和限制：</span><span class="sxs-lookup"><span data-stu-id="13918-104">The following rules and restrictions apply to the destination URL property:</span></span>  
  
-   <span data-ttu-id="13918-105">始终必须采用以下格式指定目标 URL 属性：</span><span class="sxs-lookup"><span data-stu-id="13918-105">You must always specify the destination URL property in the following format:</span></span>  
  
     <span data-ttu-id="13918-106">http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]</span><span class="sxs-lookup"><span data-stu-id="13918-106">http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]</span></span>  
  
-   <span data-ttu-id="13918-107">整个字符串可能会或可能不采用 URI 编码。</span><span class="sxs-lookup"><span data-stu-id="13918-107">The whole string may or may not be URI encoded.</span></span>  
  
-   <span data-ttu-id="13918-108">整个字符串，除了查询字符串中，不能包含任何以下字符： \< \> : \ &#124; "？</span><span class="sxs-lookup"><span data-stu-id="13918-108">The whole string, except the query string, cannot contain any of the following characters: \< \> : \ &#124; " ?</span></span> <span data-ttu-id="13918-109">\*.</span><span class="sxs-lookup"><span data-stu-id="13918-109">\*.</span></span>  
  
-   <span data-ttu-id="13918-110">该属性不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="13918-110">The property is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="13918-111">字符串的长度不得超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="13918-111">The length of the string must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13918-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="13918-112">See Also</span></span>  
 [<span data-ttu-id="13918-113">配置 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="13918-113">Configuring an HTTP Send Port</span></span>](../core/configuring-an-http-send-port.md)