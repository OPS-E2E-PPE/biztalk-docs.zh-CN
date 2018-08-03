---
title: 步骤 7： 创建和配置端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44a9696f907928f31a740e4d8545567921a82df9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965235"
---
# <a name="step-7-creating-and-configuring-ports"></a><span data-ttu-id="233a7-102">步骤 7： 创建和配置端口</span><span class="sxs-lookup"><span data-stu-id="233a7-102">Step 7: Creating and Configuring Ports</span></span>
<span data-ttu-id="233a7-103">在此步骤中，您将创建和配置用于与业务流程进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="233a7-103">In this step, you create and configure the ports you use to communicate with business processes.</span></span> <span data-ttu-id="233a7-104">每个端口都具有类型、方向和绑定属性。</span><span class="sxs-lookup"><span data-stu-id="233a7-104">Each port has a type, direction, and binding property.</span></span> <span data-ttu-id="233a7-105">这些属性确定通信的方向和模式、发送或接收消息的位置以及通信方式。</span><span class="sxs-lookup"><span data-stu-id="233a7-105">These properties establish the direction and pattern of communication, the location of where the message is sent or received, and how the communication occurs.</span></span>  
  
### <a name="to-create-a-logical-send-port"></a><span data-ttu-id="233a7-106">创建逻辑发送端口</span><span class="sxs-lookup"><span data-stu-id="233a7-106">To create a logical send port</span></span>  
  
1.  <span data-ttu-id="233a7-107">在 Visual Studio 中，从工具箱拖动**端口**形状变为业务流程设计图面并将其放在**端口图面**以打开**端口配置向导**。</span><span class="sxs-lookup"><span data-stu-id="233a7-107">In Visual Studio, from the Toolbox, drag the **Port** shape to the orchestration design surface and drop it on the **Port Surface** to open the **Port Configuration Wizard**.</span></span>  
  
2.  <span data-ttu-id="233a7-108">上**端口配置向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="233a7-108">On the **Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="233a7-109">上**端口属性**页上，在**名称**框中，键入**ContosoSQLReqResponsePort**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="233a7-109">On the **Port Properties** page, in the **Name** box, type **ContosoSQLReqResponsePort**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="233a7-110">上**选择端口类型**页上，在**端口类型名称**框中，键入**ContosoSQLReqResponsePortName**。</span><span class="sxs-lookup"><span data-stu-id="233a7-110">On the **Select a Port Type** page, in the **Port Type Name** box, type **ContosoSQLReqResponsePortName**.</span></span>  
  
5.  <span data-ttu-id="233a7-111">有关**通信模式**，选择**请求-响应**。</span><span class="sxs-lookup"><span data-stu-id="233a7-111">For **Communication Pattern**, select **Request-Response**.</span></span>  
  
6.  <span data-ttu-id="233a7-112">有关**访问限制**，选择**内部使用-局限于此项目**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="233a7-112">For **Access Restrictions**, select **Internal - limited to this project**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="233a7-113">上**端口绑定**页上，选择**我将发送请求并接收响应**，保留**端口绑定**选项设置为**指定更高版本**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="233a7-113">On the **Port Binding** page, select **I'll be sending a request and receiving a response**, leave the **Port Binding** option set to **Specify Later**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="233a7-114">单击**完成**以创建该端口。</span><span class="sxs-lookup"><span data-stu-id="233a7-114">Click **Finish** to create the port.</span></span>  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a><span data-ttu-id="233a7-115">更改业务流程端口的变量类型</span><span class="sxs-lookup"><span data-stu-id="233a7-115">To change the variable type for the orchestration ports</span></span>  
  
1.  <span data-ttu-id="233a7-116">在业务流程视图中，展开**类型**，展开**端口类型**，展开**ContosoSQLReqResponsePortName**，展开**Operation_1**，然后选择**请求**。</span><span class="sxs-lookup"><span data-stu-id="233a7-116">In Orchestration View, expand **Types**, expand **Port Types**, expand **ContosoSQLReqResponsePortName**, expand **Operation_1**, and then select **Request**.</span></span>  
  
