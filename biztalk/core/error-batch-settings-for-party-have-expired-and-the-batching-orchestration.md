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
ms.openlocfilehash: 896eb6325aa2bac076908643e582d286f2b5febe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389406"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a><span data-ttu-id="4b24f-102">参与方的批设置已过期，批处理业务流程被终止</span><span class="sxs-lookup"><span data-stu-id="4b24f-102">The batch settings for party have expired and the batching orchestration is being terminated</span></span>
## <a name="details"></a><span data-ttu-id="4b24f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4b24f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4b24f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4b24f-104">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="4b24f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4b24f-105">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="4b24f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4b24f-106">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="4b24f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="4b24f-107">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4b24f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="4b24f-108">EDI</span></span>                                                 |
|    <span data-ttu-id="4b24f-109">组件</span><span class="sxs-lookup"><span data-stu-id="4b24f-109">Component</span></span>    |                                                                                    <span data-ttu-id="4b24f-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="4b24f-110">Batching Engine</span></span>                                                                                    |
|  <span data-ttu-id="4b24f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="4b24f-111">Symbolic Name</span></span>  |                                                                                 <span data-ttu-id="4b24f-112">BatchSettingsExpired</span><span class="sxs-lookup"><span data-stu-id="4b24f-112">BatchSettingsExpired</span></span>                                                                                  |
|  <span data-ttu-id="4b24f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="4b24f-113">Message Text</span></span>   | <span data-ttu-id="4b24f-114">参与方的批处理设置{0}已过期，批处理业务流程被终止。</span><span class="sxs-lookup"><span data-stu-id="4b24f-114">The batch settings for party {0} have expired and the batching orchestration is being terminated.</span></span> <span data-ttu-id="4b24f-115">为此参与方激活批处理之前，将不会生成其他批处理。</span><span class="sxs-lookup"><span data-stu-id="4b24f-115">Further batches will not be generated till the batching is activated for this party</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4b24f-116">解释</span><span class="sxs-lookup"><span data-stu-id="4b24f-116">Explanation</span></span>  
 <span data-ttu-id="4b24f-117">此警告表明批处理业务流程实例由于已达到激活范围的末尾已被停用。</span><span class="sxs-lookup"><span data-stu-id="4b24f-117">This Warning indicates that the batching orchestration instance has been deactivated because the end of the activation range has been reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b24f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="4b24f-118">User Action</span></span>  
 <span data-ttu-id="4b24f-119">若要解决此错误，请执行以下操作重新启动批处理过程：</span><span class="sxs-lookup"><span data-stu-id="4b24f-119">To resolve this error, restart the batching process by doing the following:</span></span>  
  
1.  <span data-ttu-id="4b24f-120">打开 BizTalk Server 管理控制台，然后转到交换批处理创建设置页的 EDI 属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4b24f-120">Open the BizTalk Server Administration Console, and move to the Interchange Batch Creation Settings Page of the EDI Properties dialog box.</span></span>  
  
2.  <span data-ttu-id="4b24f-121">重置结束条件，并单击，然后重新启动该业务流程**启动**。</span><span class="sxs-lookup"><span data-stu-id="4b24f-121">Reset the end criteria, and then restart the orchestration by clicking **Start**.</span></span>  
  
3.  <span data-ttu-id="4b24f-122">在单击时的时间之前开始日期时间是否**启动**，单击**是**以开始日期时间更新为当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="4b24f-122">If the Start datetime is prior to the time when you clicked **Start**, click **Yes** to update the Start datetime to the current datetime.</span></span>