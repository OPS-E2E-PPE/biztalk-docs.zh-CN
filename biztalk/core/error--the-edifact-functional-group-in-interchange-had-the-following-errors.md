---
title: 解析期间遇到错误。 交换中的 Edifact 功能组发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b818d745366b84b41f1b44399fd699ebd68987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389010"
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a><span data-ttu-id="3c036-103">解析期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="3c036-103">Error encountered during parsing.</span></span> <span data-ttu-id="3c036-104">交换中的 Edifact 功能组发生以下错误</span><span class="sxs-lookup"><span data-stu-id="3c036-104">The Edifact functional group in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="3c036-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="3c036-105">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3c036-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="3c036-106">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="3c036-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="3c036-107">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="3c036-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3c036-108">Event ID</span></span>     |                                                                                       -                                                                                       |
|  <span data-ttu-id="3c036-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3c036-109">Event Source</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3c036-110">EDI</span><span class="sxs-lookup"><span data-stu-id="3c036-110">EDI</span></span>                                             |
|    <span data-ttu-id="3c036-111">组件</span><span class="sxs-lookup"><span data-stu-id="3c036-111">Component</span></span>    |                                                                                  <span data-ttu-id="3c036-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3c036-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="3c036-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3c036-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="3c036-114">EfactFunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="3c036-114">EfactFunctionalGroupReceiveError</span></span>                                                                        |
|  <span data-ttu-id="3c036-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3c036-115">Message Text</span></span>   | <span data-ttu-id="3c036-116">解析期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="3c036-116">Error encountered during parsing.</span></span> <span data-ttu-id="3c036-117">Edifact 功能组 id 为 '{0}，交换中包含的 id{1}，发送方 id'{2}，接收方 id{3}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="3c036-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3c036-118">解释</span><span class="sxs-lookup"><span data-stu-id="3c036-118">Explanation</span></span>  
 <span data-ttu-id="3c036-119">此错误/警告/信息事件表明 EDI 接收管道遇到错误，由于通过标识的功能组指出的错误分析传入的 EDIFACT 交换时。</span><span class="sxs-lookup"><span data-stu-id="3c036-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c036-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="3c036-120">User Action</span></span>  
 <span data-ttu-id="3c036-121">若要解决此错误，需要使用错误消息中的信息来标识组中的错误，然后确定问题解决方案产品帮助中。</span><span class="sxs-lookup"><span data-stu-id="3c036-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>