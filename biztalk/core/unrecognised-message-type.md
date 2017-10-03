---
title: "不可识别的消息类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd58907b61e68140ccf68d8256882b81e46bd863
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognised-message-type"></a><span data-ttu-id="7ec35-102">不可识别的消息类型</span><span class="sxs-lookup"><span data-stu-id="7ec35-102">Unrecognised message type</span></span>
## <a name="details"></a><span data-ttu-id="7ec35-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ec35-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ec35-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7ec35-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7ec35-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7ec35-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7ec35-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7ec35-106">Event ID</span></span>|-|  
|<span data-ttu-id="7ec35-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7ec35-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7ec35-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7ec35-108"> EDI</span></span>|  
|<span data-ttu-id="7ec35-109">组件</span><span class="sxs-lookup"><span data-stu-id="7ec35-109">Component</span></span>|<span data-ttu-id="7ec35-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7ec35-110">EDI Engine</span></span>|  
|<span data-ttu-id="7ec35-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7ec35-111">Symbolic Name</span></span>|<span data-ttu-id="7ec35-112">UnRecognizedMessageType</span><span class="sxs-lookup"><span data-stu-id="7ec35-112">UnRecognizedMessageType</span></span>|  
|<span data-ttu-id="7ec35-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7ec35-113">Message Text</span></span>|<span data-ttu-id="7ec35-114">不可识别的消息类型。</span><span class="sxs-lookup"><span data-stu-id="7ec35-114">Unrecognised message type.</span></span> <span data-ttu-id="7ec35-115">无法进一步处理。</span><span class="sxs-lookup"><span data-stu-id="7ec35-115">Cannot proceed further.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ec35-116">解释</span><span class="sxs-lookup"><span data-stu-id="7ec35-116">Explanation</span></span>  
 <span data-ttu-id="7ec35-117">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为尚为该交换中的某个事务集的文档类型部署文档架构，或者 BizTalk Server 无法从事务集标识符代码、版本和命名空间中确定文档类型。</span><span class="sxs-lookup"><span data-stu-id="7ec35-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because no document schema has been deployed for the document type of a transaction set in that interchange, or BizTalk Server cannot determine the document type from the transaction set identifier code, version, and namespace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ec35-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7ec35-118">User Action</span></span>  
 <span data-ttu-id="7ec35-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="7ec35-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="7ec35-120">为交换中的事务集的文档类型部署文档架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="7ec35-120">Deploy a document schema for the document type of a transaction set in the interchange, and then resend the interchange.</span></span>  
  
-   <span data-ttu-id="7ec35-121">验证下列值定义有效的架构： 对于 X12，目标命名空间、 版本/发行版和文档类型;对于 edifact 而言，目标命名空间、 消息版本号、 消息发行版号和消息类型。</span><span class="sxs-lookup"><span data-stu-id="7ec35-121">Verify that the following values define a valid schema: for X12, the target namespace, version/release, and document type; for EDIFACT, the target namespace, message version number, message release number, and message type.</span></span> <span data-ttu-id="7ec35-122">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中“接收的 EDI 消息的参与方解析、架构发现和授权”主题的“架构发现”部分。</span><span class="sxs-lookup"><span data-stu-id="7ec35-122">For more information, see the "Schema Discovery" section in the "Party Resolution, Schema Discovery, and Authorization for Received EDI Messages" topic in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>