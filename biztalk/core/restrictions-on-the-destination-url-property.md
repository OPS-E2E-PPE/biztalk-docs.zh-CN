---
title: "在目标 URL 属性上的限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7966fccca324a1453f0ea84e79cd7d9d3d55ad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="restrictions-on-the-destination-url-property"></a><span data-ttu-id="64cc2-102">在目标 URL 属性上的限制</span><span class="sxs-lookup"><span data-stu-id="64cc2-102">Restrictions on the Destination URL Property</span></span>
<span data-ttu-id="64cc2-103">目标 URL 是指定要在其中使用 HTTP 协议发送消息的 HTTP 服务器地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="64cc2-103">The destination URL is a string that specifies the address of the HTTP server where you want to send messages using the HTTP protocol.</span></span>  
  
 <span data-ttu-id="64cc2-104">目标 URL 属性适用以下规则和限制：</span><span class="sxs-lookup"><span data-stu-id="64cc2-104">The following rules and restrictions apply to the destination URL property:</span></span>  
  
-   <span data-ttu-id="64cc2-105">必须始终采用以下格式指定目标 URL 属性：</span><span class="sxs-lookup"><span data-stu-id="64cc2-105">You must always specify the destination URL property in the following format:</span></span>  
  
     <span data-ttu-id="64cc2-106">http [s]://\<主机\>[:\<端口\>] [/\<路径\>[/\<文件\>[？\<查询字符串\>]]]</span><span class="sxs-lookup"><span data-stu-id="64cc2-106">http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]</span></span>  
  
-   <span data-ttu-id="64cc2-107">整个字符串可以采用 URI 编码，也可不采用 URI 编码。</span><span class="sxs-lookup"><span data-stu-id="64cc2-107">The whole string may or may not be URI encoded.</span></span>  
  
-   <span data-ttu-id="64cc2-108">整个字符串，除查询字符串中，不能包含任何以下字符： \< \> : \ &#124;" ?</span><span class="sxs-lookup"><span data-stu-id="64cc2-108">The whole string, except the query string, cannot contain any of the following characters: \< \> : \ &#124; " ?</span></span> <span data-ttu-id="64cc2-109">*.</span><span class="sxs-lookup"><span data-stu-id="64cc2-109">*.</span></span>  
  
-   <span data-ttu-id="64cc2-110">该属性不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="64cc2-110">The property is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="64cc2-111">字符串的长度不得超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="64cc2-111">The length of the string must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cc2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64cc2-112">See Also</span></span>  
 [<span data-ttu-id="64cc2-113">配置 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="64cc2-113">Configuring an HTTP Send Port</span></span>](../core/configuring-an-http-send-port.md)