---
title: 无效的时间 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6942eb77-3ef1-460c-ac4f-8f1339c25d1b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aae508a945cc6934e83408b2a9b78c324947e0e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261973"
---
# <a name="invalid-time"></a><span data-ttu-id="1e900-102">无效的时间</span><span class="sxs-lookup"><span data-stu-id="1e900-102">Invalid Time</span></span>
## <a name="details"></a><span data-ttu-id="1e900-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1e900-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e900-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1e900-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1e900-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1e900-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1e900-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1e900-106">Event ID</span></span>|-|  
|<span data-ttu-id="1e900-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1e900-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1e900-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1e900-108"> EDI</span></span>|  
|<span data-ttu-id="1e900-109">组件</span><span class="sxs-lookup"><span data-stu-id="1e900-109">Component</span></span>|<span data-ttu-id="1e900-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1e900-110">EDI Engine</span></span>|  
|<span data-ttu-id="1e900-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1e900-111">Symbolic Name</span></span>|<span data-ttu-id="1e900-112">X12Ta1InvalidTimeDescription</span><span class="sxs-lookup"><span data-stu-id="1e900-112">X12Ta1InvalidTimeDescription</span></span>|  
|<span data-ttu-id="1e900-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1e900-113">Message Text</span></span>|<span data-ttu-id="1e900-114">无效的时间</span><span class="sxs-lookup"><span data-stu-id="1e900-114">Invalid Time</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1e900-115">解释</span><span class="sxs-lookup"><span data-stu-id="1e900-115">Explanation</span></span>  
 <span data-ttu-id="1e900-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为数据元素中的某个时间值不符合 EDI 架构指定的数据类型或者 X12 交换中 GS05 字段标头的此时间值不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema）。</span><span class="sxs-lookup"><span data-stu-id="1e900-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a time value in a data element did not conform to the data type specified by the EDI schema or the time value in the GS05 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="1e900-117">对于 X12，服务架构在 GS05 字段中定义了一个 X12_TM 数据类型的时间，字符长度介于 4 和 8 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="1e900-117">For X12, the service schema defines a time in the GS05 field as of the X12_TM data type and between four and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e900-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="1e900-118">User Action</span></span>  
 <span data-ttu-id="1e900-119">若要解决此错误，请确保数据元素中的时间值符合 EDI 架构指定的数据类型或 X12 交换的 GS05 标头中的时间值符合服务架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="1e900-119">To resolve this error, make sure that a time value in a data element conforms to the data type specified by the EDI schema or a time value in the GS05 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>