---
title: 如何创建新的网关节点 |Microsoft 文档
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
ms.openlocfilehash: b371243d58389415349d5a88c05b7bf312e70ef9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-gateway-node"></a><span data-ttu-id="2bc60-102">如何创建新的网关节点</span><span class="sxs-lookup"><span data-stu-id="2bc60-102">How to Create a New Gateway Node</span></span>
<span data-ttu-id="2bc60-103">请按照以下步骤在 PeopleSoft Enterprise 中创建和配置新的网关节点。</span><span class="sxs-lookup"><span data-stu-id="2bc60-103">Follow these steps to create and configure a new Gateway node in PeopleSoft Enterprise.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="2bc60-104">若要创建和配置新的网关节点</span><span class="sxs-lookup"><span data-stu-id="2bc60-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="2bc60-105">在 PeopleSoft，在左面板中，单击**节点定义**链接。</span><span class="sxs-lookup"><span data-stu-id="2bc60-105">In PeopleSoft, on the left panel, click the **Node Definitions** link.</span></span>  
  
2.  <span data-ttu-id="2bc60-106">单击**添加新值**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2bc60-106">Click the **Add a New Value** tab.</span></span>  
  
3.  <span data-ttu-id="2bc60-107">在**节点名称**字段中，输入`MSEXTERNAL`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2bc60-107">In the **Node Name** field, enter `MSEXTERNAL`, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="2bc60-108">单击**节点**选项卡，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="2bc60-108">Click the **Node** tab, and enter the following information:</span></span>  
  
    1.  <span data-ttu-id="2bc60-109">**描述：**输入节点的说明。</span><span class="sxs-lookup"><span data-stu-id="2bc60-109">**Description:** Enter a description for the node.</span></span>  
  
    2.  <span data-ttu-id="2bc60-110">**节点类型：**选择**外部**。</span><span class="sxs-lookup"><span data-stu-id="2bc60-110">**Node Type:** Select **External**.</span></span>  
  
    3.  <span data-ttu-id="2bc60-111">**路由类型：**选择**隐式**。</span><span class="sxs-lookup"><span data-stu-id="2bc60-111">**Routing Type:** Select **Implicit**.</span></span>  
  
     ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5.  <span data-ttu-id="2bc60-112">单击**连接器**选项卡，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="2bc60-112">Click the **Connectors** tab, and enter the following information:</span></span>  
  
    1.  <span data-ttu-id="2bc60-113">**网关 ID:**输入`LOCAL`。</span><span class="sxs-lookup"><span data-stu-id="2bc60-113">**Gateway ID:** Enter `LOCAL`.</span></span>  
  
    2.  <span data-ttu-id="2bc60-114">**连接器 ID:**输入`HTTPTARGET`。</span><span class="sxs-lookup"><span data-stu-id="2bc60-114">**Connector ID:** Enter `HTTPTARGET`.</span></span>  
  
     ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6.  <span data-ttu-id="2bc60-115">单击**查找**图标。</span><span class="sxs-lookup"><span data-stu-id="2bc60-115">Click the **Lookup** icon.</span></span>  
  
7.  <span data-ttu-id="2bc60-116">下**连接器 ID**，单击**HTTPTARGET**链接。</span><span class="sxs-lookup"><span data-stu-id="2bc60-116">Under **Connector ID**, click the **HTTPTARGET** link.</span></span>  
  
     ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8.  <span data-ttu-id="2bc60-117">上**属性**选项卡上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="2bc60-117">On the **Properties** tab, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="2bc60-118">**标头：**输入`Y`。</span><span class="sxs-lookup"><span data-stu-id="2bc60-118">**Header:** Enter `Y`.</span></span>  
  
    2.  <span data-ttu-id="2bc60-119">**HTTPPROPERTY:**输入`POST`。</span><span class="sxs-lookup"><span data-stu-id="2bc60-119">**HTTPPROPERTY:** Enter `POST`.</span></span>  
  
    3.  <span data-ttu-id="2bc60-120">**PrimaryURL:**输入的 IP 地址和端口的目标计算机 （的开发计算机）。</span><span class="sxs-lookup"><span data-stu-id="2bc60-120">**PrimaryURL:** Enter the IP address and port of the target computer (the development computer).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bc60-121">**接收端口**之前已设置。</span><span class="sxs-lookup"><span data-stu-id="2bc60-121">The **Receive Port** was previously set.</span></span>  
  
     ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a><span data-ttu-id="2bc60-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bc60-122">See Also</span></span>  
 [<span data-ttu-id="2bc60-123">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="2bc60-123">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)