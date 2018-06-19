---
title: 无效的交换内容 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2352c3-d233-4d79-be31-b32dde29c8ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03dc518406083cda1b070a3358cc4d8967f5f07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257021"
---
# <a name="invalid-interchange-content"></a><span data-ttu-id="043f0-102">无效的交换内容</span><span class="sxs-lookup"><span data-stu-id="043f0-102">Invalid Interchange Content</span></span>
## <a name="details"></a><span data-ttu-id="043f0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="043f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="043f0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="043f0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="043f0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="043f0-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="043f0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="043f0-106">Event ID</span></span>|-|  
|<span data-ttu-id="043f0-107">事件源</span><span class="sxs-lookup"><span data-stu-id="043f0-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="043f0-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="043f0-108"> EDI</span></span>|  
|<span data-ttu-id="043f0-109">组件</span><span class="sxs-lookup"><span data-stu-id="043f0-109">Component</span></span>|<span data-ttu-id="043f0-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="043f0-110">EDI Engine</span></span>|  
|<span data-ttu-id="043f0-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="043f0-111">Symbolic Name</span></span>|<span data-ttu-id="043f0-112">X12Ta1InvalidInterchangeContentDescription</span><span class="sxs-lookup"><span data-stu-id="043f0-112">X12Ta1InvalidInterchangeContentDescription</span></span>|  
|<span data-ttu-id="043f0-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="043f0-113">Message Text</span></span>|<span data-ttu-id="043f0-114">无效的交换内容</span><span class="sxs-lookup"><span data-stu-id="043f0-114">Invalid Interchange Content</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="043f0-115">解释</span><span class="sxs-lookup"><span data-stu-id="043f0-115">Explanation</span></span>  
 <span data-ttu-id="043f0-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或者发送管道无法处理传出交换，因为交换中的数据未通过由 BizTalk Server 执行的消息验证。</span><span class="sxs-lookup"><span data-stu-id="043f0-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the data in the interchange did not pass message validation performed by BizTalk Server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="043f0-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="043f0-117">User Action</span></span>  
 <span data-ttu-id="043f0-118">若要解决此错误，请确定交换的哪个部分未通过验证以及未通过哪个验证。</span><span class="sxs-lookup"><span data-stu-id="043f0-118">To resolve this error, identify which part of the interchange failed validation, and which validation it failed.</span></span> <span data-ttu-id="043f0-119">解决造成验证失败的问题，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="043f0-119">Resolve the issue that caused validation to fail, and then have the interchange resent.</span></span>