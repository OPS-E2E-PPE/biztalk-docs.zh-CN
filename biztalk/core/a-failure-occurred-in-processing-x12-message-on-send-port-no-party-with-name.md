---
title: 出现故障。 处理 X12 发送端口上的消息： 具有名称的否方 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e620797d45fb0b3d2ef929865a4b8bb98d2d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225349"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a><span data-ttu-id="e5044-102">出现故障。 处理 X12 发送端口上的消息： 具有名称的否方</span><span class="sxs-lookup"><span data-stu-id="e5044-102">A failure occurred in processing X12 message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="e5044-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e5044-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5044-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e5044-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e5044-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e5044-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e5044-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e5044-106">Event ID</span></span>|-|  
|<span data-ttu-id="e5044-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e5044-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e5044-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e5044-108"> EDI</span></span>|  
|<span data-ttu-id="e5044-109">组件</span><span class="sxs-lookup"><span data-stu-id="e5044-109">Component</span></span>|<span data-ttu-id="e5044-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e5044-110">EDI Engine</span></span>|  
|<span data-ttu-id="e5044-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e5044-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="e5044-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="e5044-112">Message Text</span></span>|<span data-ttu-id="e5044-113">在发送端口 {0} 上处理 X12 消息时发生故障。</span><span class="sxs-lookup"><span data-stu-id="e5044-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="e5044-114">任何一方不存在名称 {1}。</span><span class="sxs-lookup"><span data-stu-id="e5044-114">No Party exists with name {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e5044-115">解释</span><span class="sxs-lookup"><span data-stu-id="e5044-115">Explanation</span></span>  
 <span data-ttu-id="e5044-116">此错误/警告/信息事件表示 BizTalk Server 无法解析 x12 参与方交换因为 BizTalk Server 无法与使用方与关联的发送端口交换订阅的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="e5044-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the X12 interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="e5044-117">如果不 DestinationPartyName 属性，也不发件人限定符、 发件人标识符、 接收方限定符，而且接收方标识符属性提升，因此不可用于发送方参与方解析，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e5044-117">This occurs if neither the DestinationPartyName property, nor the sender qualifier, sender identifier, receiver qualifier, and receiver identifier properties, are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5044-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e5044-118">User Action</span></span>  
 <span data-ttu-id="e5044-119">若要解决此错误，确保交换订阅发送端口与匹配与方关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="e5044-119">To resolve this error, ensure the send port that subscribed to the interchange matches the send port associated with a party.</span></span>