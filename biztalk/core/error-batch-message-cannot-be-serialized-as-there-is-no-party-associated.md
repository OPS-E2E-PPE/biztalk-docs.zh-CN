---
title: 无法序列化批处理消息，因为没有任何与关联一方发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b20d10a2c7b584eccc7d1fb57e5132a4ac0d608
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241477"
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a><span data-ttu-id="4bb77-102">批消息不能序列化，因为没有与发送端口相关联的参与方</span><span class="sxs-lookup"><span data-stu-id="4bb77-102">Batch message cannot be serialized as there is no party associated with send port</span></span>
## <a name="details"></a><span data-ttu-id="4bb77-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4bb77-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bb77-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4bb77-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4bb77-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4bb77-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="4bb77-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4bb77-106">Event ID</span></span>|-|  
|<span data-ttu-id="4bb77-107">事件源</span><span class="sxs-lookup"><span data-stu-id="4bb77-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4bb77-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4bb77-108"> EDI</span></span>|  
|<span data-ttu-id="4bb77-109">组件</span><span class="sxs-lookup"><span data-stu-id="4bb77-109">Component</span></span>|<span data-ttu-id="4bb77-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="4bb77-110">Batching Engine</span></span>|  
|<span data-ttu-id="4bb77-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="4bb77-111">Symbolic Name</span></span>|<span data-ttu-id="4bb77-112">BatchMessageSerializationFailureDueToMissingParty</span><span class="sxs-lookup"><span data-stu-id="4bb77-112">BatchMessageSerializationFailureDueToMissingParty</span></span>|  
|<span data-ttu-id="4bb77-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="4bb77-113">Message Text</span></span>|<span data-ttu-id="4bb77-114">批处理消息无法序列化，因为没有与发送端口 {0} 关联的参与方。</span><span class="sxs-lookup"><span data-stu-id="4bb77-114">Batch message can not be serialized as there is no party associated with send port {0}.</span></span> <span data-ttu-id="4bb77-115">请确保有参与方与该端口关联。</span><span class="sxs-lookup"><span data-stu-id="4bb77-115">Make sure that a party is associated with the port</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4bb77-116">解释</span><span class="sxs-lookup"><span data-stu-id="4bb77-116">Explanation</span></span>  
 <span data-ttu-id="4bb77-117">此错误/警告/信息事件表明发送管道无法处理保留的交换，因为它无法确定应将消息发送到的参与方。</span><span class="sxs-lookup"><span data-stu-id="4bb77-117">This Error/Warning/Information event indicates that the send pipeline could not process a preserved interchange because it could not determine the party that the message should be sent to.</span></span> <span data-ttu-id="4bb77-118">它无法确定参与方，因为未设置 DestinationPartyName 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="4bb77-118">It could not determine the party because the DestinationPartyName context property was not set.</span></span> <span data-ttu-id="4bb77-119">因此，发送管道无法确定信封设置。</span><span class="sxs-lookup"><span data-stu-id="4bb77-119">As a result, the send pipeline could not determine the envelope settings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4bb77-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="4bb77-120">User Action</span></span>  
 <span data-ttu-id="4bb77-121">若要解决此错误，请通过直通发送管道传递消息，然后确定该消息的 DestinationPartyName 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="4bb77-121">To resolve this error, pass the message through a passthrough send pipeline, and then determine the DestinationPartyName context property for the message.</span></span> <span data-ttu-id="4bb77-122">验证参与方是否存在。</span><span class="sxs-lookup"><span data-stu-id="4bb77-122">Verify that the party exists.</span></span> <span data-ttu-id="4bb77-123">如果不存在，请创建参与方，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="4bb77-123">If not, create the party, and then resend the message.</span></span>