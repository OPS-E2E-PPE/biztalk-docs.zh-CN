---
title: Edifact 交换 Xml 序列化失败由于无效的结构、 没有 transactionSet 或修剪 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ce1c219-f2ed-46c1-ae4b-8a4206f7cd01
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5c6aae4bc3ed16afffadec774eaeac9ed64808d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241725"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a><span data-ttu-id="e3dad-102">由于结构无效，无 transactionSet 或 UNE，EDIFACT 交换 XML 序列化失败</span><span class="sxs-lookup"><span data-stu-id="e3dad-102">Edifact interchange Xml serialization failed due to invalid structure, no transactionSet or UNE</span></span>
## <a name="details"></a><span data-ttu-id="e3dad-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3dad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3dad-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e3dad-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e3dad-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e3dad-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e3dad-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e3dad-106">Event ID</span></span>|-|  
|<span data-ttu-id="e3dad-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e3dad-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e3dad-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e3dad-108"> EDI</span></span>|  
|<span data-ttu-id="e3dad-109">组件</span><span class="sxs-lookup"><span data-stu-id="e3dad-109">Component</span></span>|<span data-ttu-id="e3dad-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e3dad-110">EDI Engine</span></span>|  
|<span data-ttu-id="e3dad-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e3dad-111">Symbolic Name</span></span>|<span data-ttu-id="e3dad-112">EfactTransactionSetOrUneNotFound</span><span class="sxs-lookup"><span data-stu-id="e3dad-112">EfactTransactionSetOrUneNotFound</span></span>|  
|<span data-ttu-id="e3dad-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e3dad-113">Message Text</span></span>|<span data-ttu-id="e3dad-114">由于结构无效，Edifact 交换 Xml 序列化失败。</span><span class="sxs-lookup"><span data-stu-id="e3dad-114">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="e3dad-115">查找 TransactionSet 或 UNE，但没有找到</span><span class="sxs-lookup"><span data-stu-id="e3dad-115">Looking for TransactionSet or UNE, but not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e3dad-116">解释</span><span class="sxs-lookup"><span data-stu-id="e3dad-116">Explanation</span></span>  
 <span data-ttu-id="e3dad-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一个段既不是 UNA 段也不是 UNB 段。</span><span class="sxs-lookup"><span data-stu-id="e3dad-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA or a UNB segment.</span></span> <span data-ttu-id="e3dad-118">UNA 段是可选的；UNB 段是必需的。</span><span class="sxs-lookup"><span data-stu-id="e3dad-118">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3dad-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="e3dad-119">User Action</span></span>  
 <span data-ttu-id="e3dad-120">若要解决此错误，请确保交换的发送方结构化消息，以便组中的事务集后面跟随另一个事务集或 UNE 段。</span><span class="sxs-lookup"><span data-stu-id="e3dad-120">To resolve this error, ensure that the sender of the interchange structures the message such that a transaction set in a group is either followed by another transaction set or a UNE segment.</span></span> <span data-ttu-id="e3dad-121">然后，让发送方重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e3dad-121">Have the sender then resend the interchange.</span></span>