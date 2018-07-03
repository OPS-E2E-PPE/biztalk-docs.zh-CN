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
ms.openlocfilehash: 73d0d44c8a5a206748eb128cd2461d1d04b54c93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976662"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a><span data-ttu-id="438b2-102">There are no batch elements to send and an empty message cannot be sent as it is not configured for party</span><span class="sxs-lookup"><span data-stu-id="438b2-102">There are no batch elements to send and an empty message cannot be sent as it is not configured for party</span></span>
## <a name="details"></a><span data-ttu-id="438b2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="438b2-103">Details</span></span>  
  
|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="438b2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="438b2-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="438b2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="438b2-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="438b2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="438b2-106">Event ID</span></span>     |                                                       -                                                       |
|  <span data-ttu-id="438b2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="438b2-107">Event Source</span></span>   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="438b2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="438b2-108"> EDI</span></span>             |
|    <span data-ttu-id="438b2-109">组件</span><span class="sxs-lookup"><span data-stu-id="438b2-109">Component</span></span>    |                                                <span data-ttu-id="438b2-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="438b2-110">Batching Engine</span></span>                                                |
|  <span data-ttu-id="438b2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="438b2-111">Symbolic Name</span></span>  |                                            <span data-ttu-id="438b2-112">EmptyMessageNotAllowed</span><span class="sxs-lookup"><span data-stu-id="438b2-112">EmptyMessageNotAllowed</span></span>                                             |
|  <span data-ttu-id="438b2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="438b2-113">Message Text</span></span>   | <span data-ttu-id="438b2-114">没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方 {0}</span><span class="sxs-lookup"><span data-stu-id="438b2-114">There are no batch elements to send and an empty message cannot be sent as it is not configured for party {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="438b2-115">解释</span><span class="sxs-lookup"><span data-stu-id="438b2-115">Explanation</span></span>  
 <span data-ttu-id="438b2-116">此警告表明在基于计划的批处理过程中没有发送批处理消息，因为当计划批处理发布时未收到任何批处理元素，并且尚未启用空的批处理信号。</span><span class="sxs-lookup"><span data-stu-id="438b2-116">This Warning indicates that no batch message was sent in a schedule-based batching process because no batch elements had been received when the batch release was scheduled, and the empty batch signal has not been enabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="438b2-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="438b2-117">User Action</span></span>  
 <span data-ttu-id="438b2-118">若要阻止发布此警告，请通过执行以下操作配置空的批处理信号：</span><span class="sxs-lookup"><span data-stu-id="438b2-118">To prevent this warning from being posted, configure the empty batch signal by doing the following:</span></span>  
  
1.  <span data-ttu-id="438b2-119">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="438b2-119">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="438b2-120">移动到“参与方”节点。</span><span class="sxs-lookup"><span data-stu-id="438b2-120">Move to the Parties node.</span></span>  
  
3.  <span data-ttu-id="438b2-121">打开该参与方的“EDI 属性”对话框。</span><span class="sxs-lookup"><span data-stu-id="438b2-121">Open the EDI Properties dialog box for the party.</span></span>  
  
4.  <span data-ttu-id="438b2-122">单击“交换批处理创建设置”节点（对于相应的编码）。</span><span class="sxs-lookup"><span data-stu-id="438b2-122">Click the Interchange Batch Creation Settings node (for the appropriate encoding).</span></span>  
  
5.  <span data-ttu-id="438b2-123">单击“计划程序”。</span><span class="sxs-lookup"><span data-stu-id="438b2-123">Click the Scheduler.</span></span>  
  
6.  <span data-ttu-id="438b2-124">单击“发送空的批处理信号”属性。</span><span class="sxs-lookup"><span data-stu-id="438b2-124">Click the Send empty batch signal property.</span></span>