---
title: 参与方的批设置已过期，批处理业务流程被终止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 471d42035f0c8c279fd25e8bb5ba480f7e0f962a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990054"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a><span data-ttu-id="d3b80-102">参与方的批设置已过期，批处理业务流程被终止</span><span class="sxs-lookup"><span data-stu-id="d3b80-102">The batch settings for party have expired and the batching orchestration is being terminated</span></span>
## <a name="details"></a><span data-ttu-id="d3b80-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d3b80-103">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d3b80-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d3b80-104">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="d3b80-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d3b80-105">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="d3b80-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d3b80-106">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="d3b80-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d3b80-107">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d3b80-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d3b80-108"> EDI</span></span>                                                 |
|    <span data-ttu-id="d3b80-109">组件</span><span class="sxs-lookup"><span data-stu-id="d3b80-109">Component</span></span>    |                                                                                    <span data-ttu-id="d3b80-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="d3b80-110">Batching Engine</span></span>                                                                                    |
|  <span data-ttu-id="d3b80-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d3b80-111">Symbolic Name</span></span>  |                                                                                 <span data-ttu-id="d3b80-112">BatchSettingsExpired</span><span class="sxs-lookup"><span data-stu-id="d3b80-112">BatchSettingsExpired</span></span>                                                                                  |
|  <span data-ttu-id="d3b80-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d3b80-113">Message Text</span></span>   | <span data-ttu-id="d3b80-114">参与方的批处理设置{0}已过期，批处理业务流程被终止。</span><span class="sxs-lookup"><span data-stu-id="d3b80-114">The batch settings for party {0} have expired and the batching orchestration is being terminated.</span></span> <span data-ttu-id="d3b80-115">在为此参与方激活批处理之前，不会生成其他批处理。</span><span class="sxs-lookup"><span data-stu-id="d3b80-115">Further batches will not be generated till the batching is activated for this party</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d3b80-116">解释</span><span class="sxs-lookup"><span data-stu-id="d3b80-116">Explanation</span></span>  
 <span data-ttu-id="d3b80-117">此警告表明批处理业务流程实例已被停用，因为已达到激活范围的结尾。</span><span class="sxs-lookup"><span data-stu-id="d3b80-117">This Warning indicates that the batching orchestration instance has been deactivated because the end of the activation range has been reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d3b80-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="d3b80-118">User Action</span></span>  
 <span data-ttu-id="d3b80-119">若要解决此错误，请通过执行以下操作重新启动批处理过程：</span><span class="sxs-lookup"><span data-stu-id="d3b80-119">To resolve this error, restart the batching process by doing the following:</span></span>  
  
1.  <span data-ttu-id="d3b80-120">打开 BizTalk Server 管理控制台，移动到“EDI 属性”对话框的“交换批处理创建设置”页。</span><span class="sxs-lookup"><span data-stu-id="d3b80-120">Open the BizTalk Server Administration Console, and move to the Interchange Batch Creation Settings Page of the EDI Properties dialog box.</span></span>  
  
2.  <span data-ttu-id="d3b80-121">重置结束条件，并单击，然后重新启动该业务流程**启动**。</span><span class="sxs-lookup"><span data-stu-id="d3b80-121">Reset the end criteria, and then restart the orchestration by clicking **Start**.</span></span>  
  
3.  <span data-ttu-id="d3b80-122">在单击时的时间之前开始日期时间是否**启动**，单击**是**以开始日期时间更新为当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="d3b80-122">If the Start datetime is prior to the time when you clicked **Start**, click **Yes** to update the Start datetime to the current datetime.</span></span>