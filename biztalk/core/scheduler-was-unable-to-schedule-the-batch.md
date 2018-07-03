---
title: 计划程序无法对批处理进行计划 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbd425c8f7faacaa38ac11375905f701f597faf6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984398"
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a><span data-ttu-id="deae8-102">计划程序无法对批处理进行计划</span><span class="sxs-lookup"><span data-stu-id="deae8-102">Scheduler was unable to schedule the batch</span></span>
## <a name="details"></a><span data-ttu-id="deae8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="deae8-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="deae8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="deae8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="deae8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="deae8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="deae8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="deae8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="deae8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="deae8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="deae8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="deae8-108"> EDI</span></span> |
|    <span data-ttu-id="deae8-109">组件</span><span class="sxs-lookup"><span data-stu-id="deae8-109">Component</span></span>    |                                    <span data-ttu-id="deae8-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="deae8-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="deae8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="deae8-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="deae8-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="deae8-112">Message Text</span></span>   |                       <span data-ttu-id="deae8-113">计划程序无法对批处理进行计划</span><span class="sxs-lookup"><span data-stu-id="deae8-113">Scheduler was unable to schedule the batch</span></span>                       |

## <a name="explanation"></a><span data-ttu-id="deae8-114">解释</span><span class="sxs-lookup"><span data-stu-id="deae8-114">Explanation</span></span>  
 <span data-ttu-id="deae8-115">此错误表明计划程序无法确定下次发生的批处理发布。</span><span class="sxs-lookup"><span data-stu-id="deae8-115">This error indicates the scheduler could not determine the next occurrence of a batch release.</span></span>  

## <a name="user-action"></a><span data-ttu-id="deae8-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="deae8-116">User Action</span></span>  
 <span data-ttu-id="deae8-117">若要解决此错误，请确保批处理发布计划有效：</span><span class="sxs-lookup"><span data-stu-id="deae8-117">To resolve this error, make sure the batch release schedule is valid:</span></span>  

1. <span data-ttu-id="deae8-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="deae8-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="deae8-119">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="deae8-119">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="deae8-120">右键单击正确的参与方。</span><span class="sxs-lookup"><span data-stu-id="deae8-120">Right-click the correct party.</span></span>  

4. <span data-ttu-id="deae8-121">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="deae8-121">Click **Properties**.</span></span>  

5. <span data-ttu-id="deae8-122">在 [*参与方名称*]**参与方属性**对话框中，在左窗格中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="deae8-122">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  

6. <span data-ttu-id="deae8-123">输入中的发送端口名称**发送端口**列表。</span><span class="sxs-lookup"><span data-stu-id="deae8-123">Enter the Send port name in the **Send Ports** list.</span></span>  

7. <span data-ttu-id="deae8-124">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="deae8-124">Click **OK**.</span></span>
