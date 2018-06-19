---
title: 已接收到空的 AS2 消息，将其挂起 |Microsoft 文档
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
ms.openlocfilehash: 90c8221c7e0bd5b297b33118b8672fbe55612244
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230125"
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="44caa-102">收到空的 AS2 消息，该消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="44caa-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="44caa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="44caa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44caa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="44caa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="44caa-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="44caa-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="44caa-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44caa-106">Event ID</span></span>|-|  
|<span data-ttu-id="44caa-107">事件源</span><span class="sxs-lookup"><span data-stu-id="44caa-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="44caa-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="44caa-108"> EDI</span></span>|  
|<span data-ttu-id="44caa-109">组件</span><span class="sxs-lookup"><span data-stu-id="44caa-109">Component</span></span>|<span data-ttu-id="44caa-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="44caa-110">AS2 Engine</span></span>|  
|<span data-ttu-id="44caa-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="44caa-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="44caa-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="44caa-112">Message Text</span></span>|<span data-ttu-id="44caa-113">收到空的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="44caa-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="44caa-114">该消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="44caa-114">The message will be suspended.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44caa-115">解释</span><span class="sxs-lookup"><span data-stu-id="44caa-115">Explanation</span></span>  
 <span data-ttu-id="44caa-116">此错误/警告/信息事件指示 BizTalk Server 无法处理为传入 AS2 消息，因为消息不包含正文。</span><span class="sxs-lookup"><span data-stu-id="44caa-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="44caa-117">正文必须由两个回车符/换行符馈送分隔标头中。</span><span class="sxs-lookup"><span data-stu-id="44caa-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44caa-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="44caa-118">User Action</span></span>  
 <span data-ttu-id="44caa-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="44caa-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="44caa-120">确保发送方发送之前将正文 （从标头以两个回车符/换行符馈送进行分隔） 添加到 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="44caa-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>