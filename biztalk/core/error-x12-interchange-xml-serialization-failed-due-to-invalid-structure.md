---
title: 由于结构无效，X12 交换 Xml 序列化失败。 查找 TransactionSet 或 GE，但找不到 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d058fdbb-6be5-499f-86f7-0eb8a85c5fb2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3d4081c901e95dbd1b9911b2cd957dbe7319761
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241717"
---
# <a name="x12-interchange-xml-serialization-failed-due-to-invalid-structure-looking-for-transactionset-or-ge-but-not-found"></a><span data-ttu-id="cdc99-103">由于结构无效，X12 交换 Xml 序列化失败。</span><span class="sxs-lookup"><span data-stu-id="cdc99-103">X12 interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="cdc99-104">查找 TransactionSet 或 GE，但没有找到</span><span class="sxs-lookup"><span data-stu-id="cdc99-104">Looking for TransactionSet or GE, but not found</span></span>
## <a name="details"></a><span data-ttu-id="cdc99-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="cdc99-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cdc99-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="cdc99-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cdc99-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="cdc99-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="cdc99-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cdc99-108">Event ID</span></span>|-|  
|<span data-ttu-id="cdc99-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cdc99-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cdc99-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="cdc99-110"> EDI</span></span>|  
|<span data-ttu-id="cdc99-111">组件</span><span class="sxs-lookup"><span data-stu-id="cdc99-111">Component</span></span>|<span data-ttu-id="cdc99-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="cdc99-112">EDI Engine</span></span>|  
|<span data-ttu-id="cdc99-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cdc99-113">Symbolic Name</span></span>|<span data-ttu-id="cdc99-114">X12TransactionSetOrGeNotFound</span><span class="sxs-lookup"><span data-stu-id="cdc99-114">X12TransactionSetOrGeNotFound</span></span>|  
|<span data-ttu-id="cdc99-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cdc99-115">Message Text</span></span>|<span data-ttu-id="cdc99-116">由于结构无效，X12 交换 Xml 序列化失败。</span><span class="sxs-lookup"><span data-stu-id="cdc99-116">X12 interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="cdc99-117">查找 TransactionSet 或 GE，但没有找到</span><span class="sxs-lookup"><span data-stu-id="cdc99-117">Looking for TransactionSet or GE, but not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cdc99-118">解释</span><span class="sxs-lookup"><span data-stu-id="cdc99-118">Explanation</span></span>  
 <span data-ttu-id="cdc99-119">此错误/警告/信息事件表明发送管道无法序列化传出的交换，因为交换的结构无效。</span><span class="sxs-lookup"><span data-stu-id="cdc99-119">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the structure of the interchange was invalid.</span></span> <span data-ttu-id="cdc99-120">原因可能是所需的标头或尾部不存在或者无效。</span><span class="sxs-lookup"><span data-stu-id="cdc99-120">The reason could be that the required headers or trailers are not present or are invalid.</span></span> <span data-ttu-id="cdc99-121">如果组中的事务集后没有另一个事务集或组尾部，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="cdc99-121">It could occur if a transaction set in a group is not followed by another transaction set or the group trailer.</span></span> <span data-ttu-id="cdc99-122">如果结构完整性检查失败，也可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="cdc99-122">It could also occur if structural integrity checks failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cdc99-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="cdc99-123">User Action</span></span>  
 <span data-ttu-id="cdc99-124">若要解决此错误，请验证交换的结构，确保组或事务集标头和尾部有效，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="cdc99-124">To resolve this error, verify the structure of the interchange, ensuring that the group or transaction set headers and trailers are valid, and then resend the interchange.</span></span>