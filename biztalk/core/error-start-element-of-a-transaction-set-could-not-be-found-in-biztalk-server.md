---
title: 处理事务集，因为找不到事务集的开始元素后遇到错误 |Microsoft Docs
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
ms.openlocfilehash: 8748a34ce567ede355c0a49467afaa669f943dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346902"
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a><span data-ttu-id="29d19-102">处理事务集，因为找不到事务集的开始元素后遇到错误</span><span class="sxs-lookup"><span data-stu-id="29d19-102">Error encountered after processing Transaction Set(s) because the Start element of a Transaction set could not be found</span></span>
## <a name="details"></a><span data-ttu-id="29d19-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="29d19-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="29d19-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="29d19-104">Product Name</span></span>   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="29d19-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="29d19-105">Product Version</span></span> |                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    <span data-ttu-id="29d19-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="29d19-106">Event ID</span></span>     |                                                         -                                                         |
|  <span data-ttu-id="29d19-107">事件源</span><span class="sxs-lookup"><span data-stu-id="29d19-107">Event Source</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="29d19-108">EDI</span><span class="sxs-lookup"><span data-stu-id="29d19-108">EDI</span></span>               |
|    <span data-ttu-id="29d19-109">组件</span><span class="sxs-lookup"><span data-stu-id="29d19-109">Component</span></span>    |                                                    <span data-ttu-id="29d19-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="29d19-110">EDI Engine</span></span>                                                     |
|  <span data-ttu-id="29d19-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="29d19-111">Symbolic Name</span></span>  |                                             <span data-ttu-id="29d19-112">InvalidEfactBiboXmlFormat</span><span class="sxs-lookup"><span data-stu-id="29d19-112">InvalidEfactBiboXmlFormat</span></span>                                             |
|  <span data-ttu-id="29d19-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="29d19-113">Message Text</span></span>   | <span data-ttu-id="29d19-114">在处理后遇到错误{0}事务集。</span><span class="sxs-lookup"><span data-stu-id="29d19-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="29d19-115">找不到事务集的开始元素。</span><span class="sxs-lookup"><span data-stu-id="29d19-115">Start element of a Transaction set could not be found.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="29d19-116">解释</span><span class="sxs-lookup"><span data-stu-id="29d19-116">Explanation</span></span>  
 <span data-ttu-id="29d19-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的事务集，因为接收管道找不到 ST 或 UNH 标头。</span><span class="sxs-lookup"><span data-stu-id="29d19-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because the receive pipeline could not find the ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29d19-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="29d19-118">User Action</span></span>  
 <span data-ttu-id="29d19-119">若要解决此错误，请与交换的发件人，让他们确保中错误的事务集开头 ST01 或 UNH1 段。</span><span class="sxs-lookup"><span data-stu-id="29d19-119">To resolve this error, contact the sender of the interchange, and have them ensure that the transaction set in error begins with an ST01 or UNH1 segment.</span></span>