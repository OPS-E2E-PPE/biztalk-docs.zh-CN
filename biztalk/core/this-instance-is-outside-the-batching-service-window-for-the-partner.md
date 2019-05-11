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
ms.openlocfilehash: bc0a60bf52b691795047175186f2707c6839981a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395448"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a><span data-ttu-id="ee7e9-102">此实例是合作伙伴的批处理服务窗口之外</span><span class="sxs-lookup"><span data-stu-id="ee7e9-102">This instance is outside the Batching Service window for the partner</span></span>
## <a name="details"></a><span data-ttu-id="ee7e9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee7e9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ee7e9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ee7e9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ee7e9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ee7e9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ee7e9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ee7e9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ee7e9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ee7e9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ee7e9-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ee7e9-108">EDI</span></span> |
|    <span data-ttu-id="ee7e9-109">组件</span><span class="sxs-lookup"><span data-stu-id="ee7e9-109">Component</span></span>    |                                    <span data-ttu-id="ee7e9-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="ee7e9-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="ee7e9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ee7e9-111">Symbolic Name</span></span>  |                              <span data-ttu-id="ee7e9-112">OutsideBatchingServiceWindow</span><span class="sxs-lookup"><span data-stu-id="ee7e9-112">OutsideBatchingServiceWindow</span></span>                              |
|  <span data-ttu-id="ee7e9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ee7e9-113">Message Text</span></span>   |          <span data-ttu-id="ee7e9-114">此实例是合作伙伴的批处理服务窗口之外</span><span class="sxs-lookup"><span data-stu-id="ee7e9-114">This instance is outside the Batching Service window for the partner</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="ee7e9-115">解释</span><span class="sxs-lookup"><span data-stu-id="ee7e9-115">Explanation</span></span>  
 <span data-ttu-id="ee7e9-116">此错误/警告/信息事件表明，批处理业务流程的实例无法启动，因为该实例不属于此激活范围内的参与方。</span><span class="sxs-lookup"><span data-stu-id="ee7e9-116">This Error/Warning/Information event indicates that an instance of the batching orchestration could not be started because the instance fell outside the activation range for the party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee7e9-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ee7e9-117">User Action</span></span>  
 <span data-ttu-id="ee7e9-118">若要解决此错误，请打开 EDI 属性交换批处理创建设置页上的参与方，并确保业务流程实例在激活范围内。</span><span class="sxs-lookup"><span data-stu-id="ee7e9-118">To resolve this error, open the Interchange Batch Creations Settings page of the EDI Properties for the party, and make sure that the orchestration instance is within the activation range.</span></span> <span data-ttu-id="ee7e9-119">如果没有，请更改开始时间属性，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="ee7e9-119">If not, change the Start time property and then click **Start**.</span></span>