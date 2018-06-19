---
title: 无效的测试指示器值 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d81d501-4020-4ff9-955c-5674a99d250b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 166ab446831243c58b1c12881393be1466399e0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261789"
---
# <a name="invalid-test-indicator-value"></a><span data-ttu-id="d2d33-102">无效的测试指示器值</span><span class="sxs-lookup"><span data-stu-id="d2d33-102">Invalid Test Indicator Value</span></span>
## <a name="details"></a><span data-ttu-id="d2d33-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2d33-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2d33-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d2d33-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d2d33-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d2d33-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d2d33-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d2d33-106">Event ID</span></span>|-|  
|<span data-ttu-id="d2d33-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d2d33-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d2d33-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d2d33-108"> EDI</span></span>|  
|<span data-ttu-id="d2d33-109">组件</span><span class="sxs-lookup"><span data-stu-id="d2d33-109">Component</span></span>|<span data-ttu-id="d2d33-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d2d33-110">EDI Engine</span></span>|  
|<span data-ttu-id="d2d33-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d2d33-111">Symbolic Name</span></span>|<span data-ttu-id="d2d33-112">X12Ta1InvalidTestIndicatorValueDescription</span><span class="sxs-lookup"><span data-stu-id="d2d33-112">X12Ta1InvalidTestIndicatorValueDescription</span></span>|  
|<span data-ttu-id="d2d33-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d2d33-113">Message Text</span></span>|<span data-ttu-id="d2d33-114">无效的测试指示器值</span><span class="sxs-lookup"><span data-stu-id="d2d33-114">Invalid Test Indicator Value</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2d33-115">解释</span><span class="sxs-lookup"><span data-stu-id="d2d33-115">Explanation</span></span>  
 <span data-ttu-id="d2d33-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 UNB11 字段中的测试指示器不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。</span><span class="sxs-lookup"><span data-stu-id="d2d33-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Test Indicator in the UNB11 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2d33-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d2d33-117">User Action</span></span>  
 <span data-ttu-id="d2d33-118">若要解决此错误，请确保 UNB11 字段为 EDIFACT_N 数据类型并且长度为 1 个字符。</span><span class="sxs-lookup"><span data-stu-id="d2d33-118">To resolve this error, make sure that the UNB11 field is of the EDIFACT_N data type and is 1 character in length.</span></span> <span data-ttu-id="d2d33-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="d2d33-119">Have the interchange resent.</span></span>