---
title: 在解析过程中遇到错误。 不包含组的 Edifact 交换发生了以下错误 |Microsoft Docs
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
ms.openlocfilehash: 9c3ef771093a376349ee6656709f90d2ca7ece7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015309"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="e2f6e-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e2f6e-103">Error encountered during parsing.</span></span> <span data-ttu-id="e2f6e-104">不包含组的 EDIFACT 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="e2f6e-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="e2f6e-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="e2f6e-105">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e2f6e-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="e2f6e-106">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="e2f6e-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="e2f6e-107">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="e2f6e-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e2f6e-108">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="e2f6e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e2f6e-109">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e2f6e-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="e2f6e-110"> EDI</span></span>                                                 |
|    <span data-ttu-id="e2f6e-111">组件</span><span class="sxs-lookup"><span data-stu-id="e2f6e-111">Component</span></span>    |                                                                                      <span data-ttu-id="e2f6e-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e2f6e-112">EDI Engine</span></span>                                                                                       |
|  <span data-ttu-id="e2f6e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e2f6e-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="e2f6e-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="e2f6e-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span></span>                                                                      |
|  <span data-ttu-id="e2f6e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e2f6e-115">Message Text</span></span>   | <span data-ttu-id="e2f6e-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e2f6e-116">Error encountered during parsing.</span></span> <span data-ttu-id="e2f6e-117">Edifact 交换不包含组中的，交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="e2f6e-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e2f6e-118">解释</span><span class="sxs-lookup"><span data-stu-id="e2f6e-118">Explanation</span></span>  
 <span data-ttu-id="e2f6e-119">此错误/警告/信息事件表明由于指出的错误，解析传入的 EDIFACT 交换（不包含组）时，EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e2f6e-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange that did not contain a group because of the stated errors.</span></span> <span data-ttu-id="e2f6e-120">请注意，在 EDIFACT 交换中组是可选的。</span><span class="sxs-lookup"><span data-stu-id="e2f6e-120">Note that groups are optional in EDIFACT interchanges.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e2f6e-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="e2f6e-121">User Action</span></span>  
 <span data-ttu-id="e2f6e-122">若要解决此错误，请使用错误消息中的信息来标识错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2f6e-122">To resolve this error, use the information in the error message to identify the error and then determine the problem resolution in the product help.</span></span>