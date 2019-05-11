---
title: 事务集架构包含一个或多个控制段 ISA、 IEA、 GS、 GE |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7589d8f0-c727-47df-afbc-77b0f190f3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74af9ed587ac6af016139348cc8ae9205a51bbb1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388343"
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a><span data-ttu-id="c430e-102">事务集架构包含一个或多个控制段 ISA、IEA、GS、GE</span><span class="sxs-lookup"><span data-stu-id="c430e-102">Transaction set schema contains one or more of control segments ISA, IEA, GS, GE</span></span>
## <a name="details"></a><span data-ttu-id="c430e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c430e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c430e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c430e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c430e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c430e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c430e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c430e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c430e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c430e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c430e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c430e-108">EDI</span></span> |
|    <span data-ttu-id="c430e-109">组件</span><span class="sxs-lookup"><span data-stu-id="c430e-109">Component</span></span>    |                                       <span data-ttu-id="c430e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c430e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c430e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c430e-111">Symbolic Name</span></span>  |                       <span data-ttu-id="c430e-112">SchemaCode114EOtherControlSegmentsPresent</span><span class="sxs-lookup"><span data-stu-id="c430e-112">SchemaCode114EOtherControlSegmentsPresent</span></span>                        |
|  <span data-ttu-id="c430e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c430e-113">Message Text</span></span>   |    <span data-ttu-id="c430e-114">事务集架构包含一个或多个控制段 ISA、IEA、GS、GE</span><span class="sxs-lookup"><span data-stu-id="c430e-114">Transaction set schema contains one or more of control segments ISA, IEA, GS, GE</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="c430e-115">解释</span><span class="sxs-lookup"><span data-stu-id="c430e-115">Explanation</span></span>  
 <span data-ttu-id="c430e-116">此错误/警告/信息事件表明接收管道无法处理传入的事务集或发送管道无法处理传出的事务集，因为事务集的文档架构至少定义了一个 ISA、IEA、GS 或 GE 段。</span><span class="sxs-lookup"><span data-stu-id="c430e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the document schema for the transaction set defined at least one ISA, IEA, GS, or GE segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c430e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c430e-117">User Action</span></span>  
 <span data-ttu-id="c430e-118">若要解决此错误，请取消部署文档架构，从架构中删除 ISA、IEA、GS 或 GE 段，然后重新部署架构。</span><span class="sxs-lookup"><span data-stu-id="c430e-118">To resolve this error, undeploy the document schema, remove the ISA, IEA, GS, or GE segment from the schema, and then redeploy the schema.</span></span>