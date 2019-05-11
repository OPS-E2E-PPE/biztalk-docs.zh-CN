---
title: 故障发生在处理 X12 消息在发送端口：不带名称的参与方 |Microsoft Docs
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
ms.openlocfilehash: efebb75a8d7b4989382f7c4855aab9b981c38c2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362431"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a><span data-ttu-id="c2d8d-102">故障发生在处理 X12 消息在发送端口：不带名称的参与方</span><span class="sxs-lookup"><span data-stu-id="c2d8d-102">A failure occurred in processing X12 message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="c2d8d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2d8d-103">Details</span></span>  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c2d8d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c2d8d-104">Product Name</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="c2d8d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c2d8d-105">Product Version</span></span> |                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    <span data-ttu-id="c2d8d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c2d8d-106">Event ID</span></span>     |                                               -                                               |
|  <span data-ttu-id="c2d8d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c2d8d-107">Event Source</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c2d8d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c2d8d-108">EDI</span></span>     |
|    <span data-ttu-id="c2d8d-109">组件</span><span class="sxs-lookup"><span data-stu-id="c2d8d-109">Component</span></span>    |                                          <span data-ttu-id="c2d8d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c2d8d-110">EDI Engine</span></span>                                           |
|  <span data-ttu-id="c2d8d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c2d8d-111">Symbolic Name</span></span>  |                                               -                                               |
|  <span data-ttu-id="c2d8d-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="c2d8d-112">Message Text</span></span>   | <span data-ttu-id="c2d8d-113">故障发生在处理 X12 消息发送端口上的{0}。</span><span class="sxs-lookup"><span data-stu-id="c2d8d-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="c2d8d-114">存在具有名称的参与方{1}。</span><span class="sxs-lookup"><span data-stu-id="c2d8d-114">No Party exists with name {1}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c2d8d-115">解释</span><span class="sxs-lookup"><span data-stu-id="c2d8d-115">Explanation</span></span>  
 <span data-ttu-id="c2d8d-116">此错误/警告/信息事件表明 BizTalk Server 无法解析的参与方的 X12 交换，因为 BizTalk Server 无法将订阅该交换的参与方与关联的发送端口的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="c2d8d-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the X12 interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="c2d8d-117">如果既 DestinationPartyName 属性，也不发送方限定符、 发送方标识符、 接收方限定符和接收方标识符属性进行升级，因此不可用于发送端参与方解析，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="c2d8d-117">This occurs if neither the DestinationPartyName property, nor the sender qualifier, sender identifier, receiver qualifier, and receiver identifier properties, are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2d8d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="c2d8d-118">User Action</span></span>  
 <span data-ttu-id="c2d8d-119">若要解决此错误，请确保订阅交换的发送端口匹配与参与方关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="c2d8d-119">To resolve this error, ensure the send port that subscribed to the interchange matches the send port associated with a party.</span></span>