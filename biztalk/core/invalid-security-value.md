---
title: 无效的安全值 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee380da7-c05e-4b9b-84ee-f7ffee90eb0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e41315400ee2b0eae099439237356b61676b26cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257205"
---
# <a name="invalid-security-value"></a><span data-ttu-id="5b700-102">安全值无效</span><span class="sxs-lookup"><span data-stu-id="5b700-102">Invalid Security Value</span></span>
## <a name="details"></a><span data-ttu-id="5b700-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b700-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b700-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5b700-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5b700-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5b700-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5b700-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5b700-106">Event ID</span></span>|-|  
|<span data-ttu-id="5b700-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5b700-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5b700-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5b700-108"> EDI</span></span>|  
|<span data-ttu-id="5b700-109">组件</span><span class="sxs-lookup"><span data-stu-id="5b700-109">Component</span></span>|<span data-ttu-id="5b700-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="5b700-110">EDI Engine</span></span>|  
|<span data-ttu-id="5b700-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5b700-111">Symbolic Name</span></span>|<span data-ttu-id="5b700-112">X12Ta1InvalidSecurityValueDescription</span><span class="sxs-lookup"><span data-stu-id="5b700-112">X12Ta1InvalidSecurityValueDescription</span></span>|  
|<span data-ttu-id="5b700-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="5b700-113">Message Text</span></span>|<span data-ttu-id="5b700-114">安全值无效</span><span class="sxs-lookup"><span data-stu-id="5b700-114">Invalid Security Value</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b700-115">解释</span><span class="sxs-lookup"><span data-stu-id="5b700-115">Explanation</span></span>  
 <span data-ttu-id="5b700-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA04 字段中的安全信息或 UNB6.1 字段中的收件人引用密码值不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。</span><span class="sxs-lookup"><span data-stu-id="5b700-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Information in the ISA04 field or the Recipient Reference Password Value in the UNB6.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b700-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="5b700-117">User Action</span></span>  
 <span data-ttu-id="5b700-118">若要解决此错误，请确保 ISA04 字段 X12_AN 数据类型且为 10 字符长度 （带有或不带尾随空格） 的或者 UNB6.1 字段 EDIFACT_AN 数据类型，并且是介于 1 到 14 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="5b700-118">To resolve this error, make sure that the ISA04 field is of the X12_AN data type and is 10 characters long (with or without trailing spaces) or that the UNB6.1 field is of the EDIFACT_AN data type and is between 1 and 14 characters long.</span></span> <span data-ttu-id="5b700-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="5b700-119">Have the interchange resent.</span></span>