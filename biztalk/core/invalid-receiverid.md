---
title: "无效的 ReceiverId |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feabf940-c49b-4f4a-8906-230dc8fb1b30
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d397c75efe1172f87def3dee92e20f4d0d7ef4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-receiverid"></a><span data-ttu-id="ee7ec-102">ReceiverId 无效</span><span class="sxs-lookup"><span data-stu-id="ee7ec-102">Invalid ReceiverId</span></span>
## <a name="details"></a><span data-ttu-id="ee7ec-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee7ec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee7ec-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ee7ec-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ee7ec-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ee7ec-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ee7ec-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ee7ec-106">Event ID</span></span>|-|  
|<span data-ttu-id="ee7ec-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ee7ec-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ee7ec-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ee7ec-108"> EDI</span></span>|  
|<span data-ttu-id="ee7ec-109">组件</span><span class="sxs-lookup"><span data-stu-id="ee7ec-109">Component</span></span>|<span data-ttu-id="ee7ec-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ee7ec-110">EDI Engine</span></span>|  
|<span data-ttu-id="ee7ec-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ee7ec-111">Symbolic Name</span></span>|<span data-ttu-id="ee7ec-112">X12Ta1InvalidReceiverIdDescription</span><span class="sxs-lookup"><span data-stu-id="ee7ec-112">X12Ta1InvalidReceiverIdDescription</span></span>|  
|<span data-ttu-id="ee7ec-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ee7ec-113">Message Text</span></span>|<span data-ttu-id="ee7ec-114">ReceiverId 无效</span><span class="sxs-lookup"><span data-stu-id="ee7ec-114">Invalid ReceiverId</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ee7ec-115">解释</span><span class="sxs-lookup"><span data-stu-id="ee7ec-115">Explanation</span></span>  
 <span data-ttu-id="ee7ec-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA08 字段中的接收方 ID 或 UNB3.1 字段中的收件人标识不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。</span><span class="sxs-lookup"><span data-stu-id="ee7ec-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Receiver ID in the ISA08 field or the Recipient Identification in the UNB3.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee7ec-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ee7ec-117">User Action</span></span>  
 <span data-ttu-id="ee7ec-118">若要解决此错误，请确保 ISA08 字段是 X12_AN 数据类型，并且是 15 个字符长 （带有或不带尾随空格） 的或者 UNB3.1 字段 EDIFACT_AN 数据类型，并且是 1 到 35 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="ee7ec-118">To resolve this error, make sure that the ISA08 field is of the X12_AN data type and is 15 characters long (with or without trailing spaces) or that the UNB3.1 field is of the EDIFACT_AN data type and is between 1 and 35 characters.</span></span> <span data-ttu-id="ee7ec-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="ee7ec-119">Have the interchange resent.</span></span>