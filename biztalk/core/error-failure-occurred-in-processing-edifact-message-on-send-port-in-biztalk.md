---
title: 在发送端口上处理 Edifact 消息时发生故障：不存在用于收件人和发件人标识符限定符对协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cffc4705-164f-4779-8f04-c6a2a7f1bbda
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2937dc29be315ef5298b43a50ab95f52c4573a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348300"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="d5bdd-102">在发送端口上处理 Edifact 消息时发生故障：没有收件人和发件人标识符限定符对的协议</span><span class="sxs-lookup"><span data-stu-id="d5bdd-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="d5bdd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d5bdd-103">Details</span></span>  
  
|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5bdd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d5bdd-104">Product Name</span></span>   |                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| <span data-ttu-id="d5bdd-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d5bdd-105">Product Version</span></span> |                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    <span data-ttu-id="d5bdd-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d5bdd-106">Event ID</span></span>     |                                                                                 -                                                                                 |
|  <span data-ttu-id="d5bdd-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d5bdd-107">Event Source</span></span>   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d5bdd-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d5bdd-108">EDI</span></span>                                       |
|    <span data-ttu-id="d5bdd-109">组件</span><span class="sxs-lookup"><span data-stu-id="d5bdd-109">Component</span></span>    |                                                                            <span data-ttu-id="d5bdd-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d5bdd-110">EDI Engine</span></span>                                                                             |
|  <span data-ttu-id="d5bdd-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d5bdd-111">Symbolic Name</span></span>  |                                                                                 -                                                                                 |
|  <span data-ttu-id="d5bdd-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="d5bdd-112">Message Text</span></span>   | <span data-ttu-id="d5bdd-113">在发送端口上处理 Edifact 消息时发生故障{0}。</span><span class="sxs-lookup"><span data-stu-id="d5bdd-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="d5bdd-114">不存在协议的接收方和发件人标识符/限定符对的{1}， {2}， {3}， {4}。</span><span class="sxs-lookup"><span data-stu-id="d5bdd-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d5bdd-115">解释</span><span class="sxs-lookup"><span data-stu-id="d5bdd-115">Explanation</span></span>  
 <span data-ttu-id="d5bdd-116">此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为它无法匹配提升发件人限定符和标识符属性，并提升接收方限定符和标识符为参与方的相应值的属性。</span><span class="sxs-lookup"><span data-stu-id="d5bdd-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5bdd-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d5bdd-117">User Action</span></span>  
 <span data-ttu-id="d5bdd-118">若要解决此错误，请确保发送方限定符和标识符 （UNB2.1 和 UNB2.2） 和接收方限定符和标识符 （UNB3.1 和 unb3.2 一起使用） 的 EDI 属性对话框中的参与方的 UNB 段定义页中定义的匹配相应交换的上下文中的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="d5bdd-118">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>