2.  <span data-ttu-id="233a7-117">在属性窗口中，选择**消息类型**属性中，展开**架构**，然后单击**\<从引用的程序集选择\>**.</span><span class="sxs-lookup"><span data-stu-id="233a7-117">In the Properties window, select the **Message Type** property, expand **Schemas** and then click **\<Select from referenced assembly\>**.</span></span>  
  
3.  <span data-ttu-id="233a7-118">在选择项目类型对话框中，单击**ContosoPriceAndAvailability**。</span><span class="sxs-lookup"><span data-stu-id="233a7-118">In the Select Artifact Type dialog box, click **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="233a7-119">在右窗格中，选择**rootPriceRequest**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="233a7-119">In the right pane, select **rootPriceRequest**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="233a7-120">在业务流程视图中，在**Operation_1**，选择**响应**为**ContosoSQLReqResponsePortName**端口类型。</span><span class="sxs-lookup"><span data-stu-id="233a7-120">In Orchestration View, under **Operation_1**, select **Response** for the **ContosoSQLReqResponsePortName** port type.</span></span>  
  
6.  <span data-ttu-id="233a7-121">在属性窗口中，选择**消息类型**属性中，展开**架构**，然后单击\<**从引用的程序集选择\>**.</span><span class="sxs-lookup"><span data-stu-id="233a7-121">In the Properties window, select the **Message Type** property, expand **Schemas** and then click \<**Select from referenced assembly\>**.</span></span>  
  
7.  <span data-ttu-id="233a7-122">在**选择项目类型**对话框中，单击**ContosoPriceAndAvailability**。</span><span class="sxs-lookup"><span data-stu-id="233a7-122">In the **Select Artifact Type** dialog box, click **ContosoPriceAndAvailability**.</span></span>  
  
8.  <span data-ttu-id="233a7-123">在右窗格中，选择**rootPriceResponse**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="233a7-123">In the right pane, select **rootPriceResponse**, and then click **OK**.</span></span>  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a><span data-ttu-id="233a7-124">将端口连接到“接收”形状</span><span class="sxs-lookup"><span data-stu-id="233a7-124">To connect the ports to the Receive shapes</span></span>  
  
1.  <span data-ttu-id="233a7-125">在业务流程设计图面上，选择**Send_1**形状。</span><span class="sxs-lookup"><span data-stu-id="233a7-125">On the orchestration design surface, select the **Send_1** shape.</span></span>  
  
2.  <span data-ttu-id="233a7-126">在属性窗口中，选择**消息**属性，，然后选择**Contoso3A2RequestMessage**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="233a7-126">In the Properties window, select the **Message** property, and then select **Contoso3A2RequestMessage** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="233a7-127">连接**ContosoSQLReqResponsePort**通过旁边选择绿色句柄**请求**标签和将其拖到绿色句柄**Send_1**形状。</span><span class="sxs-lookup"><span data-stu-id="233a7-127">Connect the **ContosoSQLReqResponsePort** by selecting the green handle next to the **Request** label and dragging it to the green handle on the **Send_1** shape.</span></span>  
  
4.  <span data-ttu-id="233a7-128">在业务流程设计图面上，选择**Receive_1**形状。</span><span class="sxs-lookup"><span data-stu-id="233a7-128">On the orchestration design surface, select the **Receive_1** shape.</span></span>  
  
5.  <span data-ttu-id="233a7-129">在属性窗口中，选择**消息**属性，，然后选择**Contoso3A2ResponseMessage**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="233a7-129">In the Properties window, select the **Message** property, and then select **Contoso3A2ResponseMessage** from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="233a7-130">连接**ContosoSQLReqResponsePort**通过旁边选择绿色句柄**响应**标签和将其拖到绿色句柄**Receive_1**形状。</span><span class="sxs-lookup"><span data-stu-id="233a7-130">Connect the **ContosoSQLReqResponsePort** by selecting the green handle next to the **Response** label and dragging it to the green handle on the **Receive_1** shape.</span></span>  
  
7.  <span data-ttu-id="233a7-131">在**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="233a7-131">In the **File** Menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233a7-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="233a7-132">See Also</span></span>  
 [<span data-ttu-id="233a7-133">步骤 8：生成和部署 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="233a7-133">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)