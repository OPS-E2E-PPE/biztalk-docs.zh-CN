---
title: 在序列化期间遇到错误。 X12 功能组发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b972993026822aa66b2863a3409e35f0a1b3f434
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009614"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a><span data-ttu-id="18563-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="18563-103">Error encountered during serialization.</span></span> <span data-ttu-id="18563-104">X 12 功能组发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="18563-104">The X12 functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="18563-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="18563-105">Details</span></span>  
  
|                 |                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="18563-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="18563-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| <span data-ttu-id="18563-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="18563-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    <span data-ttu-id="18563-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18563-108">Event ID</span></span>     |                                                                                        -                                                                                        |
|  <span data-ttu-id="18563-109">事件源</span><span class="sxs-lookup"><span data-stu-id="18563-109">Event Source</span></span>   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="18563-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="18563-110"> EDI</span></span>                                              |
|    <span data-ttu-id="18563-111">组件</span><span class="sxs-lookup"><span data-stu-id="18563-111">Component</span></span>    |                                                                                   <span data-ttu-id="18563-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="18563-112">EDI Engine</span></span>                                                                                    |
|  <span data-ttu-id="18563-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="18563-113">Symbolic Name</span></span>  |                                                                           <span data-ttu-id="18563-114">X12FunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="18563-114">X12FunctionalGroupSendError</span></span>                                                                           |
|  <span data-ttu-id="18563-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="18563-115">Message Text</span></span>   | <span data-ttu-id="18563-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="18563-116">Error encountered during serialization.</span></span> <span data-ttu-id="18563-117">X12 功能组 id 为 '{0}，交换中包含的 id{1}，发送方 id'{2}，接收方 id{3}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="18563-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="18563-118">解释</span><span class="sxs-lookup"><span data-stu-id="18563-118">Explanation</span></span>  
 <span data-ttu-id="18563-119">此错误/警告/信息事件表明由于通过标识的功能指明的错误，在序列化传出的 X12 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="18563-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18563-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="18563-120">User Action</span></span>  
 <span data-ttu-id="18563-121">若要解决此错误，请使用错误消息中的信息来标识功能组中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="18563-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the product help.</span></span>