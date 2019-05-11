---
title: 在序列化期间遇到错误。 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346135947ea0b0f154178d67f29335a13a95526a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350024"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="1192e-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="1192e-103">Error encountered during serialization.</span></span> <span data-ttu-id="1192e-104">Edifact 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="1192e-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="1192e-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="1192e-105">Details</span></span>  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1192e-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="1192e-106">Product Name</span></span>   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| <span data-ttu-id="1192e-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="1192e-107">Product Version</span></span> |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    <span data-ttu-id="1192e-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1192e-108">Event ID</span></span>     |                                                                        -                                                                         |
|  <span data-ttu-id="1192e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1192e-109">Event Source</span></span>   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1192e-110">EDI</span><span class="sxs-lookup"><span data-stu-id="1192e-110">EDI</span></span>                              |
|    <span data-ttu-id="1192e-111">组件</span><span class="sxs-lookup"><span data-stu-id="1192e-111">Component</span></span>    |                                                                    <span data-ttu-id="1192e-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1192e-112">EDI Engine</span></span>                                                                    |
|  <span data-ttu-id="1192e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1192e-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="1192e-114">EfactInterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="1192e-114">EfactInterchangeSendError</span></span>                                                             |
|  <span data-ttu-id="1192e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1192e-115">Message Text</span></span>   | <span data-ttu-id="1192e-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="1192e-116">Error encountered during serialization.</span></span> <span data-ttu-id="1192e-117">Edifact 交换中的 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="1192e-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1192e-118">解释</span><span class="sxs-lookup"><span data-stu-id="1192e-118">Explanation</span></span>  
 <span data-ttu-id="1192e-119">此错误/警告/信息事件表明 EDI 发送管道遇到错误，由于通过标识的交换指出的错误序列化传出的 EDIFACT 交换时。</span><span class="sxs-lookup"><span data-stu-id="1192e-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1192e-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="1192e-120">User Action</span></span>  
 <span data-ttu-id="1192e-121">若要解决此错误，需要使用错误消息中的信息来标识交换中的错误，然后确定问题解决方案产品帮助中。</span><span class="sxs-lookup"><span data-stu-id="1192e-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>