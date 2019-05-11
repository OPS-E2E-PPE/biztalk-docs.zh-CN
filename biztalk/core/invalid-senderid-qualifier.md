---
title: SenderId 限定符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe9c51c-d569-4f14-a690-f145ef1bf6a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc05357a18679af845c6556a9a96952dbe8bfe3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330466"
---
# <a name="invalid-senderid-qualifier"></a><span data-ttu-id="03912-102">SenderId 限定符无效</span><span class="sxs-lookup"><span data-stu-id="03912-102">Invalid SenderId Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="03912-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="03912-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="03912-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="03912-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="03912-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="03912-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="03912-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="03912-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="03912-107">事件源</span><span class="sxs-lookup"><span data-stu-id="03912-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="03912-108">EDI</span><span class="sxs-lookup"><span data-stu-id="03912-108">EDI</span></span> |
|    <span data-ttu-id="03912-109">组件</span><span class="sxs-lookup"><span data-stu-id="03912-109">Component</span></span>    |                                       <span data-ttu-id="03912-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="03912-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="03912-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="03912-111">Symbolic Name</span></span>  |                       <span data-ttu-id="03912-112">X12Ta1InvalidSenderIdQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="03912-112">X12Ta1InvalidSenderIdQualifierDescription</span></span>                        |
|  <span data-ttu-id="03912-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="03912-113">Message Text</span></span>   |                               <span data-ttu-id="03912-114">SenderId 限定符无效</span><span class="sxs-lookup"><span data-stu-id="03912-114">Invalid SenderId Qualifier</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="03912-115">解释</span><span class="sxs-lookup"><span data-stu-id="03912-115">Explanation</span></span>  
 <span data-ttu-id="03912-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA05 字段中的发送方限定符（对于 X12 交换）或 UNB2.2 字段中的发送方代码限定符（对于 EDIFACT 交换）与服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的枚举中的值不匹配。</span><span class="sxs-lookup"><span data-stu-id="03912-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Sender Qualifier in the ISA05 field (for an X12 interchange) or the Sender Code Qualifier in the UNB2.2 field (for an EDIFACT interchange) did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="03912-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="03912-117">User Action</span></span>  
 <span data-ttu-id="03912-118">若要解决此错误，请确保 ISA07 字段或 UNB3.2 字段与服务架构建立的枚举中的其中一个值匹配。</span><span class="sxs-lookup"><span data-stu-id="03912-118">To resolve this error, make sure that the ISA07 field or the UNB3.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="03912-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="03912-119">Have the interchange resent.</span></span>