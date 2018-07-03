---
title: 授权值无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674585daa50f0adc0708a792b318bc0b736eca49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974430"
---
# <a name="invalid-authorization-value"></a><span data-ttu-id="6a3ab-102">授权值无效</span><span class="sxs-lookup"><span data-stu-id="6a3ab-102">Invalid Authorization Value</span></span>
## <a name="details"></a><span data-ttu-id="6a3ab-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6a3ab-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6a3ab-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6a3ab-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6a3ab-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="6a3ab-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6a3ab-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6a3ab-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6a3ab-107">事件源</span><span class="sxs-lookup"><span data-stu-id="6a3ab-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6a3ab-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6a3ab-108"> EDI</span></span> |
|    <span data-ttu-id="6a3ab-109">组件</span><span class="sxs-lookup"><span data-stu-id="6a3ab-109">Component</span></span>    |                                       <span data-ttu-id="6a3ab-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="6a3ab-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6a3ab-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="6a3ab-111">Symbolic Name</span></span>  |                       <span data-ttu-id="6a3ab-112">X12Ta1InvalidAuthorizationValueDescription</span><span class="sxs-lookup"><span data-stu-id="6a3ab-112">X12Ta1InvalidAuthorizationValueDescription</span></span>                       |
|  <span data-ttu-id="6a3ab-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="6a3ab-113">Message Text</span></span>   |                              <span data-ttu-id="6a3ab-114">授权值无效</span><span class="sxs-lookup"><span data-stu-id="6a3ab-114">Invalid Authorization Value</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="6a3ab-115">解释</span><span class="sxs-lookup"><span data-stu-id="6a3ab-115">Explanation</span></span>  
 <span data-ttu-id="6a3ab-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA02 中的“授权信息”的值不符合架构指定的数据类型 (X12_AN)，或者没有架构所需的位数 (10)。</span><span class="sxs-lookup"><span data-stu-id="6a3ab-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Information in ISA02 did not conform to the data type specified by the schema (X12_AN), or did not have the number of digits required by the schema (10).</span></span> <span data-ttu-id="6a3ab-117">架构是 BaseArtifacts.dll 中的 X12ServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="6a3ab-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a3ab-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="6a3ab-118">User Action</span></span>  
 <span data-ttu-id="6a3ab-119">若要解决此错误，请确保 ISA02 标头中的值符合 X12:AN 数据类型并且具有 10 位数（具有尾随空格），然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="6a3ab-119">To resolve this error, make sure that the value in the ISA02 header conforms to the X12:AN data type and has 10 digits (with trailing spaces), and then have the interchange resent.</span></span>