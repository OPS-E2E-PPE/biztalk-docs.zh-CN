---
title: 架构应该让段处于以下顺序 ST ....SE |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563247dc6fc4c092fe2867c6b4d03239c4be7e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269093"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="918ca-102">架构应该让段处于以下顺序 ST ....SE</span><span class="sxs-lookup"><span data-stu-id="918ca-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="918ca-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="918ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="918ca-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="918ca-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="918ca-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="918ca-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="918ca-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="918ca-106">Event ID</span></span>|-|  
|<span data-ttu-id="918ca-107">事件源</span><span class="sxs-lookup"><span data-stu-id="918ca-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="918ca-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="918ca-108"> EDI</span></span>|  
|<span data-ttu-id="918ca-109">组件</span><span class="sxs-lookup"><span data-stu-id="918ca-109">Component</span></span>|<span data-ttu-id="918ca-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="918ca-110">EDI Engine</span></span>|  
|<span data-ttu-id="918ca-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="918ca-111">Symbolic Name</span></span>|<span data-ttu-id="918ca-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="918ca-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>|  
|<span data-ttu-id="918ca-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="918ca-113">Message Text</span></span>|<span data-ttu-id="918ca-114">架构应该让段处于以下顺序 ST ....SE</span><span class="sxs-lookup"><span data-stu-id="918ca-114">Schema should have segments in the following order ST .... SE</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="918ca-115">解释</span><span class="sxs-lookup"><span data-stu-id="918ca-115">Explanation</span></span>  
 <span data-ttu-id="918ca-116">此错误/警告/信息事件表明自定义文档架构无效，因为标头和尾部未处于正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="918ca-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="918ca-117">BizTalk Server 在部署架构时执行此验证。</span><span class="sxs-lookup"><span data-stu-id="918ca-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="918ca-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="918ca-118">User Action</span></span>  
 <span data-ttu-id="918ca-119">若要解决此错误，请更改自定义的文档架构以便标头和尾部处于正确的顺序，然后重新部署架构。</span><span class="sxs-lookup"><span data-stu-id="918ca-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>