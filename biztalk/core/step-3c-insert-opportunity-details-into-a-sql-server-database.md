---
title: "步骤 3c: SQL Server 数据库中插入机会详细信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d0055c05e0c9af9f4dddc4a7275c01ff49d779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a><span data-ttu-id="2f277-102">步骤 3c: SQL Server 数据库中插入机会详细信息</span><span class="sxs-lookup"><span data-stu-id="2f277-102">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>
<span data-ttu-id="2f277-103">迄今，我们已构建用于将查询发送到 Salesforce 并接收响应的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2f277-103">By now we have built the orchestration to send a query to Salesforce and receive a response.</span></span> <span data-ttu-id="2f277-104">在此部分中，我们将更新该业务流程将响应来自 Salesforce 到**OrderDetails**在本地 SQL Server 数据库中，表**订单**。</span><span class="sxs-lookup"><span data-stu-id="2f277-104">In this section, we’ll update that orchestration to insert the response from Salesforce into an **OrderDetails** table in an on-premise SQL Server database, **Orders**.</span></span> <span data-ttu-id="2f277-105">为此，我们将执行以下广泛的步骤：</span><span class="sxs-lookup"><span data-stu-id="2f277-105">To achieve this, we’ll perform the following broad set of steps:</span></span>  
  
-   <span data-ttu-id="2f277-106">创建**OrderDetails**表中**订单**本地 SQL Server 数据库中的数据库。</span><span class="sxs-lookup"><span data-stu-id="2f277-106">Create an **OrderDetails** table in an **Orders** database in an on-premise SQL Server database.</span></span>  
  
-   <span data-ttu-id="2f277-107">使用[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]适用于[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]上生成 Insert 操作架构**OrderDetails**表。</span><span class="sxs-lookup"><span data-stu-id="2f277-107">Use the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] available with [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to generate the schema for the Insert operation on the **OrderDetails** table.</span></span>  
  
-   <span data-ttu-id="2f277-108">创建一个映射，以便转换 Salesforce 响应消息与用于插入到消息**OrderDetails** SQL Server 中的表。</span><span class="sxs-lookup"><span data-stu-id="2f277-108">Create a map to transform the Salesforce response message to the message for inserting into **OrderDetails** table in SQL Server.</span></span>  
  
-   <span data-ttu-id="2f277-109">更新业务流程用于转换插入到响应消息**OrderDetails**表。</span><span class="sxs-lookup"><span data-stu-id="2f277-109">Update the orchestration to use the transform to insert the response message into the **OrderDetails** table.</span></span>  
  
## <a name="create-sql-server-database-and-table"></a><span data-ttu-id="2f277-110">创建 SQL Server 数据库和表</span><span class="sxs-lookup"><span data-stu-id="2f277-110">Create SQL Server Database and Table</span></span>  
  
#### <a name="to-create-the-database-and-table"></a><span data-ttu-id="2f277-111">创建数据库和表</span><span class="sxs-lookup"><span data-stu-id="2f277-111">To create the database and table</span></span>  
  
1.  <span data-ttu-id="2f277-112">打开 SQL Server Management Studio 并以管理员身份连接。</span><span class="sxs-lookup"><span data-stu-id="2f277-112">Open SQL Server Management Studio and connect as an administrator.</span></span>  
  
2.  <span data-ttu-id="2f277-113">右键单击**数据库**节点，然后单击**新数据库**。</span><span class="sxs-lookup"><span data-stu-id="2f277-113">Right-click the **Databases** node and click **New Database**.</span></span> <span data-ttu-id="2f277-114">指定数据库名称作为`Orders`并指定其他详细信息，以创建新的数据库。</span><span class="sxs-lookup"><span data-stu-id="2f277-114">Specify the database name as `Orders` and specify other details to create a new database.</span></span>  
  
3.  <span data-ttu-id="2f277-115">打开查询编辑器并运行以下查询以创建**OrderDetails**表中**订单**数据库：</span><span class="sxs-lookup"><span data-stu-id="2f277-115">Open a query editor and run the following query to create an **OrderDetails** table in the **Orders** database:</span></span>  
  
    ```  
    USE [Orders]  
    GO  
    /****** Object:  Table [dbo].[OrderDetails]    Script Date: 07-12-2012 22:15:47 ******/  
    SET ANSI_NULLS ON  
    GO  
    SET QUOTED_IDENTIFIER ON  
    GO  
    SET ANSI_PADDING ON  
    GO  
    CREATE TABLE [dbo].[OrderDetails]([ID] [int] IDENTITY(1,1) NOT NULL,  
    [TITLE] [varchar](200) NULL,  
    [ProductName] [varchar](200) NULL,  
    [Quantity] [float] NULL,  
    [Amount] [float] NULL,  
    PRIMARY KEY CLUSTERED   
    (  
    [ID] ASC  
    )WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
    GO  
    SET ANSI_PADDING OFF  
    GO  
    ```  
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a><span data-ttu-id="2f277-116">创建用于对 OrderDetails 表执行 Insert 操作的架构</span><span class="sxs-lookup"><span data-stu-id="2f277-116">Create Schema for Insert Operation on OrderDetails Table</span></span>  
 <span data-ttu-id="2f277-117">安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]，它可以用于中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目以生成 Insert 操作的架构上**OrderDetails**表。</span><span class="sxs-lookup"><span data-stu-id="2f277-117">Installing [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] provides a [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] that can be used within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project to generate the schema for the Insert operation on the **OrderDetails** table.</span></span> <span data-ttu-id="2f277-118">本部分提供创建消息架构时要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="2f277-118">This section provides steps to follow to create the message schema.</span></span>  
  
