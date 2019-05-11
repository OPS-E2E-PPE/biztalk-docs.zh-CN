---
title: 是无效的处置通知选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8956b6ef3dd583522bb142e646920d4731651391
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350999"
---
# <a name="disposition-notification-option-is-invalid"></a><span data-ttu-id="5311f-102">处理设置通知选项无效</span><span class="sxs-lookup"><span data-stu-id="5311f-102">Disposition-Notification-Option is invalid</span></span>
## <a name="details"></a><span data-ttu-id="5311f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5311f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5311f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5311f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5311f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5311f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5311f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5311f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5311f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5311f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5311f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5311f-108">EDI</span></span> |
|    <span data-ttu-id="5311f-109">组件</span><span class="sxs-lookup"><span data-stu-id="5311f-109">Component</span></span>    |                                       <span data-ttu-id="5311f-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="5311f-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="5311f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5311f-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="5311f-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="5311f-112">Message Text</span></span>   |              <span data-ttu-id="5311f-113">处理设置通知选项值:"{0}"无效。</span><span class="sxs-lookup"><span data-stu-id="5311f-113">Disposition-Notification-Option value: "{0}" is invalid.</span></span> <span data-ttu-id="5311f-114">{1}</span><span class="sxs-lookup"><span data-stu-id="5311f-114">{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="5311f-115">解释</span><span class="sxs-lookup"><span data-stu-id="5311f-115">Explanation</span></span>  
 <span data-ttu-id="5311f-116">此错误/警告/信息事件表明 AS2 接收管道无法生成 MDN，因为处理设置通知选项标头无效。</span><span class="sxs-lookup"><span data-stu-id="5311f-116">This Error/Warning/Information event indicates that the AS2 receive pipeline could not generate the MDN because the Disposition-Notification-Option header was invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5311f-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="5311f-117">User Action</span></span>  
 <span data-ttu-id="5311f-118">若要解决此错误，请确保在 AS2 消息处置通知选项标头符合 RFC 4130 中描述的语法"基于 MIME 的安全对等业务数据交换使用 HTTP、 Applicability Statement 2 (AS2")。</span><span class="sxs-lookup"><span data-stu-id="5311f-118">To resolve this error, make sure that the Disposition-Notification-Option header in the AS2 message conforms to the syntax described in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span></span> <span data-ttu-id="5311f-119">请确保签名回执协议标头设置为"可选"或"pcks7-签名"和 Signed-receipt-micalg 的标头已设置为"可选"、"MD5"或"SHA1"。</span><span class="sxs-lookup"><span data-stu-id="5311f-119">Ensure that the Signed-Receipt-Protocol header is set to "optional" or "pcks7-signature", and that the Signed-Receipt-MICAlg header is set to "optional", "MD5", or "SHA1".</span></span> <span data-ttu-id="5311f-120">（这两个这些标头包含处置通知选项标头中。）</span><span class="sxs-lookup"><span data-stu-id="5311f-120">(Both of these headers are included in the Disposition-Notification-Option header.)</span></span>