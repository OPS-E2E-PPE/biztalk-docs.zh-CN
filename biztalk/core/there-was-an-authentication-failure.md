---
title: "没有身份验证失败 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36524da9-da91-41e7-bf73-7781cde20c80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180645d30c5cccc64eacd57730539bbca220f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="there-was-an-authentication-failure"></a><span data-ttu-id="0dcdf-102">出现验证错误</span><span class="sxs-lookup"><span data-stu-id="0dcdf-102">There was an authentication failure</span></span>
## <a name="details"></a><span data-ttu-id="0dcdf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dcdf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0dcdf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0dcdf-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0dcdf-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0dcdf-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0dcdf-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0dcdf-106">Event ID</span></span>|-|  
|<span data-ttu-id="0dcdf-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0dcdf-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0dcdf-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0dcdf-108"> EDI</span></span>|  
|<span data-ttu-id="0dcdf-109">组件</span><span class="sxs-lookup"><span data-stu-id="0dcdf-109">Component</span></span>|<span data-ttu-id="0dcdf-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0dcdf-110">EDI Engine</span></span>|  
|<span data-ttu-id="0dcdf-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0dcdf-111">Symbolic Name</span></span>|<span data-ttu-id="0dcdf-112">DescPartyNotFound</span><span class="sxs-lookup"><span data-stu-id="0dcdf-112">DescPartyNotFound</span></span>|  
|<span data-ttu-id="0dcdf-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0dcdf-113">Message Text</span></span>|<span data-ttu-id="0dcdf-114">出现验证错误。</span><span class="sxs-lookup"><span data-stu-id="0dcdf-114">There was an authentication failure.</span></span> <span data-ttu-id="0dcdf-115">确保正在处理的消息存在匹配的参与方。</span><span class="sxs-lookup"><span data-stu-id="0dcdf-115">Make sure that a matching party exists for the message being processed.</span></span> <span data-ttu-id="0dcdf-116">并且消息中的安全/密码信息与“参与方”配置匹配</span><span class="sxs-lookup"><span data-stu-id="0dcdf-116">And the security/password information in the message matches the Party configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0dcdf-117">解释</span><span class="sxs-lookup"><span data-stu-id="0dcdf-117">Explanation</span></span>  
 <span data-ttu-id="0dcdf-118">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 BizTalk Server 无法验证消息的发送方。</span><span class="sxs-lookup"><span data-stu-id="0dcdf-118">This Error/Warning/Information event indicates that the receive pipeline was unable to process the incoming interchange because BizTalk Server was unable to authenticate the sender of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0dcdf-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="0dcdf-119">User Action</span></span>  
 <span data-ttu-id="0dcdf-120">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="0dcdf-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="0dcdf-121">验证交换标头中的发送方限定符和标识符（对于 X12，为字段 ISA5 和 ISA6，对于 EDIFACT，为字段 UNB2.1 和 UNB2.2）是否与某个参与方的属性中的发送方限定符和标识符匹配（如“EDI 属性”对话框的“交换处理属性”页中所定义）。</span><span class="sxs-lookup"><span data-stu-id="0dcdf-121">Verify that the sender qualifier and identifier in the interchange header (fields ISA5 and ISA6 for X12 or UNB2.1 and UNB2.2 for EDIFACT) match the sender qualifier and identifier in the properties of a party (as defined in the Interchange Processing Properties page of the EDI Properties dialog box).</span></span>  
  
-   <span data-ttu-id="0dcdf-122">验证交换标头中的安全/密码信息（对于 X12，为字段 ISA3 和 ISA4，对于 EDIFACT，为字段 UNB6.1 和 UNB6.2）是否与某个参与方的属性中的安全/密码信息匹配（如“EDI 属性”对话框的“交换处理属性”页中所定义）。</span><span class="sxs-lookup"><span data-stu-id="0dcdf-122">Verify that the security/password information in the header of the interchange (fields ISA3 and ISA4 for X12 or UNB6.1 and UNB6.2 for EDIFACT) match the security/password information in the properties of a party (as defined in the Interchange Processing Properties page of the EDI Properties dialog box).</span></span>