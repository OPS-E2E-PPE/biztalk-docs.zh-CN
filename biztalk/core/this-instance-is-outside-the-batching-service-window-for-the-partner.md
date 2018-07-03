---
title: 此实例是合作伙伴的批处理服务窗口之外 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741439b5d6691a3218811568087450f2008b0ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966478"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a><span data-ttu-id="6d60e-102">此实例在合作伙伴的“批处理服务”窗口之外</span><span class="sxs-lookup"><span data-stu-id="6d60e-102">This instance is outside the Batching Service window for the partner</span></span>
## <a name="details"></a><span data-ttu-id="6d60e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6d60e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6d60e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6d60e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6d60e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="6d60e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6d60e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6d60e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6d60e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="6d60e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6d60e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6d60e-108"> EDI</span></span> |
|    <span data-ttu-id="6d60e-109">组件</span><span class="sxs-lookup"><span data-stu-id="6d60e-109">Component</span></span>    |                                    <span data-ttu-id="6d60e-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="6d60e-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="6d60e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="6d60e-111">Symbolic Name</span></span>  |                              <span data-ttu-id="6d60e-112">OutsideBatchingServiceWindow</span><span class="sxs-lookup"><span data-stu-id="6d60e-112">OutsideBatchingServiceWindow</span></span>                              |
|  <span data-ttu-id="6d60e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="6d60e-113">Message Text</span></span>   |          <span data-ttu-id="6d60e-114">此实例在合作伙伴的“批处理服务”窗口之外</span><span class="sxs-lookup"><span data-stu-id="6d60e-114">This instance is outside the Batching Service window for the partner</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="6d60e-115">解释</span><span class="sxs-lookup"><span data-stu-id="6d60e-115">Explanation</span></span>  
 <span data-ttu-id="6d60e-116">此错误/警告/信息事件表明批处理业务流程的一个实例无法启动，因为该实例在参与方的激活范围之外。</span><span class="sxs-lookup"><span data-stu-id="6d60e-116">This Error/Warning/Information event indicates that an instance of the batching orchestration could not be started because the instance fell outside the activation range for the party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d60e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="6d60e-117">User Action</span></span>  
 <span data-ttu-id="6d60e-118">若要解决此错误，请打开参与方的“EDI 属性”的“交换批处理创建设置”页，并确保该业务流程实例在激活范围之内。</span><span class="sxs-lookup"><span data-stu-id="6d60e-118">To resolve this error, open the Interchange Batch Creations Settings page of the EDI Properties for the party, and make sure that the orchestration instance is within the activation range.</span></span> <span data-ttu-id="6d60e-119">如果没有，请更改开始时间属性，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="6d60e-119">If not, change the Start time property and then click **Start**.</span></span>