#### <a name="to-create-the-schema-for-insert-operation"></a><span data-ttu-id="2f277-119">创建用于 Insert 操作的架构</span><span class="sxs-lookup"><span data-stu-id="2f277-119">To create the schema for Insert operation</span></span>  
  
1.  <span data-ttu-id="2f277-120">右键单击**BtsSalesforceIntegration**项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="2f277-120">Right-click the **BtsSalesforceIntegration** project, point to **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="2f277-121">在**添加生成的项**对话框中，单击**使用适配器服务**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2f277-121">In the **Add Generated Items** dialog box, click **Consume Adapter Service**, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="2f277-122">在[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]，从选择绑定的下拉列表中，单击**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="2f277-122">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)], from the Select a binding drop-down, click **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="2f277-123">在**配置适配器**对话框中，在**安全**选项卡上，为**客户端凭据类型**，选择**Windows**为使用 Windows若要连接到 SQL Server 数据库的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2f277-123">In the **Configure Adapter** dialog box, under **Security** tab, for **Client credential type**, select **Windows** to use Windows authentication to connect to SQL Server database.</span></span>  
  
4.  <span data-ttu-id="2f277-124">在**配置适配器**对话框中，在**URI 属性**选项卡上，为**初始目录**指定 (Orders) 连接到的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="2f277-124">In the **Configure Adapter** dialog box, under **URI Properties** tab, for **Initial Catalog** specify the database name (Orders) to connect to.</span></span> <span data-ttu-id="2f277-125">有关**服务器**指定安装了你要连接到的 SQL Server 的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="2f277-125">For **Server** specify the computer name where SQL Server you are connecting to is installed.</span></span> <span data-ttu-id="2f277-126">SQL Server 数据库是否为同一台计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目中，可以只将期间 (**。**)。</span><span class="sxs-lookup"><span data-stu-id="2f277-126">If the SQL Server database is on the same computer as the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, you can just put a period (**.**).</span></span> <span data-ttu-id="2f277-127">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2f277-127">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2f277-128">在[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="2f277-128">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] click **Connect**.</span></span> <span data-ttu-id="2f277-129">建立连接后，选择与具有协定类型**客户端 （出站操作）**。</span><span class="sxs-lookup"><span data-stu-id="2f277-129">After the connection is established, select the contract type as **Client(Outbound operations)**.</span></span> <span data-ttu-id="2f277-130">下**选择类别**框中，展开**表**，单击**OrderDetails**表，然后在右窗格中单击**插入**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2f277-130">Under the **Select a category** box, expand **Tables**, click **OrderDetails** table, and in the right pane click **Insert** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="2f277-131">指定**文件名前缀**如果你想要前缀标识符与生成的架构。</span><span class="sxs-lookup"><span data-stu-id="2f277-131">Specify a **Filename Prefix** if you want to prefix the generated schemas with an identifier.</span></span> <span data-ttu-id="2f277-132">对于本教程，让我们指定作为前缀**InsertOrders** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2f277-132">For this tutorial, let’s specify the prefix as **InsertOrders** and then click **OK**.</span></span>  
  
     <span data-ttu-id="2f277-133">此时，多个架构将添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="2f277-133">A bunch of schemas are added to the project.</span></span> <span data-ttu-id="2f277-134">我们将使用用于插入到消息的架构**OrderDetails**表是**InsertOrdersTableOperation.dbo.OrderDetails.xsd**。</span><span class="sxs-lookup"><span data-stu-id="2f277-134">The schema that we’ll use for inserting messages into the **OrderDetails** table is **InsertOrdersTableOperation.dbo.OrderDetails.xsd**.</span></span>  
  
