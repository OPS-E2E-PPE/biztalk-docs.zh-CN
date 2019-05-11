---
title: 没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0752079a-173e-4de3-96f4-e5de01b799b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a224625122fa498410dc9aed9036fe875e4b739
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346320"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a><span data-ttu-id="7c7ae-102">没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方</span><span class="sxs-lookup"><span data-stu-id="7c7ae-102">There are no batch elements to send and an empty message cannot be sent as it is not configured for party</span></span>
## <a name="details"></a><span data-ttu-id="7c7ae-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7c7ae-103">Details</span></span>  
  
|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7c7ae-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7c7ae-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="7c7ae-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7c7ae-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="7c7ae-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7c7ae-106">Event ID</span></span>     |                                                       -                                                       |
|  <span data-ttu-id="7c7ae-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7c7ae-107">Event Source</span></span>   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7c7ae-108">EDI</span><span class="sxs-lookup"><span data-stu-id="7c7ae-108">EDI</span></span>             |
|    <span data-ttu-id="7c7ae-109">组件</span><span class="sxs-lookup"><span data-stu-id="7c7ae-109">Component</span></span>    |                                                <span data-ttu-id="7c7ae-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="7c7ae-110">Batching Engine</span></span>                                                |
|  <span data-ttu-id="7c7ae-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7c7ae-111">Symbolic Name</span></span>  |                                            <span data-ttu-id="7c7ae-112">EmptyMessageNotAllowed</span><span class="sxs-lookup"><span data-stu-id="7c7ae-112">EmptyMessageNotAllowed</span></span>                                             |
|  <span data-ttu-id="7c7ae-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7c7ae-113">Message Text</span></span>   | <span data-ttu-id="7c7ae-114">没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方 {0}</span><span class="sxs-lookup"><span data-stu-id="7c7ae-114">There are no batch elements to send and an empty message cannot be sent as it is not configured for party {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7c7ae-115">解释</span><span class="sxs-lookup"><span data-stu-id="7c7ae-115">Explanation</span></span>  
 <span data-ttu-id="7c7ae-116">此警告意味着任何批处理消息被基于计划的批处理过程中发送，因为当计划批处理发布，并不启用了空的批处理信号已不收到任何批处理元素。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-116">This Warning indicates that no batch message was sent in a schedule-based batching process because no batch elements had been received when the batch release was scheduled, and the empty batch signal has not been enabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c7ae-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7c7ae-117">User Action</span></span>  
 <span data-ttu-id="7c7ae-118">要阻止发布此警告，请执行以下操作配置空的批处理信号：</span><span class="sxs-lookup"><span data-stu-id="7c7ae-118">To prevent this warning from being posted, configure the empty batch signal by doing the following:</span></span>  
  
1.  <span data-ttu-id="7c7ae-119">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-119">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="7c7ae-120">将移动到参与方节点。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-120">Move to the Parties node.</span></span>  
  
3.  <span data-ttu-id="7c7ae-121">打开的参与方 EDI 属性对话框。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-121">Open the EDI Properties dialog box for the party.</span></span>  
  
4.  <span data-ttu-id="7c7ae-122">单击交换批处理创建设置节点 （适用于相应的编码）。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-122">Click the Interchange Batch Creation Settings node (for the appropriate encoding).</span></span>  
  
5.  <span data-ttu-id="7c7ae-123">单击计划程序。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-123">Click the Scheduler.</span></span>  
  
6.  <span data-ttu-id="7c7ae-124">单击发送空的批处理信号属性。</span><span class="sxs-lookup"><span data-stu-id="7c7ae-124">Click the Send empty batch signal property.</span></span>