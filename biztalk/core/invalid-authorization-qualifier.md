---
title: "无效的授权限定符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf33e8bd42b18134bd31f02f791b306ece97272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-authorization-qualifier"></a><span data-ttu-id="ea93c-102">授权限定符无效</span><span class="sxs-lookup"><span data-stu-id="ea93c-102">Invalid Authorization Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="ea93c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ea93c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea93c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ea93c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ea93c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ea93c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ea93c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ea93c-106">Event ID</span></span>|-|  
|<span data-ttu-id="ea93c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ea93c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ea93c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ea93c-108"> EDI</span></span>|  
|<span data-ttu-id="ea93c-109">组件</span><span class="sxs-lookup"><span data-stu-id="ea93c-109">Component</span></span>|<span data-ttu-id="ea93c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ea93c-110">EDI Engine</span></span>|  
|<span data-ttu-id="ea93c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ea93c-111">Symbolic Name</span></span>|<span data-ttu-id="ea93c-112">X12Ta1InvalidAuthorizationQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="ea93c-112">X12Ta1InvalidAuthorizationQualifierDescription</span></span>|  
|<span data-ttu-id="ea93c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ea93c-113">Message Text</span></span>|<span data-ttu-id="ea93c-114">授权限定符无效</span><span class="sxs-lookup"><span data-stu-id="ea93c-114">Invalid Authorization Qualifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ea93c-115">解释</span><span class="sxs-lookup"><span data-stu-id="ea93c-115">Explanation</span></span>  
 <span data-ttu-id="ea93c-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA01 中“授权限定符”的值与架构指定的任何枚举值都不匹配。</span><span class="sxs-lookup"><span data-stu-id="ea93c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Qualifier in ISA01 did not match any of the enumeration values specified by the schema.</span></span> <span data-ttu-id="ea93c-117">架构是 BaseArtifacts.dll 中的 X12ServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="ea93c-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea93c-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ea93c-118">User Action</span></span>  
 <span data-ttu-id="ea93c-119">若要解决此错误，请确保 ISA01 标头中的值与 X12ServiceSchema 指定的其中一个枚举值匹配，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="ea93c-119">To resolve this error, make sure that the value in the ISA01 header matches one of the enumeration values specified by the X12ServiceSchema, and then have the interchange resent.</span></span>