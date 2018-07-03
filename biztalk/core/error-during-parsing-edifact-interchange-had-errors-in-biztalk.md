---
title: 在解析过程中遇到错误。 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d891abe7ca75dbbe9052f221970e235b390269
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988206"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="0a9cf-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="0a9cf-103">Error encountered during parsing.</span></span> <span data-ttu-id="0a9cf-104">EDIFACT 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="0a9cf-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="0a9cf-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a9cf-105">Details</span></span>  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a9cf-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="0a9cf-106">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="0a9cf-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="0a9cf-107">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    <span data-ttu-id="0a9cf-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0a9cf-108">Event ID</span></span>     |                                                                     -                                                                      |
|  <span data-ttu-id="0a9cf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0a9cf-109">Event Source</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a9cf-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="0a9cf-110"> EDI</span></span>                           |
|    <span data-ttu-id="0a9cf-111">组件</span><span class="sxs-lookup"><span data-stu-id="0a9cf-111">Component</span></span>    |                                                                 <span data-ttu-id="0a9cf-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0a9cf-112">EDI Engine</span></span>                                                                 |
|  <span data-ttu-id="0a9cf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0a9cf-113">Symbolic Name</span></span>  |                                                        <span data-ttu-id="0a9cf-114">EfactInterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="0a9cf-114">EfactInterchangeReceiveError</span></span>                                                        |
|  <span data-ttu-id="0a9cf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0a9cf-115">Message Text</span></span>   | <span data-ttu-id="0a9cf-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="0a9cf-116">Error encountered during parsing.</span></span> <span data-ttu-id="0a9cf-117">Edifact 交换中的 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="0a9cf-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0a9cf-118">解释</span><span class="sxs-lookup"><span data-stu-id="0a9cf-118">Explanation</span></span>  
 <span data-ttu-id="0a9cf-119">此错误/警告/信息事件表明由于在交换中指出的错误，在分析传入的 EDIFACT 交换时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="0a9cf-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a9cf-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="0a9cf-120">User Action</span></span>  
 <span data-ttu-id="0a9cf-121">若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="0a9cf-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>