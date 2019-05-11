---
title: 如何创建新的网关节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- gateway nodes, creating
ms.assetid: e7c5f9a7-a58e-4661-9cb5-2414e31a57a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5549317c45fbb431155eb3fab3e757c519956cc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385578"
---
# <a name="how-to-create-a-new-gateway-node"></a><span data-ttu-id="60d6d-102">如何创建新的网关节点</span><span class="sxs-lookup"><span data-stu-id="60d6d-102">How to Create a New Gateway Node</span></span>
<span data-ttu-id="60d6d-103">按照以下步骤来创建和配置新的网关节点在 PeopleSoft Enterprise。</span><span class="sxs-lookup"><span data-stu-id="60d6d-103">Follow these steps to create and configure a new Gateway node in PeopleSoft Enterprise.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="60d6d-104">若要创建和配置新的网关节点</span><span class="sxs-lookup"><span data-stu-id="60d6d-104">To create and configure a new gateway node</span></span>  
  
1. <span data-ttu-id="60d6d-105">在 PeopleSoft，左面板中，单击**节点定义**链接。</span><span class="sxs-lookup"><span data-stu-id="60d6d-105">In PeopleSoft, on the left panel, click the **Node Definitions** link.</span></span>  
  
2. <span data-ttu-id="60d6d-106">单击**添加新值**选项卡。</span><span class="sxs-lookup"><span data-stu-id="60d6d-106">Click the **Add a New Value** tab.</span></span>  
  
3. <span data-ttu-id="60d6d-107">在中**节点名称**字段中，输入`MSEXTERNAL`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="60d6d-107">In the **Node Name** field, enter `MSEXTERNAL`, and then click **Add**.</span></span>  
  
4. <span data-ttu-id="60d6d-108">单击**节点**选项卡，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="60d6d-108">Click the **Node** tab, and enter the following information:</span></span>  
  
   1. <span data-ttu-id="60d6d-109">**说明：** 输入节点的说明。</span><span class="sxs-lookup"><span data-stu-id="60d6d-109">**Description:** Enter a description for the node.</span></span>  
  
   2. <span data-ttu-id="60d6d-110">**节点类型：** 选择**外部**。</span><span class="sxs-lookup"><span data-stu-id="60d6d-110">**Node Type:** Select **External**.</span></span>  
  
   3. <span data-ttu-id="60d6d-111">**路由类型：** 选择**隐式**。</span><span class="sxs-lookup"><span data-stu-id="60d6d-111">**Routing Type:** Select **Implicit**.</span></span>  
  
      <span data-ttu-id="60d6d-112">![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")</span><span class="sxs-lookup"><span data-stu-id="60d6d-112">![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")</span></span>  
  
5. <span data-ttu-id="60d6d-113">单击**连接器**选项卡，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="60d6d-113">Click the **Connectors** tab, and enter the following information:</span></span>  
  
   1. <span data-ttu-id="60d6d-114">**网关 ID:** 输入`LOCAL`。</span><span class="sxs-lookup"><span data-stu-id="60d6d-114">**Gateway ID:** Enter `LOCAL`.</span></span>  
  
   2. <span data-ttu-id="60d6d-115">**连接器 ID:** 输入`HTTPTARGET`。</span><span class="sxs-lookup"><span data-stu-id="60d6d-115">**Connector ID:** Enter `HTTPTARGET`.</span></span>  
  
      <span data-ttu-id="60d6d-116">![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")</span><span class="sxs-lookup"><span data-stu-id="60d6d-116">![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")</span></span>  
  
6. <span data-ttu-id="60d6d-117">单击**查找**图标。</span><span class="sxs-lookup"><span data-stu-id="60d6d-117">Click the **Lookup** icon.</span></span>  
  
7. <span data-ttu-id="60d6d-118">下**连接器 ID**，单击**HTTPTARGET**链接。</span><span class="sxs-lookup"><span data-stu-id="60d6d-118">Under **Connector ID**, click the **HTTPTARGET** link.</span></span>  
  
    <span data-ttu-id="60d6d-119">![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")</span><span class="sxs-lookup"><span data-stu-id="60d6d-119">![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")</span></span>  
  
8. <span data-ttu-id="60d6d-120">上**属性**选项卡上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="60d6d-120">On the **Properties** tab, enter the following information:</span></span>  
  
   1.  <span data-ttu-id="60d6d-121">**标头：** 输入`Y`。</span><span class="sxs-lookup"><span data-stu-id="60d6d-121">**Header:** Enter `Y`.</span></span>  
  
   2.  <span data-ttu-id="60d6d-122">**HTTPPROPERTY:** 输入`POST`。</span><span class="sxs-lookup"><span data-stu-id="60d6d-122">**HTTPPROPERTY:** Enter `POST`.</span></span>  
  
   3.  <span data-ttu-id="60d6d-123">**PrimaryURL:** 输入的 IP 地址和端口的目标计算机 （开发计算机）。</span><span class="sxs-lookup"><span data-stu-id="60d6d-123">**PrimaryURL:** Enter the IP address and port of the target computer (the development computer).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="60d6d-124">**接收端口**之前设置。</span><span class="sxs-lookup"><span data-stu-id="60d6d-124">The **Receive Port** was previously set.</span></span>  
  
    <span data-ttu-id="60d6d-125">![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")</span><span class="sxs-lookup"><span data-stu-id="60d6d-125">![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d6d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="60d6d-126">See Also</span></span>  
 [<span data-ttu-id="60d6d-127">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="60d6d-127">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)