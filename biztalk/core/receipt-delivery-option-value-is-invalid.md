---
title: "回执送达选项值无效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f14541cd9c296e6a4527e7c2958123e072be8c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receipt-delivery-option-value-is-invalid"></a><span data-ttu-id="31499-102">Receipt-Delivery-Option 值无效</span><span class="sxs-lookup"><span data-stu-id="31499-102">Receipt-Delivery-Option value is invalid</span></span>
## <a name="details"></a><span data-ttu-id="31499-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="31499-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31499-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="31499-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="31499-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="31499-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="31499-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="31499-106">Event ID</span></span>|-|  
|<span data-ttu-id="31499-107">事件源</span><span class="sxs-lookup"><span data-stu-id="31499-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="31499-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="31499-108"> EDI</span></span>|  
|<span data-ttu-id="31499-109">组件</span><span class="sxs-lookup"><span data-stu-id="31499-109">Component</span></span>|<span data-ttu-id="31499-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="31499-110">AS2 Engine</span></span>|  
|<span data-ttu-id="31499-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="31499-111">Symbolic Name</span></span>|<span data-ttu-id="31499-112">InvalidReceiptDeliveryOptionError</span><span class="sxs-lookup"><span data-stu-id="31499-112">InvalidReceiptDeliveryOptionError</span></span>|  
|<span data-ttu-id="31499-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="31499-113">Message Text</span></span>|<span data-ttu-id="31499-114">回执送达选项值:"{0}"无效。</span><span class="sxs-lookup"><span data-stu-id="31499-114">Receipt-Delivery-Option value: "{0}" is invalid.</span></span>  <span data-ttu-id="31499-115">{1}</span><span class="sxs-lookup"><span data-stu-id="31499-115">{1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31499-116">解释</span><span class="sxs-lookup"><span data-stu-id="31499-116">Explanation</span></span>  
 <span data-ttu-id="31499-117">此错误/警告/信息事件表明所收到的 AS2 消息中的 Receipt-Delivery-Option 是无效的 URL 并且不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="31499-117">This Error/Warning/Information event indicates that the Receipt-Delivery-Option in the received AS2 message is not a valid URL and does not conform to the specifications in the AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31499-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="31499-118">User Action</span></span>  
 <span data-ttu-id="31499-119">若要解决此错误，请将 AS2 消息中的 Receipt-Delivery-Option 更改为包含有效的 URL 并且符合 AS2 RFC 4130 的第 7.3 节中的规范，然后重新发送 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="31499-119">To resolve this error, have the Receipt-Delivery-Option in the AS2 message changed to include a valid URL and conform to the specifications in section 7.3 of the AS2 RFC 4130, and then resend the AS2 message.</span></span>