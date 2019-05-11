---
title: 此 AS2 交换的参与方必须包含值为 AS2-到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccabce0ce60f018f6d55d64a26c1f9540ed88fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394099"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a><span data-ttu-id="ff2ef-102">此 AS2 交换的参与方必须包含值为 AS2-到</span><span class="sxs-lookup"><span data-stu-id="ff2ef-102">The party for this AS2 interchange must contain a value for AS2-To</span></span>
## <a name="details"></a><span data-ttu-id="ff2ef-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff2ef-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ff2ef-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ff2ef-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ff2ef-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ff2ef-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ff2ef-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ff2ef-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ff2ef-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ff2ef-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ff2ef-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ff2ef-108">EDI</span></span> |
|    <span data-ttu-id="ff2ef-109">组件</span><span class="sxs-lookup"><span data-stu-id="ff2ef-109">Component</span></span>    |                                       <span data-ttu-id="ff2ef-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="ff2ef-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="ff2ef-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ff2ef-111">Symbolic Name</span></span>  |                               <span data-ttu-id="ff2ef-112">InvalidAgreementAS2ToName</span><span class="sxs-lookup"><span data-stu-id="ff2ef-112">InvalidAgreementAS2ToName</span></span>                                |
|  <span data-ttu-id="ff2ef-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ff2ef-113">Message Text</span></span>   |          <span data-ttu-id="ff2ef-114">此 AS2 交换的参与方必须包含值为 AS2-到。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-114">The party for this AS2 interchange must contain a value for AS2-To.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="ff2ef-115">解释</span><span class="sxs-lookup"><span data-stu-id="ff2ef-115">Explanation</span></span>  
 <span data-ttu-id="ff2ef-116">此错误/警告/信息事件表明发送管道不无法处理传出的 AS2 消息，因为 AS2-作为消息接收方的解析参与方未设置属性。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-116">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing AS2 message because the AS2-To property was not set for the resolved party as message receiver.</span></span> <span data-ttu-id="ff2ef-117">这表示传出的 AS2 消息的参与方已通过匹配订阅该消息的发送端口的参与方与关联的发送端口来解决。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-117">This indicates that the party for the outgoing AS2 message was resolved by matching the send port associated with the party with the send port that subscribed to the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff2ef-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ff2ef-118">User Action</span></span>  
 <span data-ttu-id="ff2ef-119">若要解决此错误，请执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff2ef-119">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="ff2ef-120">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="ff2ef-121">转到参与方节点，然后打开为消息解析的参与方 AS2 属性对话框。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-121">Move to the Parties node, and open the AS2 Properties dialog box for the party resolved for the message.</span></span>  
  
3.  <span data-ttu-id="ff2ef-122">为 AS2 消息接收方节点中单击的参与方。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-122">Click the Party as AS2 Message Receiver node.</span></span>  
  
4.  <span data-ttu-id="ff2ef-123">输入 AS2 的值的属性。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-123">Enter a value for the AS2-To property.</span></span>