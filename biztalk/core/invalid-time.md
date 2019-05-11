---
title: 无效的时间 |Microsoft Docs
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
ms.openlocfilehash: c305afe09a7ff116d04554bb1c1962a137274945
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330094"
---
# <a name="invalid-time"></a><span data-ttu-id="55c1a-102">无效的时间</span><span class="sxs-lookup"><span data-stu-id="55c1a-102">Invalid Time</span></span>
## <a name="details"></a><span data-ttu-id="55c1a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="55c1a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="55c1a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="55c1a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="55c1a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="55c1a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="55c1a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="55c1a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="55c1a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="55c1a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="55c1a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="55c1a-108">EDI</span></span> |
|    <span data-ttu-id="55c1a-109">组件</span><span class="sxs-lookup"><span data-stu-id="55c1a-109">Component</span></span>    |                                       <span data-ttu-id="55c1a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="55c1a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="55c1a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="55c1a-111">Symbolic Name</span></span>  |                              <span data-ttu-id="55c1a-112">X12Ta1InvalidTimeDescription</span><span class="sxs-lookup"><span data-stu-id="55c1a-112">X12Ta1InvalidTimeDescription</span></span>                              |
|  <span data-ttu-id="55c1a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="55c1a-113">Message Text</span></span>   |                                      <span data-ttu-id="55c1a-114">无效的时间</span><span class="sxs-lookup"><span data-stu-id="55c1a-114">Invalid Time</span></span>                                      |
  
## <a name="explanation"></a><span data-ttu-id="55c1a-115">解释</span><span class="sxs-lookup"><span data-stu-id="55c1a-115">Explanation</span></span>  
 <span data-ttu-id="55c1a-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为数据元素中的时间值不符合指定的 EDI 架构或 GS05 字段标头在 X12 中的时间值的数据类型交换不符合服务架构 (baseartifacts.dll 中的 X12ServiceSchema)。</span><span class="sxs-lookup"><span data-stu-id="55c1a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a time value in a data element did not conform to the data type specified by the EDI schema or the time value in the GS05 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="55c1a-117">对于 X12，服务架构在 GS05 字段 X12_TM 数据类型和长度的四个和 8 个字符之间定义的时间。</span><span class="sxs-lookup"><span data-stu-id="55c1a-117">For X12, the service schema defines a time in the GS05 field as of the X12_TM data type and between four and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55c1a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="55c1a-118">User Action</span></span>  
 <span data-ttu-id="55c1a-119">若要解决此错误，请确保时间数据元素中的值符合 EDI 架构或时间值的 X12 交换符合服务架构在 GS05 标头中指定的数据类型，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="55c1a-119">To resolve this error, make sure that a time value in a data element conforms to the data type specified by the EDI schema or a time value in the GS05 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>