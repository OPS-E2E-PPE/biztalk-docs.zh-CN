---
title: 如何配置 MQSeries 适配器发送和接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b2b40729dfd8e1f6e4077149a3c360dc35cc81e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341312"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a><span data-ttu-id="a8b1e-102">如何配置 MQSeries 适配器发送和接收处理程序</span><span class="sxs-lookup"><span data-stu-id="a8b1e-102">How to Configure MQSeries Adapter Send and Receive Handlers</span></span>
<span data-ttu-id="a8b1e-103">你可以配置某些属性的发送和接收处理程序，MQSeries 适配器通过 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-103">You can configure some properties for the send and receive handlers for the MQSeries adapter through the BizTalk Server Administration console.</span></span> <span data-ttu-id="a8b1e-104">该过程中所述[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)建立大部分发送处理程序属性的值。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-104">The process described in [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establishes the values for the majority of send handler properties.</span></span>  

## <a name="to-configure-the-send-and-receive-handlers"></a><span data-ttu-id="a8b1e-105">若要配置发送和接收处理程序</span><span class="sxs-lookup"><span data-stu-id="a8b1e-105">To configure the send and receive handlers</span></span>  
 <span data-ttu-id="a8b1e-106">请执行以下步骤来配置发送和接收的 MSQeries 适配器处理程序：</span><span class="sxs-lookup"><span data-stu-id="a8b1e-106">Follow these steps to configure send and receive handlers for the MSQeries adapter:</span></span>  

1. <span data-ttu-id="a8b1e-107">单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-107">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="a8b1e-108">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，单击此项可展开**平台设置**，然后单击到展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-108">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span>  

3. <span data-ttu-id="a8b1e-109">在展开的适配器列表中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-109">In the expanded adapter list, select **MQSeries**.</span></span> <span data-ttu-id="a8b1e-110">列表发送和接收处理程序绑定到 MQSeries 适配器显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-110">The list of send and receive handlers that are bound to the MQSeries adapter appear in the right pane.</span></span>  

4. <span data-ttu-id="a8b1e-111">在右窗格中，双击发送或接收处理程序，在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-111">In the right pane, double-click a send or receive handler in the right pane.</span></span>  

5. <span data-ttu-id="a8b1e-112">在中**适配器处理程序属性**对话框中，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-112">In the **Adapter Handler Properties** dialog box, click **Properties**.</span></span>  

6. <span data-ttu-id="a8b1e-113">在中**MQSeries 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8b1e-113">In the **MQSeries Transport Properties** dialog box, do the following:</span></span>  


   |           <span data-ttu-id="a8b1e-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a8b1e-114">Use this</span></span>            |                                    <span data-ttu-id="a8b1e-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a8b1e-115">To do this</span></span>                                    |
   |-------------------------------|----------------------------------------------------------------------------------|
   | <span data-ttu-id="a8b1e-116">**批中最大消息数**</span><span class="sxs-lookup"><span data-stu-id="a8b1e-116">**Maximum Messages in Batch**</span></span> | <span data-ttu-id="a8b1e-117">在批处理中设置的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-117">Set the maximum number of messages in a batch.</span></span> <span data-ttu-id="a8b1e-118">仅适用于发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-118">Applies only to the send handler.</span></span> |
   |          <span data-ttu-id="a8b1e-119">**Server**</span><span class="sxs-lookup"><span data-stu-id="a8b1e-119">**Server**</span></span>           |      <span data-ttu-id="a8b1e-120">运行 MQSeries Server for Windows 的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-120">The name of the computer that is running MQSeries Server for Windows.</span></span>       |


7. <span data-ttu-id="a8b1e-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-121">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a8b1e-122">接收位置和发送端口属性重写的接收处理程序和发送处理程序值。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-122">The Receive Location and Send Port properties override the Receive Handler and Send Handler values.</span></span> <span data-ttu-id="a8b1e-123">如果没有为接收位置或发送端口属性的值，适配器将分别使用的接收处理程序和发送处理程序值。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-123">If there is no value for the Receive Location or Send Port properties, the adapter uses the Receive Handler and Send Handler values respectively.</span></span>  

8. <span data-ttu-id="a8b1e-124">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a8b1e-124">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a8b1e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b1e-125">See Also</span></span>  
 <span data-ttu-id="a8b1e-126">[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a8b1e-126">[How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span></span>  
 [<span data-ttu-id="a8b1e-127">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="a8b1e-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)