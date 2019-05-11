---
title: 如何配置集成网关和 HTTP 输出连接器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Integration Gateway
- gateway nodes, creating
- HTTP Output Connector
ms.assetid: a02ee533-07a8-42fa-a72a-7e5359b18f40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b054893004f270ca352dc537c60ef8fcb719cba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340834"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a><span data-ttu-id="0823e-102">如何配置集成网关和 HTTP 输出连接器</span><span class="sxs-lookup"><span data-stu-id="0823e-102">How to Configure the Integration Gateway and HTTP Output Connector</span></span>
<span data-ttu-id="0823e-103">请按照下列步骤以配置集成网关和 HTTP 输出连接器。</span><span class="sxs-lookup"><span data-stu-id="0823e-103">Follow these steps to configure the Integration Gateway and HTTP Output Connector.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="0823e-104">若要创建和配置新的网关节点</span><span class="sxs-lookup"><span data-stu-id="0823e-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="0823e-105">在 Web 浏览器中打开 PeopleSoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0823e-105">In a Web browser, open the PeopleSoft application.</span></span>  
  
2.  <span data-ttu-id="0823e-106">找到**PeopleTools**，选择**Integration Broker**，然后选择**网关**。</span><span class="sxs-lookup"><span data-stu-id="0823e-106">Locate **PeopleTools**, select **Integration Broker**, and then select **Gateways**.</span></span>  
  
3.  <span data-ttu-id="0823e-107">在中**Search By**字段中，键入`LOCAL`，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="0823e-107">In the **Search By** field, type `LOCAL`, and then click **Search**.</span></span>  
  
     <span data-ttu-id="0823e-108">![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")</span><span class="sxs-lookup"><span data-stu-id="0823e-108">![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")</span></span>  
  
4.  <span data-ttu-id="0823e-109">输入`machine-name/PSIGW/PeopleSoftListeningConnector`成**网关 URL**条目。</span><span class="sxs-lookup"><span data-stu-id="0823e-109">Enter `machine-name/PSIGW/PeopleSoftListeningConnector` into the **Gateway URL** entry.</span></span>  
  
     <span data-ttu-id="0823e-110">![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")</span><span class="sxs-lookup"><span data-stu-id="0823e-110">![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")</span></span>  
  
5.  <span data-ttu-id="0823e-111">单击**刷新**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="0823e-111">Click **Refresh**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="0823e-112">单击**属性**中的链接**HTTPTARGET**若要查看属性/值组合为该 id。</span><span class="sxs-lookup"><span data-stu-id="0823e-112">Click the **Properties** link for **HTTPTARGET** to view the properties/value combination for that ID.</span></span>  
  
     <span data-ttu-id="0823e-113">您可以在这里，或者在节点定义设置 URL。</span><span class="sxs-lookup"><span data-stu-id="0823e-113">You can set the URL here, or at the Node Definition.</span></span> <span data-ttu-id="0823e-114">本次讨论中，在节点级别设置 URL。</span><span class="sxs-lookup"><span data-stu-id="0823e-114">For this discussion, set the URL at the Node level.</span></span>  
  
     <span data-ttu-id="0823e-115">![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")</span><span class="sxs-lookup"><span data-stu-id="0823e-115">![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0823e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0823e-116">See Also</span></span>  
 [<span data-ttu-id="0823e-117">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="0823e-117">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)