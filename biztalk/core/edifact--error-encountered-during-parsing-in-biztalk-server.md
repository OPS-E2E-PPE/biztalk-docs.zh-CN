---
title: 解析期间遇到错误。 不包含组的 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace43a641e08265852212d25750977ba5f95398c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350188"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="50144-103">解析期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="50144-103">Error encountered during parsing.</span></span> <span data-ttu-id="50144-104">不包含组的 Edifact 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="50144-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="50144-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="50144-105">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="50144-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="50144-106">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="50144-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="50144-107">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="50144-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="50144-108">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="50144-109">事件源</span><span class="sxs-lookup"><span data-stu-id="50144-109">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="50144-110">EDI</span><span class="sxs-lookup"><span data-stu-id="50144-110">EDI</span></span>                                                 |
|    <span data-ttu-id="50144-111">组件</span><span class="sxs-lookup"><span data-stu-id="50144-111">Component</span></span>    |                                                                                      <span data-ttu-id="50144-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="50144-112">EDI Engine</span></span>                                                                                       |
|  <span data-ttu-id="50144-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="50144-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="50144-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="50144-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span></span>                                                                      |
|  <span data-ttu-id="50144-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="50144-115">Message Text</span></span>   | <span data-ttu-id="50144-116">解析期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="50144-116">Error encountered during parsing.</span></span> <span data-ttu-id="50144-117">Edifact 交换不包含组中的，交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="50144-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="50144-118">解释</span><span class="sxs-lookup"><span data-stu-id="50144-118">Explanation</span></span>  
 <span data-ttu-id="50144-119">此错误/警告/信息事件表明 EDI 接收管道遇到错误时分析传入的 EDIFACT 交换不包含一组由于指出的错误。</span><span class="sxs-lookup"><span data-stu-id="50144-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange that did not contain a group because of the stated errors.</span></span> <span data-ttu-id="50144-120">请注意，组在 EDIFACT 交换中为可选。</span><span class="sxs-lookup"><span data-stu-id="50144-120">Note that groups are optional in EDIFACT interchanges.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50144-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="50144-121">User Action</span></span>  
 <span data-ttu-id="50144-122">若要解决此错误，需要使用错误消息中的信息来标识错误然后确定问题解决方案产品帮助中。</span><span class="sxs-lookup"><span data-stu-id="50144-122">To resolve this error, use the information in the error message to identify the error and then determine the problem resolution in the product help.</span></span>