---
title: 故障发生在处理 X12 消息在发送端口：不存在用于收件人和发件人标识符限定符对协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9989a9d5e3c7568e8c02dbc52cfbec23aa0272c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347256"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="ce5a4-102">故障发生在处理 X12 消息在发送端口：没有收件人和发件人标识符限定符对的协议</span><span class="sxs-lookup"><span data-stu-id="ce5a4-102">A failure occurred in processing X12 message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="ce5a4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce5a4-103">Details</span></span>  
  
|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce5a4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ce5a4-104">Product Name</span></span>   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                       |
| <span data-ttu-id="ce5a4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ce5a4-105">Product Version</span></span> |                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                   |
|    <span data-ttu-id="ce5a4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce5a4-106">Event ID</span></span>     |                                                                               -                                                                               |
|  <span data-ttu-id="ce5a4-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ce5a4-107">Event Source</span></span>   |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ce5a4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ce5a4-108">EDI</span></span>                                     |
|    <span data-ttu-id="ce5a4-109">组件</span><span class="sxs-lookup"><span data-stu-id="ce5a4-109">Component</span></span>    |                                                                          <span data-ttu-id="ce5a4-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ce5a4-110">EDI Engine</span></span>                                                                           |
|  <span data-ttu-id="ce5a4-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ce5a4-111">Symbolic Name</span></span>  |                                                                               -                                                                               |
|  <span data-ttu-id="ce5a4-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="ce5a4-112">Message Text</span></span>   | <span data-ttu-id="ce5a4-113">故障发生在处理 X12 消息发送端口上的{0}。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="ce5a4-114">不存在协议的接收方和发件人标识符/限定符对的{1}， {2}， {3}， {4}。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ce5a4-115">解释</span><span class="sxs-lookup"><span data-stu-id="ce5a4-115">Explanation</span></span>  
 <span data-ttu-id="ce5a4-116">此错误/警告/信息事件表明 BizTalk Server 无法解析该参与方的 EDIFACT 交换，因为 BizTalk Server 无法匹配提升发件人限定符和标识符属性，并提升接收方限定符和为参与方的相应值的标识符属性。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce5a4-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ce5a4-117">User Action</span></span>  
 <span data-ttu-id="ce5a4-118">若要解决此错误，请确保发送方限定符和标识符 （ISA5 和 ISA6） 和接收方限定符和标识符 （ISA7 和 ISA8） 中的 EDI 属性对话框中的参与方的 ISA 段定义页定义匹配相应的提升交换的上下文中的属性。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-118">To resolve this error, ensure that the sender qualifier and identifier (ISA5 and ISA6) and receiver qualifier and identifier (ISA7 and ISA8) defined in the party's ISA Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>