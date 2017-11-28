---
title: "无效的 AS2-从收到的标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f20a74e60a6365c0c16e139e8b2caca1bc33646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-from-header-received"></a><span data-ttu-id="48ca9-102">收到的 AS2-From 头部无效</span><span class="sxs-lookup"><span data-stu-id="48ca9-102">Invalid AS2-From header received</span></span>
## <a name="details"></a><span data-ttu-id="48ca9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="48ca9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48ca9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="48ca9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="48ca9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="48ca9-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="48ca9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="48ca9-106">Event ID</span></span>|-|  
|<span data-ttu-id="48ca9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="48ca9-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="48ca9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="48ca9-108"> EDI</span></span>|  
|<span data-ttu-id="48ca9-109">组件</span><span class="sxs-lookup"><span data-stu-id="48ca9-109">Component</span></span>|<span data-ttu-id="48ca9-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="48ca9-110">AS2 Engine</span></span>|  
|<span data-ttu-id="48ca9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="48ca9-111">Symbolic Name</span></span>|<span data-ttu-id="48ca9-112">InvalidAS2FromNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="48ca9-112">InvalidAS2FromNameHeaderReceivedError</span></span>|  
|<span data-ttu-id="48ca9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="48ca9-113">Message Text</span></span>|<span data-ttu-id="48ca9-114">收到的 AS2-From 头部无效。</span><span class="sxs-lookup"><span data-stu-id="48ca9-114">Invalid AS2-From header received.</span></span>  <span data-ttu-id="48ca9-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="48ca9-115">Value: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="48ca9-116">解释</span><span class="sxs-lookup"><span data-stu-id="48ca9-116">Explanation</span></span>  
 <span data-ttu-id="48ca9-117">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为消息中 AS2-From 标头的值不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="48ca9-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-From header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48ca9-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="48ca9-118">User Action</span></span>  
 <span data-ttu-id="48ca9-119">若要解决此错误，请确保消息中 AS2-From 标头的值符合 AS2 RFC 4130 第 6.2 节中的规范，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="48ca9-119">To resolve this error, make sure that the value in the AS2-From header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>