## <a name="map-salesforce-response-and-insert-schemas"></a><span data-ttu-id="2f277-135">映射 Salesforce 响应架构和插入架构</span><span class="sxs-lookup"><span data-stu-id="2f277-135">Map Salesforce Response and Insert Schemas</span></span>  
 <span data-ttu-id="2f277-136">现在，我们有两个架构 (来自 Salesforce 并将插入到响应**OrderDetails**)，我们必须映射到 insert 架构从 Salesforce 响应架构**OrderDetails**以便可以在 SQL Server 数据库表中插入从 Salesforce 的响应消息。</span><span class="sxs-lookup"><span data-stu-id="2f277-136">Now that we have both the schemas (response from Salesforce and inserting into **OrderDetails**), we must map the response schema from Salesforce into the insert schema for **OrderDetails** so that the response message from Salesforce can be inserted in the SQL Server database table.</span></span>  
  
#### <a name="to-map-the-schemas"></a><span data-ttu-id="2f277-137">若要将架构映射</span><span class="sxs-lookup"><span data-stu-id="2f277-137">To map the schemas</span></span>  
  
1.  <span data-ttu-id="2f277-138">右键单击**BtsSalesforceIntegration**项目，指向**添加**，单击**新项**，然后单击**映射**。</span><span class="sxs-lookup"><span data-stu-id="2f277-138">Right-click the **BtsSalesforceIntegration** project, point to **Add**, click **New Item**, and then click **Map**.</span></span> <span data-ttu-id="2f277-139">将映射名称指定为`QueryResult_Orders.btm`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2f277-139">Specify the map name as `QueryResult_Orders.btm` and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="2f277-140">在代码图图面，对于源架构中，选择**QueryResult**和对于目标架构中，选择**InsertOrdersTableOperation.dbo.OrderDetails.xsd** ，其中，然后**插入**节点。</span><span class="sxs-lookup"><span data-stu-id="2f277-140">On the map surface, for the source schema, select **QueryResult** and for the destination schema, select **InsertOrdersTableOperation.dbo.OrderDetails.xsd** and then within that, the **Insert** node.</span></span>  
  
