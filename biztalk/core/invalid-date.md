---
title: "无效的日期 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a41da9c5-9dcf-44cd-be5b-922e6c267ec3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 259456e781f5f5255f9fed8a51c8eb0569dd57b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-date"></a><span data-ttu-id="8796f-102">日期无效</span><span class="sxs-lookup"><span data-stu-id="8796f-102">Invalid Date</span></span>
## <a name="details"></a><span data-ttu-id="8796f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8796f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8796f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8796f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8796f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8796f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8796f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8796f-106">Event ID</span></span>|-|  
|<span data-ttu-id="8796f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8796f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8796f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8796f-108"> EDI</span></span>|  
|<span data-ttu-id="8796f-109">组件</span><span class="sxs-lookup"><span data-stu-id="8796f-109">Component</span></span>|<span data-ttu-id="8796f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="8796f-110">EDI Engine</span></span>|  
|<span data-ttu-id="8796f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8796f-111">Symbolic Name</span></span>|<span data-ttu-id="8796f-112">X12DeInvalidDateDescription</span><span class="sxs-lookup"><span data-stu-id="8796f-112">X12DeInvalidDateDescription</span></span>|  
|<span data-ttu-id="8796f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8796f-113">Message Text</span></span>|<span data-ttu-id="8796f-114">日期无效</span><span class="sxs-lookup"><span data-stu-id="8796f-114">Invalid Date</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8796f-115">解释</span><span class="sxs-lookup"><span data-stu-id="8796f-115">Explanation</span></span>  
 <span data-ttu-id="8796f-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传出的交换，因为数据元素中的某个日期值不符合 EDI 架构指定的数据类型或者 X12 交换中 GS04 字段标头的此日期值不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema）。</span><span class="sxs-lookup"><span data-stu-id="8796f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a date value in a data element did not conform to the data type specified by the EDI schema or the date value in the GS04 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="8796f-117">对于 X12，服务架构在 GS04 字段中定义了一个 X12_DT 数据类型的日期，字符长度介于 6 和 8 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="8796f-117">For X12, the service schema defines a date in the GS04 field as of the X12_DT data type and between six and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8796f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8796f-118">User Action</span></span>  
 <span data-ttu-id="8796f-119">若要解决此错误，请确保数据元素中的时间值符合 EDI 架构指定的数据类型或 X12 交换的 GS04 标头中的日期值符合服务架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="8796f-119">To resolve this error, make sure that the time value in a data element conforms to the data type specified by the EDI schema or the date value in the GS04 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>