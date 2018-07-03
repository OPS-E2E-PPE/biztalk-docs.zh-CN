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
ms.openlocfilehash: eb97be1be3c623673d2429a20598c748a8d73de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000822"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="cd354-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="cd354-103">Error encountered during serialization.</span></span> <span data-ttu-id="cd354-104">EDIFACT 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="cd354-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="cd354-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="cd354-105">Details</span></span>  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cd354-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="cd354-106">Product Name</span></span>   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| <span data-ttu-id="cd354-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="cd354-107">Product Version</span></span> |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    <span data-ttu-id="cd354-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cd354-108">Event ID</span></span>     |                                                                        -                                                                         |
|  <span data-ttu-id="cd354-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cd354-109">Event Source</span></span>   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cd354-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="cd354-110"> EDI</span></span>                              |
|    <span data-ttu-id="cd354-111">组件</span><span class="sxs-lookup"><span data-stu-id="cd354-111">Component</span></span>    |                                                                    <span data-ttu-id="cd354-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="cd354-112">EDI Engine</span></span>                                                                    |
|  <span data-ttu-id="cd354-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cd354-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="cd354-114">EfactInterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="cd354-114">EfactInterchangeSendError</span></span>                                                             |
|  <span data-ttu-id="cd354-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cd354-115">Message Text</span></span>   | <span data-ttu-id="cd354-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="cd354-116">Error encountered during serialization.</span></span> <span data-ttu-id="cd354-117">Edifact 交换中的 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="cd354-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cd354-118">解释</span><span class="sxs-lookup"><span data-stu-id="cd354-118">Explanation</span></span>  
 <span data-ttu-id="cd354-119">此错误/警告/信息事件表明由于通过标识的交换指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="cd354-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd354-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="cd354-120">User Action</span></span>  
 <span data-ttu-id="cd354-121">若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="cd354-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>