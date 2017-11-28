---
title: "在序列化期间遇到错误。 Edifact 交换其中不包含一组具有以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af693139-e4cd-4bcb-922c-79caa148d3b7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72108104b359d4d06233cf9a623097bfd046a0ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="7816a-103">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="7816a-103">Error encountered during serialization.</span></span> <span data-ttu-id="7816a-104">不包含组的 EDIFACT 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="7816a-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="7816a-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="7816a-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7816a-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="7816a-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7816a-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="7816a-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7816a-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7816a-108">Event ID</span></span>|-|  
|<span data-ttu-id="7816a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7816a-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7816a-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="7816a-110"> EDI</span></span>|  
|<span data-ttu-id="7816a-111">组件</span><span class="sxs-lookup"><span data-stu-id="7816a-111">Component</span></span>|<span data-ttu-id="7816a-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7816a-112">EDI Engine</span></span>|  
|<span data-ttu-id="7816a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7816a-113">Symbolic Name</span></span>|<span data-ttu-id="7816a-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="7816a-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>|  
|<span data-ttu-id="7816a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7816a-115">Message Text</span></span>|<span data-ttu-id="7816a-116">在序列化期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="7816a-116">Error encountered during serialization.</span></span> <span data-ttu-id="7816a-117">Edifact 交换不包含具有交换 id"{0}"，发件人 id {1} 的组，其中接收方 id {2} 具有以下错误：</span><span class="sxs-lookup"><span data-stu-id="7816a-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7816a-118">解释</span><span class="sxs-lookup"><span data-stu-id="7816a-118">Explanation</span></span>  
 <span data-ttu-id="7816a-119">此错误/警告/信息事件表明由于通过标识的交换指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="7816a-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="7816a-120">请注意，在交换不包含一组。</span><span class="sxs-lookup"><span data-stu-id="7816a-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7816a-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="7816a-121">User Action</span></span>  
 <span data-ttu-id="7816a-122">若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="7816a-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>