---
title: 为此 AS2 交换方必须包含值对于 AS2-到 |Microsoft 文档
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
ms.openlocfilehash: 4adda90c2ae0e5dfa659e3bd36dcadfc58f815ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279085"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a><span data-ttu-id="b654d-102">此 AS2 交换的参与方必须包含 AS2-To 的值</span><span class="sxs-lookup"><span data-stu-id="b654d-102">The party for this AS2 interchange must contain a value for AS2-To</span></span>
## <a name="details"></a><span data-ttu-id="b654d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b654d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b654d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b654d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b654d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b654d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b654d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b654d-106">Event ID</span></span>|-|  
|<span data-ttu-id="b654d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b654d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b654d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b654d-108"> EDI</span></span>|  
|<span data-ttu-id="b654d-109">组件</span><span class="sxs-lookup"><span data-stu-id="b654d-109">Component</span></span>|<span data-ttu-id="b654d-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="b654d-110">AS2 Engine</span></span>|  
|<span data-ttu-id="b654d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b654d-111">Symbolic Name</span></span>|<span data-ttu-id="b654d-112">InvalidAgreementAS2ToName</span><span class="sxs-lookup"><span data-stu-id="b654d-112">InvalidAgreementAS2ToName</span></span>|  
|<span data-ttu-id="b654d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b654d-113">Message Text</span></span>|<span data-ttu-id="b654d-114">此 AS2 交换的参与方必须包含 AS2-To 的值。</span><span class="sxs-lookup"><span data-stu-id="b654d-114">The party for this AS2 interchange must contain a value for AS2-To.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b654d-115">解释</span><span class="sxs-lookup"><span data-stu-id="b654d-115">Explanation</span></span>  
 <span data-ttu-id="b654d-116">此错误/警告/信息事件表明发送管道无法处理传出的 AS2 消息，因为没有为解析后的作为消息接收方的参与方设置 AS2-To 属性。</span><span class="sxs-lookup"><span data-stu-id="b654d-116">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing AS2 message because the AS2-To property was not set for the resolved party as message receiver.</span></span> <span data-ttu-id="b654d-117">这表明通过将与参与方关联的发送端口与订阅消息的发送端口匹配来解析传出 AS2 消息的参与方。</span><span class="sxs-lookup"><span data-stu-id="b654d-117">This indicates that the party for the outgoing AS2 message was resolved by matching the send port associated with the party with the send port that subscribed to the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b654d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="b654d-118">User Action</span></span>  
 <span data-ttu-id="b654d-119">若要解决此错误，请执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b654d-119">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="b654d-120">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b654d-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="b654d-121">移动到“参与方”节点，并打开为消息解析的参与方的“AS2 属性”对话框。</span><span class="sxs-lookup"><span data-stu-id="b654d-121">Move to the Parties node, and open the AS2 Properties dialog box for the party resolved for the message.</span></span>  
  
3.  <span data-ttu-id="b654d-122">单击“作为 AS2 消息接收方的参与方”节点。</span><span class="sxs-lookup"><span data-stu-id="b654d-122">Click the Party as AS2 Message Receiver node.</span></span>  
  
4.  <span data-ttu-id="b654d-123">为 AS2-To 属性输入值。</span><span class="sxs-lookup"><span data-stu-id="b654d-123">Enter a value for the AS2-To property.</span></span>