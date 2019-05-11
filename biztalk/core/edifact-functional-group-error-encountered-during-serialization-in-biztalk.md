---
title: 在序列化期间遇到错误。 Edifact 功能组发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e8750a1ae4070543a9463b95827f14d10ab5180
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530791"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a><span data-ttu-id="1eefc-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="1eefc-103">Error encountered during serialization.</span></span> <span data-ttu-id="1eefc-104">Edifact 功能组发生以下错误</span><span class="sxs-lookup"><span data-stu-id="1eefc-104">The Edifact functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="1eefc-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="1eefc-105">Details</span></span>  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1eefc-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="1eefc-106">Product Name</span></span>   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| <span data-ttu-id="1eefc-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="1eefc-107">Product Version</span></span> |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    <span data-ttu-id="1eefc-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1eefc-108">Event ID</span></span>     |                                                                                          -                                                                                          |
|  <span data-ttu-id="1eefc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1eefc-109">Event Source</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1eefc-110">EDI</span><span class="sxs-lookup"><span data-stu-id="1eefc-110">EDI</span></span>                                                |
|    <span data-ttu-id="1eefc-111">组件</span><span class="sxs-lookup"><span data-stu-id="1eefc-111">Component</span></span>    |                                                                                     <span data-ttu-id="1eefc-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1eefc-112">EDI Engine</span></span>                                                                                      |
|  <span data-ttu-id="1eefc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1eefc-113">Symbolic Name</span></span>  |                                                                            <span data-ttu-id="1eefc-114">EfactFunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="1eefc-114">EfactFunctionalGroupSendError</span></span>                                                                            |
|  <span data-ttu-id="1eefc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1eefc-115">Message Text</span></span>   | <span data-ttu-id="1eefc-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="1eefc-116">Error encountered during serialization.</span></span> <span data-ttu-id="1eefc-117">Edifact 功能组 id 为 '{0}，交换中包含的 id{1}，发送方 id'{2}，接收方 id{3}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="1eefc-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1eefc-118">解释</span><span class="sxs-lookup"><span data-stu-id="1eefc-118">Explanation</span></span>  
 <span data-ttu-id="1eefc-119">此错误/警告/信息事件表明 EDI 发送管道遇到错误，由于指出的错误与组序列化传出的 EDIFACT 交换中的一个功能组时。</span><span class="sxs-lookup"><span data-stu-id="1eefc-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing a functional group within an outgoing EDIFACT interchange because of the stated errors with the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1eefc-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="1eefc-120">User Action</span></span>  
 <span data-ttu-id="1eefc-121">若要解决此错误，需要使用错误消息中的信息来标识功能组中的错误，然后确定问题解决方案的文档中。</span><span class="sxs-lookup"><span data-stu-id="1eefc-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the documentation.</span></span>