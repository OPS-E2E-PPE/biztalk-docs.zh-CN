---
title: SenderId 无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be8055ab-8aba-49ac-ad33-fb33d4ff3e8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61ae69c91cc5e44d29e0f99abff9198632a02553
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381237"
---
# <a name="invalid-senderid"></a><span data-ttu-id="09939-102">SenderId 无效</span><span class="sxs-lookup"><span data-stu-id="09939-102">Invalid SenderId</span></span>
## <a name="details"></a><span data-ttu-id="09939-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="09939-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="09939-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="09939-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="09939-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="09939-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="09939-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="09939-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="09939-107">事件源</span><span class="sxs-lookup"><span data-stu-id="09939-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="09939-108">EDI</span><span class="sxs-lookup"><span data-stu-id="09939-108">EDI</span></span> |
|    <span data-ttu-id="09939-109">组件</span><span class="sxs-lookup"><span data-stu-id="09939-109">Component</span></span>    |                                       <span data-ttu-id="09939-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="09939-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="09939-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="09939-111">Symbolic Name</span></span>  |                            <span data-ttu-id="09939-112">X12Ta1InvalidSenderIdDescription</span><span class="sxs-lookup"><span data-stu-id="09939-112">X12Ta1InvalidSenderIdDescription</span></span>                            |
|  <span data-ttu-id="09939-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="09939-113">Message Text</span></span>   |                                    <span data-ttu-id="09939-114">SenderId 无效</span><span class="sxs-lookup"><span data-stu-id="09939-114">Invalid SenderId</span></span>                                    |
  
## <a name="explanation"></a><span data-ttu-id="09939-115">解释</span><span class="sxs-lookup"><span data-stu-id="09939-115">Explanation</span></span>  
 <span data-ttu-id="09939-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA06 字段中发送方 ID 或 UNB2.1 字段中的发送方标识不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。</span><span class="sxs-lookup"><span data-stu-id="09939-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Sender ID in the ISA06 field or the Sender Identification in the UNB2.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09939-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="09939-117">User Action</span></span>  
 <span data-ttu-id="09939-118">若要解决此错误，请确保 ISA06 字段为 X12_AN 数据类型并且长度为 15 个字符（带有或不带有尾部空格）或者 UNB2.1 字段为 EDIFACT_AN 数据类型并且长度介于 1 和 35 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="09939-118">To resolve this error, make sure that the ISA06 field is of the X12_AN data type and is 15 characters long (with or without trailing spaces) or that the UNB2.1 field is of the EDIFACT_AN data type and is between 1 and 35 characters.</span></span> <span data-ttu-id="09939-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="09939-119">Have the interchange resent.</span></span>