---
title: 已收到空的 AS2 消息，将其挂起 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349f7134-d039-44ab-b2b3-d378d38dfd38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48701d24b405f46ad66a76c0ac473fb7343317f2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994126"
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="6a7c1-102">收到空的 AS2 消息，该消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="6a7c1-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="6a7c1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6a7c1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6a7c1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6a7c1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6a7c1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="6a7c1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6a7c1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6a7c1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6a7c1-107">事件源</span><span class="sxs-lookup"><span data-stu-id="6a7c1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6a7c1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6a7c1-108"> EDI</span></span> |
|    <span data-ttu-id="6a7c1-109">组件</span><span class="sxs-lookup"><span data-stu-id="6a7c1-109">Component</span></span>    |                                       <span data-ttu-id="6a7c1-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="6a7c1-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="6a7c1-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="6a7c1-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="6a7c1-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="6a7c1-112">Message Text</span></span>   |           <span data-ttu-id="6a7c1-113">收到空的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="6a7c1-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="6a7c1-114">该消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="6a7c1-114">The message will be suspended.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="6a7c1-115">解释</span><span class="sxs-lookup"><span data-stu-id="6a7c1-115">Explanation</span></span>  
 <span data-ttu-id="6a7c1-116">此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 AS2 消息，因为该消息不包含正文。</span><span class="sxs-lookup"><span data-stu-id="6a7c1-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="6a7c1-117">正文必须由两个回车符/换行符馈送分隔从标头。</span><span class="sxs-lookup"><span data-stu-id="6a7c1-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a7c1-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="6a7c1-118">User Action</span></span>  
 <span data-ttu-id="6a7c1-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a7c1-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="6a7c1-120">请确保发送方发送之前将 （从标头以分隔两个回车符/换行符馈送） 的主体添加到 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="6a7c1-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>