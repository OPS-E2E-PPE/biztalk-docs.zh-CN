---
title: 事务集不支持 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751b4bdff008a191a2367faea62fa92b6c15011b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278637"
---
# <a name="transaction-set-not-supported"></a><span data-ttu-id="ae12d-102">不支持事务集</span><span class="sxs-lookup"><span data-stu-id="ae12d-102">Transaction Set Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="ae12d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae12d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae12d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ae12d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ae12d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ae12d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ae12d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ae12d-106">Event ID</span></span>|-|  
|<span data-ttu-id="ae12d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ae12d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ae12d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ae12d-108"> EDI</span></span>|  
|<span data-ttu-id="ae12d-109">组件</span><span class="sxs-lookup"><span data-stu-id="ae12d-109">Component</span></span>|<span data-ttu-id="ae12d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ae12d-110">EDI Engine</span></span>|  
|<span data-ttu-id="ae12d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ae12d-111">Symbolic Name</span></span>|<span data-ttu-id="ae12d-112">X12TsNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="ae12d-112">X12TsNotSupportedDescription</span></span>|  
|<span data-ttu-id="ae12d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ae12d-113">Message Text</span></span>|<span data-ttu-id="ae12d-114">不支持事务集</span><span class="sxs-lookup"><span data-stu-id="ae12d-114">Transaction Set Not Supported</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae12d-115">解释</span><span class="sxs-lookup"><span data-stu-id="ae12d-115">Explanation</span></span>  
 <span data-ttu-id="ae12d-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为尚为该事务集的文档类型部署文档架构。</span><span class="sxs-lookup"><span data-stu-id="ae12d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a document schema has not been deployed for the document type of that transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae12d-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ae12d-117">User Action</span></span>  
 <span data-ttu-id="ae12d-118">若要解决此错误，请在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中为事务集的文档类型部署文档架构。</span><span class="sxs-lookup"><span data-stu-id="ae12d-118">To resolve this error, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] deploy a document schema for the document type of the transaction set.</span></span>