---
title: 消息不包含 UNA 和分隔符的管道属性是不正确的格式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761d820-e09d-4949-bb41-da9e66054c60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6310c96f897126a498772f2147a20c84f7e926a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241837"
---
# <a name="message-did-not-contain-una-and-pipeline-property-for-delimiters-was-incorrect-format"></a><span data-ttu-id="ca61b-102">消息不包含 UNA 和管道属性，因为分隔符使用了不正确的格式</span><span class="sxs-lookup"><span data-stu-id="ca61b-102">Message did not contain UNA and pipeline property for delimiters was incorrect format</span></span>
## <a name="details"></a><span data-ttu-id="ca61b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca61b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca61b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ca61b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ca61b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ca61b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ca61b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ca61b-106">Event ID</span></span>|-|  
|<span data-ttu-id="ca61b-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ca61b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ca61b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ca61b-108"> EDI</span></span>|  
|<span data-ttu-id="ca61b-109">组件</span><span class="sxs-lookup"><span data-stu-id="ca61b-109">Component</span></span>|<span data-ttu-id="ca61b-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ca61b-110">EDI Engine</span></span>|  
|<span data-ttu-id="ca61b-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ca61b-111">Symbolic Name</span></span>|<span data-ttu-id="ca61b-112">EfactDelimiterIncorrectFormat</span><span class="sxs-lookup"><span data-stu-id="ca61b-112">EfactDelimiterIncorrectFormat</span></span>|  
|<span data-ttu-id="ca61b-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ca61b-113">Message Text</span></span>|<span data-ttu-id="ca61b-114">消息不包含 UNA 和管道属性，因为分隔符使用了不正确的格式“{0}”</span><span class="sxs-lookup"><span data-stu-id="ca61b-114">Message did not contain UNA and pipeline property for delimiters was incorrect format '{0}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca61b-115">解释</span><span class="sxs-lookup"><span data-stu-id="ca61b-115">Explanation</span></span>  
 <span data-ttu-id="ca61b-116">此错误/警告/信息事件表明接收管道无法处理传入的I EDIFACT 交换，因为它无法确定处理该交换所需的分隔符。</span><span class="sxs-lookup"><span data-stu-id="ca61b-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because it could not determine the separators required to process the interchange.</span></span> <span data-ttu-id="ca61b-117">如果交换没有 UNA 段并且 EfactDelimiters 管道属性没有定义足够的分隔符，则会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="ca61b-117">This can occur if the interchange does not have a UNA segment and the EfactDelimiters pipeline property does not adequately define the separators.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca61b-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ca61b-118">User Action</span></span>  
 <span data-ttu-id="ca61b-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ca61b-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="ca61b-120">确保交换具有为交换定义分隔符的 UNA 段，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="ca61b-120">Make sure that the interchange has a UNA segment that defines the separators for the interchange, and then resend the interchange.</span></span>  
  
2.  <span data-ttu-id="ca61b-121">通过打开 BizTalk Server 管理控制台，右键单击将接收交换的接收位置，单击“属性”，单击管道的省略号，然后输入包含分隔符值的字符串来为发送管道设置 EfactDelimiters 管道属性。</span><span class="sxs-lookup"><span data-stu-id="ca61b-121">Set the EfactDelimiters pipeline property for the send pipeline by opening the BizTalk Server Administration Console, right-clicking the receive location that will be receiving the interchange, clicking Properties, clicking the ellipsis for the pipeline, and then entering a string containing the values of the separators.</span></span>