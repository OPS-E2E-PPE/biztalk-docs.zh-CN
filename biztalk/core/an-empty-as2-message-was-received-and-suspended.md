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
ms.openlocfilehash: e1c99776d350f556855b541290fac1f6a65f5921
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360259"
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="62957-102">空的 AS2 消息收到，被挂起</span><span class="sxs-lookup"><span data-stu-id="62957-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="62957-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="62957-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="62957-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="62957-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="62957-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="62957-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="62957-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="62957-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="62957-107">事件源</span><span class="sxs-lookup"><span data-stu-id="62957-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="62957-108">EDI</span><span class="sxs-lookup"><span data-stu-id="62957-108">EDI</span></span> |
|    <span data-ttu-id="62957-109">组件</span><span class="sxs-lookup"><span data-stu-id="62957-109">Component</span></span>    |                                       <span data-ttu-id="62957-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="62957-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="62957-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="62957-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="62957-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="62957-112">Message Text</span></span>   |           <span data-ttu-id="62957-113">收到空的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="62957-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="62957-114">该消息将挂起。</span><span class="sxs-lookup"><span data-stu-id="62957-114">The message will be suspended.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="62957-115">解释</span><span class="sxs-lookup"><span data-stu-id="62957-115">Explanation</span></span>  
 <span data-ttu-id="62957-116">此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 AS2 消息，因为该消息不包含正文。</span><span class="sxs-lookup"><span data-stu-id="62957-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="62957-117">正文必须由两个回车符/换行符馈送分隔从标头。</span><span class="sxs-lookup"><span data-stu-id="62957-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62957-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="62957-118">User Action</span></span>  
 <span data-ttu-id="62957-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="62957-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="62957-120">请确保发送方发送之前将 （从标头以分隔两个回车符/换行符馈送） 的主体添加到 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="62957-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>