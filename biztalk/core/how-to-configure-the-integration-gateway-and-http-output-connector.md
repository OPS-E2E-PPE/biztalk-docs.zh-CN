---
title: 如何配置集成网关和 HTTP 输出连接器 |Microsoft 文档
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
ms.openlocfilehash: acfa52be85a664432af95af0ca292e9cc394c6ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247917"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a><span data-ttu-id="62dd8-102">如何配置集成网关和 HTTP 输出连接器</span><span class="sxs-lookup"><span data-stu-id="62dd8-102">How to Configure the Integration Gateway and HTTP Output Connector</span></span>
<span data-ttu-id="62dd8-103">请按照下列步骤来配置集成网关和 HTTP 输出连接器。</span><span class="sxs-lookup"><span data-stu-id="62dd8-103">Follow these steps to configure the Integration Gateway and HTTP Output Connector.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="62dd8-104">若要创建和配置新的网关节点</span><span class="sxs-lookup"><span data-stu-id="62dd8-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="62dd8-105">在 Web 浏览器中，打开 PeopleSoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="62dd8-105">In a Web browser, open the PeopleSoft application.</span></span>  
  
2.  <span data-ttu-id="62dd8-106">找到**PeopleTools**，选择**集成 Broker**，然后选择**网关**。</span><span class="sxs-lookup"><span data-stu-id="62dd8-106">Locate **PeopleTools**, select **Integration Broker**, and then select **Gateways**.</span></span>  
  
3.  <span data-ttu-id="62dd8-107">在**搜索通过**字段中，键入`LOCAL`，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="62dd8-107">In the **Search By** field, type `LOCAL`, and then click **Search**.</span></span>  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  <span data-ttu-id="62dd8-108">输入`machine-name/PSIGW/PeopleSoftListeningConnector`到**网关 URL**条目。</span><span class="sxs-lookup"><span data-stu-id="62dd8-108">Enter `machine-name/PSIGW/PeopleSoftListeningConnector` into the **Gateway URL** entry.</span></span>  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  <span data-ttu-id="62dd8-109">单击**刷新**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="62dd8-109">Click **Refresh**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="62dd8-110">单击**属性**链接**HTTPTARGET**若要查看该 ID 的属性/值组合</span><span class="sxs-lookup"><span data-stu-id="62dd8-110">Click the **Properties** link for **HTTPTARGET** to view the properties/value combination for that ID.</span></span>  
  
     <span data-ttu-id="62dd8-111">您可以在这里，或者在节点定义设置 URL。</span><span class="sxs-lookup"><span data-stu-id="62dd8-111">You can set the URL here, or at the Node Definition.</span></span> <span data-ttu-id="62dd8-112">有关此讨论，在节点级别设置 URL。</span><span class="sxs-lookup"><span data-stu-id="62dd8-112">For this discussion, set the URL at the Node level.</span></span>  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a><span data-ttu-id="62dd8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62dd8-113">See Also</span></span>  
 [<span data-ttu-id="62dd8-114">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="62dd8-114">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)