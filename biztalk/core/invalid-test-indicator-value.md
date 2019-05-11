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
ms.openlocfilehash: 01525f716ab77b91c83e3baf884761b317d78ec1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381046"
---
# <a name="invalid-test-indicator-value"></a><span data-ttu-id="d4fe8-102">测试指示器值无效</span><span class="sxs-lookup"><span data-stu-id="d4fe8-102">Invalid Test Indicator Value</span></span>
## <a name="details"></a><span data-ttu-id="d4fe8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d4fe8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d4fe8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d4fe8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d4fe8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d4fe8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d4fe8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d4fe8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d4fe8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d4fe8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d4fe8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d4fe8-108">EDI</span></span> |
|    <span data-ttu-id="d4fe8-109">组件</span><span class="sxs-lookup"><span data-stu-id="d4fe8-109">Component</span></span>    |                                       <span data-ttu-id="d4fe8-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d4fe8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d4fe8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d4fe8-111">Symbolic Name</span></span>  |                       <span data-ttu-id="d4fe8-112">X12Ta1InvalidTestIndicatorValueDescription</span><span class="sxs-lookup"><span data-stu-id="d4fe8-112">X12Ta1InvalidTestIndicatorValueDescription</span></span>                       |
|  <span data-ttu-id="d4fe8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d4fe8-113">Message Text</span></span>   |                              <span data-ttu-id="d4fe8-114">测试指示器值无效</span><span class="sxs-lookup"><span data-stu-id="d4fe8-114">Invalid Test Indicator Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="d4fe8-115">解释</span><span class="sxs-lookup"><span data-stu-id="d4fe8-115">Explanation</span></span>  
 <span data-ttu-id="d4fe8-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为 UNB11 字段中的测试指示器不符合的数据类型和服务架构 （通过建立的数字个数X12ServiceSchema 或 EdifactServiceSchema 在 BaseArtifacts.dll 中）。</span><span class="sxs-lookup"><span data-stu-id="d4fe8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Test Indicator in the UNB11 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4fe8-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d4fe8-117">User Action</span></span>  
 <span data-ttu-id="d4fe8-118">若要解决此错误，请确保 UNB11 字段为 EDIFACT_N 数据类型为 1 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="d4fe8-118">To resolve this error, make sure that the UNB11 field is of the EDIFACT_N data type and is 1 character in length.</span></span> <span data-ttu-id="d4fe8-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="d4fe8-119">Have the interchange resent.</span></span>