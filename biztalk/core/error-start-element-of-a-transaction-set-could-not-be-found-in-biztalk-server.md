---
title: 在处理事务集，因为找不到事务集的开始元素之后遇到错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b08046d1733aa8426909d7dddac4b10e48c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241805"
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a><span data-ttu-id="a902c-102">处理事务集后遇到错误，因为找不到事务集的 Start 元素</span><span class="sxs-lookup"><span data-stu-id="a902c-102">Error encountered after processing Transaction Set(s) because the Start element of a Transaction set could not be found</span></span>
## <a name="details"></a><span data-ttu-id="a902c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a902c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a902c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a902c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a902c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a902c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a902c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a902c-106">Event ID</span></span>|-|  
|<span data-ttu-id="a902c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a902c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a902c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a902c-108"> EDI</span></span>|  
|<span data-ttu-id="a902c-109">组件</span><span class="sxs-lookup"><span data-stu-id="a902c-109">Component</span></span>|<span data-ttu-id="a902c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a902c-110">EDI Engine</span></span>|  
|<span data-ttu-id="a902c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a902c-111">Symbolic Name</span></span>|<span data-ttu-id="a902c-112">InvalidEfactBiboXmlFormat</span><span class="sxs-lookup"><span data-stu-id="a902c-112">InvalidEfactBiboXmlFormat</span></span>|  
|<span data-ttu-id="a902c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="a902c-113">Message Text</span></span>|<span data-ttu-id="a902c-114">事务集处理 {0} 后遇到错误。</span><span class="sxs-lookup"><span data-stu-id="a902c-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="a902c-115">找不到事务集的开始元素。</span><span class="sxs-lookup"><span data-stu-id="a902c-115">Start element of a Transaction set could not be found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a902c-116">解释</span><span class="sxs-lookup"><span data-stu-id="a902c-116">Explanation</span></span>  
 <span data-ttu-id="a902c-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的事务集，因为接收管道找不到 ST 或 UNH 标头。</span><span class="sxs-lookup"><span data-stu-id="a902c-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because the receive pipeline could not find the ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a902c-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="a902c-118">User Action</span></span>  
 <span data-ttu-id="a902c-119">若要解决此错误，请与交换的发送方联系，让他们确保出错的事务集从 ST01 或 UNH1 段开始。</span><span class="sxs-lookup"><span data-stu-id="a902c-119">To resolve this error, contact the sender of the interchange, and have them ensure that the transaction set in error begins with an ST01 or UNH1 segment.</span></span>