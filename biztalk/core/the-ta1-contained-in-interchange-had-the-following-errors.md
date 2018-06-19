---
title: 包含在交换 TA1 出现以下错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bd7486d25e2c94fc809e6dc50c43359c152b70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278629"
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a><span data-ttu-id="797a7-102">交换中包含的 TA1 发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="797a7-102">The TA1 contained in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="797a7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="797a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="797a7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="797a7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="797a7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="797a7-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="797a7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="797a7-106">Event ID</span></span>|-|  
|<span data-ttu-id="797a7-107">事件源</span><span class="sxs-lookup"><span data-stu-id="797a7-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="797a7-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="797a7-108"> EDI</span></span>|  
|<span data-ttu-id="797a7-109">组件</span><span class="sxs-lookup"><span data-stu-id="797a7-109">Component</span></span>|<span data-ttu-id="797a7-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="797a7-110">EDI Engine</span></span>|  
|<span data-ttu-id="797a7-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="797a7-111">Symbolic Name</span></span>|<span data-ttu-id="797a7-112">X12TA1Error</span><span class="sxs-lookup"><span data-stu-id="797a7-112">X12TA1Error</span></span>|  
|<span data-ttu-id="797a7-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="797a7-113">Message Text</span></span>|<span data-ttu-id="797a7-114">{0} TA1 包含 id 为 {1} 发件人 id {2} 交换中，接收方 id {3} 出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="797a7-114">The {0} TA1 contained in interchange with id '{1}', sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="797a7-115">解释</span><span class="sxs-lookup"><span data-stu-id="797a7-115">Explanation</span></span>  
 <span data-ttu-id="797a7-116">此错误/警告/信息事件表明由于指出的错误条件，接收管道无法处理传入的  TA1  确认。</span><span class="sxs-lookup"><span data-stu-id="797a7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming TA1 acknowledgment because of the indicated error condition.</span></span> <span data-ttu-id="797a7-117">此错误可能表明确认不符合 TA1Schema。</span><span class="sxs-lookup"><span data-stu-id="797a7-117">This may indicate that the acknowledgment does not conform to the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="797a7-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="797a7-118">User Action</span></span>  
 <span data-ttu-id="797a7-119">若要解决此错误，请让确认的发送方解决确认中的问题，从而确保确认符合 TA1Schema，然后重新发送确认。</span><span class="sxs-lookup"><span data-stu-id="797a7-119">To resolve this error, have the sender of the acknowledgment resolve the issue with the acknowledgment, ensuring that the acknowledgment conforms to the TA1Schema, and then resend the acknowledgment.</span></span>