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
ms.openlocfilehash: 50831c03bc7dc0412cdb6fcd40ca981e87cf43f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023187"
---
# <a name="disposition-notification-option-is-invalid"></a><span data-ttu-id="7cdb6-102">Disposition-Notification-Option 无效</span><span class="sxs-lookup"><span data-stu-id="7cdb6-102">Disposition-Notification-Option is invalid</span></span>
## <a name="details"></a><span data-ttu-id="7cdb6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7cdb6-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7cdb6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7cdb6-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7cdb6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7cdb6-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7cdb6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7cdb6-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7cdb6-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7cdb6-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7cdb6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7cdb6-108"> EDI</span></span> |
|    <span data-ttu-id="7cdb6-109">组件</span><span class="sxs-lookup"><span data-stu-id="7cdb6-109">Component</span></span>    |                                       <span data-ttu-id="7cdb6-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="7cdb6-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="7cdb6-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7cdb6-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7cdb6-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="7cdb6-112">Message Text</span></span>   |              <span data-ttu-id="7cdb6-113">处理设置通知选项值:"{0}"无效。</span><span class="sxs-lookup"><span data-stu-id="7cdb6-113">Disposition-Notification-Option value: "{0}" is invalid.</span></span> <span data-ttu-id="7cdb6-114">{1}</span><span class="sxs-lookup"><span data-stu-id="7cdb6-114">{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="7cdb6-115">解释</span><span class="sxs-lookup"><span data-stu-id="7cdb6-115">Explanation</span></span>  
 <span data-ttu-id="7cdb6-116">此错误/警告/信息事件表明 AS2 接收管道无法生成 MDN，因为 Disposition-Notification-Option 标头无效。</span><span class="sxs-lookup"><span data-stu-id="7cdb6-116">This Error/Warning/Information event indicates that the AS2 receive pipeline could not generate the MDN because the Disposition-Notification-Option header was invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7cdb6-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7cdb6-117">User Action</span></span>  
 <span data-ttu-id="7cdb6-118">若要解决此错误，请确保 AS2 消息中的 Disposition-Notification-Option 标头符合 RFC 4130“MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)”（针对使用 HTTP 进行基于 MIME 的安全对等业务数据交换的 Applicability Statement 2 (AS2)）中描述的语法。</span><span class="sxs-lookup"><span data-stu-id="7cdb6-118">To resolve this error, make sure that the Disposition-Notification-Option header in the AS2 message conforms to the syntax described in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span></span> <span data-ttu-id="7cdb6-119">确保 Signed-Receipt-Protocol 标头设置为“可选”或“pcks7-signature”，并且确保 Signed-Receipt-MICAlg 标头设置为“可选”、“MD5”或“SHA1”。</span><span class="sxs-lookup"><span data-stu-id="7cdb6-119">Ensure that the Signed-Receipt-Protocol header is set to "optional" or "pcks7-signature", and that the Signed-Receipt-MICAlg header is set to "optional", "MD5", or "SHA1".</span></span> <span data-ttu-id="7cdb6-120">（这两个这些标头包含处置通知选项标头中。）</span><span class="sxs-lookup"><span data-stu-id="7cdb6-120">(Both of these headers are included in the Disposition-Notification-Option header.)</span></span>