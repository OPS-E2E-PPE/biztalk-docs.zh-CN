---
title: 控制架构应该让标头段处于正确的顺序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fee939bb14b98dc66373d754af13d9f4bb327f2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354457"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a><span data-ttu-id="1f6c5-102">控制架构应该让标头段处于正确的顺序</span><span class="sxs-lookup"><span data-stu-id="1f6c5-102">Control schema should have header segments in the correct order</span></span>
## <a name="details"></a><span data-ttu-id="1f6c5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f6c5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1f6c5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1f6c5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1f6c5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1f6c5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1f6c5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1f6c5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1f6c5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1f6c5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1f6c5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="1f6c5-108">EDI</span></span> |
|    <span data-ttu-id="1f6c5-109">组件</span><span class="sxs-lookup"><span data-stu-id="1f6c5-109">Component</span></span>    |                                       <span data-ttu-id="1f6c5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1f6c5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="1f6c5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1f6c5-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="1f6c5-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="1f6c5-112">Message Text</span></span>   |  <span data-ttu-id="1f6c5-113">控制架构应该让段处于以下顺序：ISA GS ST...SE GE IEA</span><span class="sxs-lookup"><span data-stu-id="1f6c5-113">Control schema should have segments in the following order: ISA GS ST .... SE GE IEA</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="1f6c5-114">解释</span><span class="sxs-lookup"><span data-stu-id="1f6c5-114">Explanation</span></span>  
 <span data-ttu-id="1f6c5-115">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为标头和尾部的交换、 组和事务集不是交换中正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="1f6c5-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because the headers and trailers for the interchange, groups, and transaction sets were not in the correct order in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1f6c5-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="1f6c5-116">User Action</span></span>  
 <span data-ttu-id="1f6c5-117">若要解决此错误，请确保，ISA、 GS 和 ST 标头和 SE、 GE 和 IEA 尾部在交换中，正确的顺序，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="1f6c5-117">To resolve this error, ensure that the ISA, GS, and ST headers, and the SE, GE, and IEA trailers, are in the correct order in the interchange, and then resend the interchange.</span></span>