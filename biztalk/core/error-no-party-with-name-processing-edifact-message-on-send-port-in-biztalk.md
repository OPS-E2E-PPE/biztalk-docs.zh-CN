---
title: 在发送端口上处理 Edifact 消息时发生故障： 无带名称参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 823b0d1315c82676017f0cc5e1bfa45b9ed9e342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979334"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a><span data-ttu-id="1fefa-102">在发送端口上处理 Edifact 消息时发生故障： 无带名称参与方</span><span class="sxs-lookup"><span data-stu-id="1fefa-102">A failure occurred in processing Edifact message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="1fefa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1fefa-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1fefa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1fefa-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="1fefa-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1fefa-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="1fefa-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1fefa-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="1fefa-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1fefa-107">Event Source</span></span>   |                                        <span data-ttu-id="1fefa-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="1fefa-108">BizTalk Server EDI</span></span>                                         |
|    <span data-ttu-id="1fefa-109">组件</span><span class="sxs-lookup"><span data-stu-id="1fefa-109">Component</span></span>    |                                            <span data-ttu-id="1fefa-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1fefa-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="1fefa-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1fefa-111">Symbolic Name</span></span>  |                                                 -                                                 |
|  <span data-ttu-id="1fefa-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="1fefa-112">Message Text</span></span>   | <span data-ttu-id="1fefa-113">在发送端口上处理 Edifact 消息时发生故障{0}。</span><span class="sxs-lookup"><span data-stu-id="1fefa-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="1fefa-114">不存在名称为 {1} 的参与方。</span><span class="sxs-lookup"><span data-stu-id="1fefa-114">No Party exists with name {1}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1fefa-115">解释</span><span class="sxs-lookup"><span data-stu-id="1fefa-115">Explanation</span></span>  
 <span data-ttu-id="1fefa-116">此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为 BizTalk Server 无法订阅该交换的参与方与关联的发送端口的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="1fefa-116">This Error/Warning/Information event indicates that BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="1fefa-117">如果既 DestinationPartyName 属性也不发送方限定符和标识符和接收方限定符和标识符属性进行升级，因此不可用于发送端参与方解析，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1fefa-117">This occurs if neither the DestinationPartyName property nor the sender qualifier and identifier and receiver qualifier and identifier properties are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1fefa-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="1fefa-118">User Action</span></span>  
 <span data-ttu-id="1fefa-119">若要解决此错误，请确保订阅交换的发送端口和与某个参与方关联的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="1fefa-119">To resolve this error, ensure that the send port that subscribed to the interchange matches the send port associated with a party.</span></span>