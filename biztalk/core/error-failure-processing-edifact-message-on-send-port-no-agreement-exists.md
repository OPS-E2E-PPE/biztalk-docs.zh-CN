---
title: 在发送端口上处理 Edifact 消息时发生故障：不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11880c7c-6032-449b-b251-27fc2b2f0d72
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd3df9a2635864f0dcc884426816f1674c9284c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389304"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a><span data-ttu-id="8d25e-102">在发送端口上处理 Edifact 消息时发生故障：不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议</span><span class="sxs-lookup"><span data-stu-id="8d25e-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs and no party with name</span></span>
## <a name="details"></a><span data-ttu-id="8d25e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8d25e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8d25e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8d25e-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| <span data-ttu-id="8d25e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8d25e-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    <span data-ttu-id="8d25e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8d25e-106">Event ID</span></span>     |                                                                                                -                                                                                                 |
|  <span data-ttu-id="8d25e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8d25e-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8d25e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8d25e-108">EDI</span></span>                                                      |
|    <span data-ttu-id="8d25e-109">组件</span><span class="sxs-lookup"><span data-stu-id="8d25e-109">Component</span></span>    |                                                                                            <span data-ttu-id="8d25e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="8d25e-110">EDI Engine</span></span>                                                                                            |
|  <span data-ttu-id="8d25e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8d25e-111">Symbolic Name</span></span>  |                                                                                                -                                                                                                 |
|  <span data-ttu-id="8d25e-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="8d25e-112">Message Text</span></span>   | <span data-ttu-id="8d25e-113">在发送端口上处理 Edifact 消息时发生故障{0}。</span><span class="sxs-lookup"><span data-stu-id="8d25e-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="8d25e-114">不存在协议的接收方和发件人标识符/限定符对的{1}， {2}， {3}， {4}。</span><span class="sxs-lookup"><span data-stu-id="8d25e-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> <span data-ttu-id="8d25e-115">存在具有名称的参与方{5}。</span><span class="sxs-lookup"><span data-stu-id="8d25e-115">No Party exists with name {5}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8d25e-116">解释</span><span class="sxs-lookup"><span data-stu-id="8d25e-116">Explanation</span></span>  
 <span data-ttu-id="8d25e-117">此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为它无法匹配提升发件人限定符和标识符属性，并提升接收方限定符和标识符为参与方的相应值的属性。</span><span class="sxs-lookup"><span data-stu-id="8d25e-117">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d25e-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8d25e-118">User Action</span></span>  
 <span data-ttu-id="8d25e-119">若要解决此错误，请确保发送方限定符和标识符 （UNB2.1 和 UNB2.2） 和接收方限定符和标识符 （UNB3.1 和 unb3.2 一起使用） 的 EDI 属性对话框中的参与方的 UNB 段定义页中定义的匹配相应交换的上下文中的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="8d25e-119">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>