---
title: 消息类型不允许作为协议的一部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d5bb18ad9a46150b45d6994182ad18eb4fa564
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394539"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a><span data-ttu-id="1d885-102">消息类型不允许作为协议的一部分</span><span class="sxs-lookup"><span data-stu-id="1d885-102">Message Type is not allowed as part of the Agreement</span></span>
## <a name="details"></a><span data-ttu-id="1d885-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1d885-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1d885-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1d885-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1d885-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1d885-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1d885-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1d885-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1d885-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1d885-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1d885-108">EDI</span><span class="sxs-lookup"><span data-stu-id="1d885-108">EDI</span></span> |
|    <span data-ttu-id="1d885-109">组件</span><span class="sxs-lookup"><span data-stu-id="1d885-109">Component</span></span>    |                                       <span data-ttu-id="1d885-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1d885-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="1d885-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1d885-111">Symbolic Name</span></span>  |                          <span data-ttu-id="1d885-112">TransactionSetNotAllowedDescription</span><span class="sxs-lookup"><span data-stu-id="1d885-112">TransactionSetNotAllowedDescription</span></span>                           |
|  <span data-ttu-id="1d885-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1d885-113">Message Text</span></span>   |               <span data-ttu-id="1d885-114">消息类型{0}不允许作为协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="1d885-114">Message Type {0} is not allowed as part of the Agreement.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="1d885-115">解释</span><span class="sxs-lookup"><span data-stu-id="1d885-115">Explanation</span></span>  
 <span data-ttu-id="1d885-116">此错误/警告/信息事件表明 BizTalk Server 能够处理文档，因为该文档的消息类型不允许作为协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="1d885-116">This Error/Warning/Information event indicates BizTalk Server was able to process the document because the message type of the document is not allowed as part of the agreement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d885-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="1d885-117">User Action</span></span>  
 <span data-ttu-id="1d885-118">若要解决此错误，请查看允许和不允许作为协议的一部分的消息类型。</span><span class="sxs-lookup"><span data-stu-id="1d885-118">To resolve this error, please look at the message types that are allowed and not allowed as part of the agreement.</span></span>