3.  <span data-ttu-id="2f277-141">映射这两个架构，如下面的屏幕快照中所示：</span><span class="sxs-lookup"><span data-stu-id="2f277-141">Map the two schemas as shown in the following screenshot:</span></span>  
  
     <span data-ttu-id="2f277-142">![映射到 Insert 架构的 Salesforce 响应](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span><span class="sxs-lookup"><span data-stu-id="2f277-142">![Map Salesforce response to Insert schema](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span></span>  
  
     <span data-ttu-id="2f277-143">请注意，地图使用**循环**之间 functoid**记录**和**OrderDetails**链接。</span><span class="sxs-lookup"><span data-stu-id="2f277-143">Notice that the map uses a **Looping** functoid between the **records** and the **OrderDetails** link.</span></span> <span data-ttu-id="2f277-144">这样可确保所有一个或多个匹配项下的节点**记录**映射到类似出现下的子节点的**OrderDetails**。</span><span class="sxs-lookup"><span data-stu-id="2f277-144">This ensures that all one or more than one occurrences of nodes under **records** are mapped to similar occurrences of nodes under the **OrderDetails**.</span></span>  
  
4.  <span data-ttu-id="2f277-145">保存对映射所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2f277-145">Save changes to the map.</span></span>  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a><span data-ttu-id="2f277-146">更新业务流程，以将消息插入到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f277-146">Update the Orchestration to Insert Messages into SQL Server</span></span>  
 <span data-ttu-id="2f277-147">在此部分中，我们将在业务流程中使用映射，将 Salesforce 响应消息转换为用于将订单详细信息插入到 SQL Server 表的消息。</span><span class="sxs-lookup"><span data-stu-id="2f277-147">In this section, we’ll use the map in the orchestration to transform the Salesforce response message into a message for inserting order details in a SQL Server table.</span></span> <span data-ttu-id="2f277-148">我们还将添加用于将该消息发送到 SQL Server 的端口。</span><span class="sxs-lookup"><span data-stu-id="2f277-148">We’ll also add a port to send that message to SQL Server.</span></span>  
  
#### <a name="to-update-the-orchestration"></a><span data-ttu-id="2f277-149">若要更新业务流程</span><span class="sxs-lookup"><span data-stu-id="2f277-149">To update the orchestration</span></span>  
  
1.  <span data-ttu-id="2f277-150">为插入架构创建消息变量。</span><span class="sxs-lookup"><span data-stu-id="2f277-150">Create a message variable for the insert schema.</span></span> <span data-ttu-id="2f277-151">在业务流程视图中，右键单击**消息**节点，，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="2f277-151">From the orchestration view, right-click the **Messages** node, and then click **New Message**.</span></span> <span data-ttu-id="2f277-152">设置消息同名**InsertOrders**和消息类型作为**BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**。</span><span class="sxs-lookup"><span data-stu-id="2f277-152">Set the message name as **InsertOrders** and message type as **BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**.</span></span>  
  
2.  <span data-ttu-id="2f277-153">添加后的构造消息形状**ReceiveQueryResult**形状。</span><span class="sxs-lookup"><span data-stu-id="2f277-153">Add a Construct Message shape after the **ReceiveQueryResult** shape.</span></span> <span data-ttu-id="2f277-154">设置到形状的名称`ConstructOrders`并设置**消息构造**属性**InsertOrders**。</span><span class="sxs-lookup"><span data-stu-id="2f277-154">Set the name of the shape to `ConstructOrders` and set the **Messages Constructed** property to **InsertOrders**.</span></span>  
  
3.  <span data-ttu-id="2f277-155">在**ConstructOrders**形状，添加**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="2f277-155">Within the **ConstructOrders** shape, add a **Transform** shape.</span></span> <span data-ttu-id="2f277-156">双击“转换”形状以打开“转换配置”对话框。</span><span class="sxs-lookup"><span data-stu-id="2f277-156">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="2f277-157">在对话框中，选择**现有映射**选项，然后再从下拉列表选中**BtsSalesforceIntegration.QueryResult_Orders**。</span><span class="sxs-lookup"><span data-stu-id="2f277-157">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.QueryResult_Orders**.</span></span> <span data-ttu-id="2f277-158">设置**源**到**QueryResultMsg**，**目标**到**InsertOrders**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2f277-158">Set **Source** to **QueryResultMsg**, **Destination** to **InsertOrders**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2f277-159">后**ConstructOrders**形状，添加发送形状。</span><span class="sxs-lookup"><span data-stu-id="2f277-159">After the **ConstructOrders** shape, add a Send shape.</span></span> <span data-ttu-id="2f277-160">命名形状`SendOrders`和将消息类型设置为**InsertOrders**。</span><span class="sxs-lookup"><span data-stu-id="2f277-160">Name the shape `SendOrders` and set the message type as **InsertOrders**.</span></span>  
  
5.  <span data-ttu-id="2f277-161">添加用于将订单详细信息插入到 Salesforce 的端口。</span><span class="sxs-lookup"><span data-stu-id="2f277-161">Add a port to insert order details into Salesforce.</span></span> <span data-ttu-id="2f277-162">在“端口配置”向导中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="2f277-162">In the Port Configuration wizard, select the following options:</span></span>  
  
    -   <span data-ttu-id="2f277-163">将端口名称指定为`SendToSQL`。</span><span class="sxs-lookup"><span data-stu-id="2f277-163">Specify the port name as `SendToSQL`.</span></span>  
  
    -   <span data-ttu-id="2f277-164">选择用于创建新的端口类型的选项。</span><span class="sxs-lookup"><span data-stu-id="2f277-164">Select the option to create a new port type.</span></span>  
  
    -   <span data-ttu-id="2f277-165">设置**通信模式**到*单向*。</span><span class="sxs-lookup"><span data-stu-id="2f277-165">Set **Communication Pattern** to *One-Way*.</span></span>  
  
    -   <span data-ttu-id="2f277-166">设置**端口的通信的方向**到*我将始终发送消息上此端口*并设置**端口绑定**到*稍后指定*。</span><span class="sxs-lookup"><span data-stu-id="2f277-166">Set **Port direction of communication** to *I’ll always be sending messages on this port* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="2f277-167">连接**请求**操作到端口**SendOrders**发送形状来完成业务流程。</span><span class="sxs-lookup"><span data-stu-id="2f277-167">Connect the **Request** operation of port to the **SendOrders** Send shape to complete the orchestration.</span></span> <span data-ttu-id="2f277-168">以下屏幕快照描述了已完成的业务流程（端到端）。</span><span class="sxs-lookup"><span data-stu-id="2f277-168">The following screenshot depicts the completed orchestration, end-to-end.</span></span>  
  
     <span data-ttu-id="2f277-169">![Salesforce 集成的完整 orchesration](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span><span class="sxs-lookup"><span data-stu-id="2f277-169">![Complete orchesration for Salesforce integration](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span></span>  
  
     <span data-ttu-id="2f277-170">向项目添加强名称密钥文件，并保存对项目所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2f277-170">Add a strong name key file to the project and save changes to the project.</span></span>  
  
 <span data-ttu-id="2f277-171">使用本主题中的步骤，我们已经完成业务流程，以接收来自 Salesforce 的机会通知，查询 Salesforce 以获取有关机会的详细信息，然后将查询响应插入到 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="2f277-171">With the steps in this topic, we have completed the orchestration, to receive an opportunity notification from Salesforce, query Salesforce for more details about the opportunity, and then insert the query response into a SQL Server database.</span></span> <span data-ttu-id="2f277-172">在随后的主题中，我们将构建此解决方案的其他一些关键组件，这些组件用于向 Salesforce 进行身份验证，并在 BizTalk Server 内处理 Salesforce 响应。</span><span class="sxs-lookup"><span data-stu-id="2f277-172">In the subsequent topics, we’ll build some other key components of the solution that are used to authenticate with Salesforce and process Salesforce response within BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f277-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f277-173">See Also</span></span>  
 [<span data-ttu-id="2f277-174">步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案</span><span class="sxs-lookup"><span data-stu-id="2f277-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)