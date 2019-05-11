---
title: 架构应该让段处于以下顺序 ST ....SE | Microsoft Docs
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
ms.openlocfilehash: b975f28221941ef84f0683fae1597816640d48a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396906"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="b5b9b-102">架构应该让段处于以下顺序 ST ....SE</span><span class="sxs-lookup"><span data-stu-id="b5b9b-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="b5b9b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b5b9b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b5b9b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b5b9b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b5b9b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b5b9b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b5b9b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b5b9b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b5b9b-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b5b9b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b5b9b-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b5b9b-108">EDI</span></span> |
|    <span data-ttu-id="b5b9b-109">组件</span><span class="sxs-lookup"><span data-stu-id="b5b9b-109">Component</span></span>    |                                       <span data-ttu-id="b5b9b-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b5b9b-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="b5b9b-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b5b9b-111">Symbolic Name</span></span>  |                    <span data-ttu-id="b5b9b-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="b5b9b-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>                    |
|  <span data-ttu-id="b5b9b-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b5b9b-113">Message Text</span></span>   |             <span data-ttu-id="b5b9b-114">架构应该让段处于以下顺序 ST ....SE</span><span class="sxs-lookup"><span data-stu-id="b5b9b-114">Schema should have segments in the following order ST .... SE</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="b5b9b-115">解释</span><span class="sxs-lookup"><span data-stu-id="b5b9b-115">Explanation</span></span>  
 <span data-ttu-id="b5b9b-116">此错误/警告/信息事件表明自定义文档架构无效，因为标头和尾部未处于正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="b5b9b-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="b5b9b-117">BizTalk Server 在部署架构时执行此验证。</span><span class="sxs-lookup"><span data-stu-id="b5b9b-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5b9b-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="b5b9b-118">User Action</span></span>  
 <span data-ttu-id="b5b9b-119">若要解决此错误，请更改自定义的文档架构以便标头和尾部处于正确的顺序，然后重新部署架构。</span><span class="sxs-lookup"><span data-stu-id="b5b9b-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>