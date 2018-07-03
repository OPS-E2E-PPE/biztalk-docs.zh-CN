---
title: 无效的测试指示器值 |Microsoft Docs
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
ms.openlocfilehash: 89245453e7b1b7d8c40e33bf25a3ab3aac1933db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991022"
---
# <a name="invalid-test-indicator-value"></a><span data-ttu-id="0948c-102">测试指示器值无效</span><span class="sxs-lookup"><span data-stu-id="0948c-102">Invalid Test Indicator Value</span></span>
## <a name="details"></a><span data-ttu-id="0948c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0948c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0948c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0948c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0948c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0948c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0948c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0948c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0948c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0948c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0948c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0948c-108"> EDI</span></span> |
|    <span data-ttu-id="0948c-109">组件</span><span class="sxs-lookup"><span data-stu-id="0948c-109">Component</span></span>    |                                       <span data-ttu-id="0948c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0948c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0948c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0948c-111">Symbolic Name</span></span>  |                       <span data-ttu-id="0948c-112">X12Ta1InvalidTestIndicatorValueDescription</span><span class="sxs-lookup"><span data-stu-id="0948c-112">X12Ta1InvalidTestIndicatorValueDescription</span></span>                       |
|  <span data-ttu-id="0948c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0948c-113">Message Text</span></span>   |                              <span data-ttu-id="0948c-114">测试指示器值无效</span><span class="sxs-lookup"><span data-stu-id="0948c-114">Invalid Test Indicator Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="0948c-115">解释</span><span class="sxs-lookup"><span data-stu-id="0948c-115">Explanation</span></span>  
 <span data-ttu-id="0948c-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 UNB11 字段中的测试指示器不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。</span><span class="sxs-lookup"><span data-stu-id="0948c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Test Indicator in the UNB11 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0948c-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0948c-117">User Action</span></span>  
 <span data-ttu-id="0948c-118">若要解决此错误，请确保 UNB11 字段为 EDIFACT_N 数据类型并且长度为 1 个字符。</span><span class="sxs-lookup"><span data-stu-id="0948c-118">To resolve this error, make sure that the UNB11 field is of the EDIFACT_N data type and is 1 character in length.</span></span> <span data-ttu-id="0948c-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="0948c-119">Have the interchange resent.</span></span>