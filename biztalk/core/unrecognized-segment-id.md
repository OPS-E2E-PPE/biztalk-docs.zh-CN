---
title: 无法识别的段 ID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a3990ce9a1d913cdb9840605c6f0e34623db8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007535"
---
# <a name="unrecognized-segment-id"></a><span data-ttu-id="e42e2-102">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="e42e2-102">Unrecognized segment ID</span></span>
## <a name="details"></a><span data-ttu-id="e42e2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e42e2-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e42e2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e42e2-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e42e2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e42e2-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e42e2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e42e2-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e42e2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e42e2-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e42e2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e42e2-108"> EDI</span></span> |
|    <span data-ttu-id="e42e2-109">组件</span><span class="sxs-lookup"><span data-stu-id="e42e2-109">Component</span></span>    |                                       <span data-ttu-id="e42e2-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e42e2-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e42e2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e42e2-111">Symbolic Name</span></span>  | <span data-ttu-id="e42e2-112">EfactUnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="e42e2-112">EfactUnrecognizedSegmentIDDescription</span></span><br /><br /> <span data-ttu-id="e42e2-113">X12UnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="e42e2-113">X12UnrecognizedSegmentIDDescription</span></span>  |
|  <span data-ttu-id="e42e2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="e42e2-114">Message Text</span></span>   |                                <span data-ttu-id="e42e2-115">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="e42e2-115">Unrecognized segment ID</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="e42e2-116">解释</span><span class="sxs-lookup"><span data-stu-id="e42e2-116">Explanation</span></span>  
 <span data-ttu-id="e42e2-117">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中事务集的某个段不是由相应的文档架构定义的。</span><span class="sxs-lookup"><span data-stu-id="e42e2-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a segment in a transaction set in the interchange was not defined by the corresponding document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e42e2-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e42e2-118">User Action</span></span>  
 <span data-ttu-id="e42e2-119">若要解决此错误，请让交换的发送方删除无法识别的段，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e42e2-119">To resolve this error, have the sender of the interchange remove the unrecognized segment and resend the interchange.</span></span>