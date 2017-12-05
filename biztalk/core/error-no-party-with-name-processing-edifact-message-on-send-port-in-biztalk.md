---
title: "处理在发送端口上的 Edifact 消息时出现故障： 同名否方 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6becad3fefaa8167c9cf1af051731aa08be0d80a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a><span data-ttu-id="d98b7-102">处理在发送端口上的 Edifact 消息时出现故障： 同名否方</span><span class="sxs-lookup"><span data-stu-id="d98b7-102">A failure occurred in processing Edifact message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="d98b7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d98b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d98b7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d98b7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d98b7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d98b7-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d98b7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d98b7-106">Event ID</span></span>|-|  
|<span data-ttu-id="d98b7-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d98b7-107">Event Source</span></span>|<span data-ttu-id="d98b7-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="d98b7-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="d98b7-109">组件</span><span class="sxs-lookup"><span data-stu-id="d98b7-109">Component</span></span>|<span data-ttu-id="d98b7-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d98b7-110">EDI Engine</span></span>|  
|<span data-ttu-id="d98b7-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d98b7-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="d98b7-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="d98b7-112">Message Text</span></span>|<span data-ttu-id="d98b7-113">在发送端口 {0} 上处理 Edifact 消息时发生故障。</span><span class="sxs-lookup"><span data-stu-id="d98b7-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="d98b7-114">任何一方不存在名称 {1}。</span><span class="sxs-lookup"><span data-stu-id="d98b7-114">No Party exists with name {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d98b7-115">解释</span><span class="sxs-lookup"><span data-stu-id="d98b7-115">Explanation</span></span>  
 <span data-ttu-id="d98b7-116">此错误/警告/信息事件指示 BizTalk 服务器无法解析为 EDIFACT 交换参与方，因为 BizTalk Server 无法与使用方与关联的发送端口交换订阅的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="d98b7-116">This Error/Warning/Information event indicates that BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="d98b7-117">如果不 DestinationPartyName 属性也发件人限定符和标识符和接收方限定符和标识符属性提升，因此不可用于发送方参与方解析，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d98b7-117">This occurs if neither the DestinationPartyName property nor the sender qualifier and identifier and receiver qualifier and identifier properties are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d98b7-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="d98b7-118">User Action</span></span>  
 <span data-ttu-id="d98b7-119">若要解决此错误，请确保订阅交换的发送端口和与某个参与方关联的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="d98b7-119">To resolve this error, ensure that the send port that subscribed to the interchange matches the send port associated with a party.</span></span>