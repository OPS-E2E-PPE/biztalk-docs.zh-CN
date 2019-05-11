---
title: 在序列化期间遇到错误。 不包含组的 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af693139-e4cd-4bcb-922c-79caa148d3b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2faef5b896440a6f412187016d145e33e2ab0868
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348885"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="ee1a6-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-103">Error encountered during serialization.</span></span> <span data-ttu-id="ee1a6-104">不包含组的 Edifact 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="ee1a6-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="ee1a6-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee1a6-105">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ee1a6-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="ee1a6-106">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="ee1a6-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="ee1a6-107">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="ee1a6-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ee1a6-108">Event ID</span></span>     |                                                                                              -                                                                                              |
|  <span data-ttu-id="ee1a6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ee1a6-109">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ee1a6-110">EDI</span><span class="sxs-lookup"><span data-stu-id="ee1a6-110">EDI</span></span>                                                    |
|    <span data-ttu-id="ee1a6-111">组件</span><span class="sxs-lookup"><span data-stu-id="ee1a6-111">Component</span></span>    |                                                                                         <span data-ttu-id="ee1a6-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ee1a6-112">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="ee1a6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ee1a6-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="ee1a6-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="ee1a6-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>                                                                          |
|  <span data-ttu-id="ee1a6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ee1a6-115">Message Text</span></span>   | <span data-ttu-id="ee1a6-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-116">Error encountered during serialization.</span></span> <span data-ttu-id="ee1a6-117">Edifact 交换不包含组中的，交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="ee1a6-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ee1a6-118">解释</span><span class="sxs-lookup"><span data-stu-id="ee1a6-118">Explanation</span></span>  
 <span data-ttu-id="ee1a6-119">此错误/警告/信息事件表明 EDI 发送管道遇到错误，由于通过标识的交换指出的错误序列化传出的 EDIFACT 交换时。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="ee1a6-120">请注意，交换不包含一组。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee1a6-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="ee1a6-121">User Action</span></span>  
 <span data-ttu-id="ee1a6-122">若要解决此错误，需要使用错误消息中的信息来标识交换中的错误，然后确定问题解决方案产品帮助中。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>