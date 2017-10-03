---
title: "找到的数据元素过少 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8244f927cb7aff9cd0cb517dd132b986d53d67f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="too-few-data-elements-found"></a><span data-ttu-id="498d9-102">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="498d9-102">Too few data elements found</span></span>
## <a name="details"></a><span data-ttu-id="498d9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="498d9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="498d9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="498d9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="498d9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="498d9-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="498d9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="498d9-106">Event ID</span></span>|-|  
|<span data-ttu-id="498d9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="498d9-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="498d9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="498d9-108"> EDI</span></span>|  
|<span data-ttu-id="498d9-109">组件</span><span class="sxs-lookup"><span data-stu-id="498d9-109">Component</span></span>|<span data-ttu-id="498d9-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="498d9-110">EDI Engine</span></span>|  
|<span data-ttu-id="498d9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="498d9-111">Symbolic Name</span></span>|<span data-ttu-id="498d9-112">X12FeTooFewDataElementsFoundDescription</span><span class="sxs-lookup"><span data-stu-id="498d9-112">X12FeTooFewDataElementsFoundDescription</span></span>|  
|<span data-ttu-id="498d9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="498d9-113">Message Text</span></span>|<span data-ttu-id="498d9-114">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="498d9-114">Too few data elements found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="498d9-115">解释</span><span class="sxs-lookup"><span data-stu-id="498d9-115">Explanation</span></span>  
 <span data-ttu-id="498d9-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传入的交换，因为交换中的某个段包含的数据元素少于文档架构或服务架构所需的数据元素。</span><span class="sxs-lookup"><span data-stu-id="498d9-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained fewer data elements than required by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="498d9-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="498d9-117">User Action</span></span>  
 <span data-ttu-id="498d9-118">若要解决此错误，请让交换的发送方确保段包含所需的数据元素数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="498d9-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, and then resend the interchange.</span></span>