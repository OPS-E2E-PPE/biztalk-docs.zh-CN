---
title: 找到的数据元素过少 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d82a5015d2285437363f178f88c165e3ba6333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984774"
---
# <a name="too-few-data-elements-found"></a><span data-ttu-id="c6ae7-102">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="c6ae7-102">Too few data elements found</span></span>
## <a name="details"></a><span data-ttu-id="c6ae7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6ae7-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c6ae7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c6ae7-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c6ae7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c6ae7-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c6ae7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c6ae7-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c6ae7-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c6ae7-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c6ae7-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c6ae7-108"> EDI</span></span> |
|    <span data-ttu-id="c6ae7-109">组件</span><span class="sxs-lookup"><span data-stu-id="c6ae7-109">Component</span></span>    |                                       <span data-ttu-id="c6ae7-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c6ae7-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c6ae7-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c6ae7-111">Symbolic Name</span></span>  |                        <span data-ttu-id="c6ae7-112">X12FeTooFewDataElementsFoundDescription</span><span class="sxs-lookup"><span data-stu-id="c6ae7-112">X12FeTooFewDataElementsFoundDescription</span></span>                         |
|  <span data-ttu-id="c6ae7-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c6ae7-113">Message Text</span></span>   |                              <span data-ttu-id="c6ae7-114">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="c6ae7-114">Too few data elements found</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="c6ae7-115">解释</span><span class="sxs-lookup"><span data-stu-id="c6ae7-115">Explanation</span></span>  
 <span data-ttu-id="c6ae7-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传入的交换，因为交换中的某个段包含的数据元素少于文档架构或服务架构所需的数据元素。</span><span class="sxs-lookup"><span data-stu-id="c6ae7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained fewer data elements than required by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6ae7-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c6ae7-117">User Action</span></span>  
 <span data-ttu-id="c6ae7-118">若要解决此错误，请让交换的发送方确保段包含所需的数据元素数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="c6ae7-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, and then resend the interchange.</span></span>