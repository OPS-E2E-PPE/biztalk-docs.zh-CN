---
title: 交换发生了结构错误的第一个功能组之前 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051323ef4c1ff6456595e34d6989e0183f050766
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254368"
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a><span data-ttu-id="607ab-102">交换发生了结构错误的第一个功能组之前</span><span class="sxs-lookup"><span data-stu-id="607ab-102">The interchange had a structural error in-before the first functional group</span></span>
## <a name="details"></a><span data-ttu-id="607ab-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="607ab-103">Details</span></span>  
  
|                 |                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="607ab-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="607ab-104">Product Name</span></span>   |                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                        |
| <span data-ttu-id="607ab-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="607ab-105">Product Version</span></span> |                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                    |
|    <span data-ttu-id="607ab-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="607ab-106">Event ID</span></span>     |                                                                -                                                                 |
|  <span data-ttu-id="607ab-107">事件源</span><span class="sxs-lookup"><span data-stu-id="607ab-107">Event Source</span></span>   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="607ab-108">EDI</span><span class="sxs-lookup"><span data-stu-id="607ab-108">EDI</span></span>                      |
|    <span data-ttu-id="607ab-109">组件</span><span class="sxs-lookup"><span data-stu-id="607ab-109">Component</span></span>    |                                                            <span data-ttu-id="607ab-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="607ab-110">EDI Engine</span></span>                                                            |
|  <span data-ttu-id="607ab-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="607ab-111">Symbolic Name</span></span>  |                                           <span data-ttu-id="607ab-112">X12InterchangeStructuralErrorBefore1stGroup</span><span class="sxs-lookup"><span data-stu-id="607ab-112">X12InterchangeStructuralErrorBefore1stGroup</span></span>                                            |
|  <span data-ttu-id="607ab-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="607ab-113">Message Text</span></span>   | <span data-ttu-id="607ab-114">交换 id 为 '{0}，发送方 id{1}，接收方 id{2}第一个功能组中/之前有结构错误</span><span class="sxs-lookup"><span data-stu-id="607ab-114">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error in/before the first functional group</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="607ab-115">解释</span><span class="sxs-lookup"><span data-stu-id="607ab-115">Explanation</span></span>  
 <span data-ttu-id="607ab-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，出于以下原因之一：</span><span class="sxs-lookup"><span data-stu-id="607ab-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, for one of the following reasons:</span></span>  
  
-   <span data-ttu-id="607ab-117">因此交换不符合适用的架构中的 ISA 和 IEA 段或交换，在第一个功能组发生了结构错误。</span><span class="sxs-lookup"><span data-stu-id="607ab-117">A structural error occurred in either the ISA and IEA segments or the first functional group of the interchange, so the interchange did not conform to the applicable schema.</span></span>  
  
-   <span data-ttu-id="607ab-118">未部署 X12ServiceSchema （在 BaseArtifacts.dll 中)。</span><span class="sxs-lookup"><span data-stu-id="607ab-118">The X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="607ab-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="607ab-119">User Action</span></span>  
 <span data-ttu-id="607ab-120">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="607ab-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="607ab-121">让发件人的交换更改 ISA 和/或 IEA 段或者第一个功能组，以便它符合适用的架构，，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="607ab-121">Have the sender of the interchange change the ISA and/or IEA segments or the first functional group so that it conforms to the applicable schema, and then resend the interchange.</span></span>  
  
-   <span data-ttu-id="607ab-122">确保 BaseArtifacts.dll 包含 X12ServiceSchema 并且已部署。</span><span class="sxs-lookup"><span data-stu-id="607ab-122">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="607ab-123">可以通过打开 BizTalk Server 管理控制台、 打开 BizTalk EDI 应用程序节点和架构节点，并验证列出了 X12ServiceSchema 来执行操作。</span><span class="sxs-lookup"><span data-stu-id="607ab-123">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>