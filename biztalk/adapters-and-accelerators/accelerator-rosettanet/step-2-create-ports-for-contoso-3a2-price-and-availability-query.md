---
title: 步骤 2： 为 Contoso 3A2 价格和可用性查询响应方案中使用 BizTalk 资源管理器创建端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
ms.assetid: e0b12a96-e799-47ac-8293-7de10662bdf0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64101a31b1d1ea9c7af00471c5d764a1d8cfe598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210141"
---
# <a name="step-2-creating-ports-for-the-contoso-3a2-price-and-availability-queryresponse-scenario"></a><span data-ttu-id="ed171-102">步骤 2： 为 Contoso 3A2 价格和可用性查询/响应方案创建端口</span><span class="sxs-lookup"><span data-stu-id="ed171-102">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>
<span data-ttu-id="ed171-103">在此步骤中，你可以创建使用 BizTalk Server 提供的 SQL 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ed171-103">In this step, you create send ports using the SQL adapter provided by BizTalk Server.</span></span> <span data-ttu-id="ed171-104">该 SQL 端口将用于向 Contoso ERP 系统发送 3A2 价格与可用性响应，及从 Contoso ERP 系统接收 3A2 价格与可用性响应。</span><span class="sxs-lookup"><span data-stu-id="ed171-104">You use the SQL port for sending and receiving the 3A2 Price and Availability response to and from the ERP system for Contoso.</span></span>  
  
### <a name="to-configure-a-send-port-using-the-sql-adapter"></a><span data-ttu-id="ed171-105">使用 SQL 适配器配置发送端口</span><span class="sxs-lookup"><span data-stu-id="ed171-105">To configure a send port using the SQL adapter</span></span>  
  
1.  <span data-ttu-id="ed171-106">在 Visual Studio 中，在**视图**菜单上，单击**BizTalk 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="ed171-106">In Visual Studio, on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="ed171-107">在 BizTalk 资源管理器中，右键单击**发送端口**，然后单击**添加发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ed171-107">In BizTalk Explorer, right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="ed171-108">在创建新发送端口对话框中，选择**静态请求-响应端口**从下拉列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ed171-108">In the Create New Send Port dialog box, select **Static Solicit-Response Port** from the drop-down list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="ed171-109">在静态请求-响应发送端口属性对话框中，在**名称**框中，键入**3A2SQLReqResponseSendPort**。</span><span class="sxs-lookup"><span data-stu-id="ed171-109">In the Static Solicit-Response Send Port Properties dialog box, in the **Name** box, type **3A2SQLReqResponseSendPort**.</span></span>  
  
5.  <span data-ttu-id="ed171-110">下的属性窗口中**常规**标题下，选择**SQL**作为**传输类型**。</span><span class="sxs-lookup"><span data-stu-id="ed171-110">In the Properties window under the **General** heading, select **SQL** as the **Transport Type**.</span></span>  
  
6.  <span data-ttu-id="ed171-111">在**地址 URI**框中，单击省略号按钮 (**...**).</span><span class="sxs-lookup"><span data-stu-id="ed171-111">In the **Address URI** box, click the ellipsis button (**…**).</span></span>  
  
7.  <span data-ttu-id="ed171-112">在 SQL 传输属性对话框中，单击省略号按钮 (**...**) 旁边**连接字符串**框。</span><span class="sxs-lookup"><span data-stu-id="ed171-112">In the SQL Transport Properties dialog box, click the ellipsis button (**…**) next to the **Connection String** box.</span></span>  
  
8.  <span data-ttu-id="ed171-113">在数据链接属性对话框中，在**选择或输入服务器名称**框中，键入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="ed171-113">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span>  
  
9. <span data-ttu-id="ed171-114">选择**使用 Windows NT 集成安全性**。</span><span class="sxs-lookup"><span data-stu-id="ed171-114">Select **Use Windows NT Integrated security**.</span></span>  
  
10. <span data-ttu-id="ed171-115">在**选择服务器上的数据库**框中，选择**Contoso**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ed171-115">In the **Select the database on the server** box, select **Contoso**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="ed171-116">在 SQL 传输属性对话框中，在**文档目标 Namespace**框中，键入**http://Contoso.com/Price**。</span><span class="sxs-lookup"><span data-stu-id="ed171-116">In the SQL Transport Properties dialog box, in the **Document Target Namespace** box, type **http://Contoso.com/Price**.</span></span>  
  
12. <span data-ttu-id="ed171-117">在**响应文档根元素名称**框中，键入**rootPriceResponse**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ed171-117">In the **Response Document Root Element Name** box, type **rootPriceResponse**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="ed171-118">在静态的请求-响应发送端口属性对话框的左窗格中，单击**发送**。</span><span class="sxs-lookup"><span data-stu-id="ed171-118">In the left pane of the Static Solicit-Response Send Port Properties dialog box, click **Send**.</span></span>  
  
14. <span data-ttu-id="ed171-119">在静态请求-响应发送端口属性-配置-发送的常规对话框中，在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="ed171-119">In the Static Solicit-Response Send Port Properties-Configurations-Send-General dialog box, in the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
15. <span data-ttu-id="ed171-120">在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ed171-120">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="ed171-121">在 BizTalk 资源管理器中，右键单击**3A2SQLReqResponseSendPort**，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="ed171-121">In BizTalk Explorer, right-click **3A2SQLReqResponseSendPort**, and then click **Enlist**.</span></span> <span data-ttu-id="ed171-122">再次右键单击它，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="ed171-122">Right-click it again, and click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed171-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed171-123">See Also</span></span>  
 [<span data-ttu-id="ed171-124">创建和修改 Contoso 私有过程</span><span class="sxs-lookup"><span data-stu-id="ed171-124">Creating and Modifying the Private Process for Contoso</span></span>](creating-and-modifying-the-private-process-for-contoso.md)