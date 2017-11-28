---
title: "为此 AS2 交换方必须包含值对于 AS2-从 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b52f153cce06eac014d98fa1908978694fc67706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a><span data-ttu-id="6fb2a-102">此 AS2 交换的参与方必须包含 AS2-From 的值</span><span class="sxs-lookup"><span data-stu-id="6fb2a-102">The party for this AS2 interchange must contain a value for AS2-From</span></span>
## <a name="details"></a><span data-ttu-id="6fb2a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6fb2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6fb2a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6fb2a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6fb2a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="6fb2a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6fb2a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6fb2a-106">Event ID</span></span>|-|  
|<span data-ttu-id="6fb2a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="6fb2a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6fb2a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6fb2a-108"> EDI</span></span>|  
|<span data-ttu-id="6fb2a-109">组件</span><span class="sxs-lookup"><span data-stu-id="6fb2a-109">Component</span></span>|<span data-ttu-id="6fb2a-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="6fb2a-110">AS2 Engine</span></span>|  
|<span data-ttu-id="6fb2a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="6fb2a-111">Symbolic Name</span></span>|<span data-ttu-id="6fb2a-112">InvalidAgreementAS2FromName</span><span class="sxs-lookup"><span data-stu-id="6fb2a-112">InvalidAgreementAS2FromName</span></span>|  
|<span data-ttu-id="6fb2a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="6fb2a-113">Message Text</span></span>|<span data-ttu-id="6fb2a-114">此 AS2 交换的参与方必须包含 AS2-From 的值。</span><span class="sxs-lookup"><span data-stu-id="6fb2a-114">The party for this AS2 interchange must contain a value for AS2-From.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6fb2a-115">解释</span><span class="sxs-lookup"><span data-stu-id="6fb2a-115">Explanation</span></span>  
 <span data-ttu-id="6fb2a-116">此错误/警告/信息事件表明发送管道无法发送 AS2 消息，因为没有为解析后的作为消息接收方的参与方设置 AS2-From 属性。</span><span class="sxs-lookup"><span data-stu-id="6fb2a-116">This Error/Warning/Information event indicates that the send pipeline could not send the AS2 message because the AS2-From property was not set for the resolved party as message receiver.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fb2a-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="6fb2a-117">User Action</span></span>  
 <span data-ttu-id="6fb2a-118">若要解决此错误，请打开 BizTalk Server 管理控制台，移动到“参与方”节点，打开为消息解析的参与方的“AS2 属性”对话框，单击“作为 AS2 消息接收方的参与方”节点，然后为“AS2-From”属性输入值。</span><span class="sxs-lookup"><span data-stu-id="6fb2a-118">To resolve this error, open the BizTalk Server Administration Console, move to the Parties node, open the AS2 Properties dialog box for the party resolved for the message, click the Party as AS2 Message Receiver node, and then enter a value for the AS2-From property.</span></span>