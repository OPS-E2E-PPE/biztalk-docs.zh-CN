---
title: "用于 Oracle 数据库配置的绑定属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73b7a5205b2fbfe0bc42bf5af0930356a003d5be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-oracle-database"></a><span data-ttu-id="7ac42-102">用于 Oracle 数据库配置的绑定属性</span><span class="sxs-lookup"><span data-stu-id="7ac42-102">Configure the binding properties for Oracle Database</span></span>
<span data-ttu-id="7ac42-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]面，使您能够控制其行为特征一部分的多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7ac42-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="7ac42-104">本部分提供有关从 Visual Studio 和 BizTalk Server 管理控制台设置的绑定属性的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac42-104">This section provides information about setting the binding properties from Visual Studio and from the BizTalk Server Administration console.</span></span> <span data-ttu-id="7ac42-105">从 Visual Studio 中，必须在生成针对特定操作的架构时指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7ac42-105">From Visual Studio, you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="7ac42-106">从 BizTalk Server 中，必须指定绑定属性作为一部分发送或接收端口来发送或接收消息从 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7ac42-106">From BizTalk Server, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the Oracle database.</span></span>  
  
 <span data-ttu-id="7ac42-107">有关绑定属性的信息，包括一个绑定的属性列表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac42-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="7ac42-108">指定 Visual Studio 中的绑定属性</span><span class="sxs-lookup"><span data-stu-id="7ac42-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="7ac42-109">从 Visual Studio 中，你必须指定使用的凭据[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7ac42-109">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="7ac42-110">指定使用适配器服务外接程序中使用的绑定属性</span><span class="sxs-lookup"><span data-stu-id="7ac42-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="7ac42-111">右键单击你的 BizTalk 项目，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-111">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="7ac42-112">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ac42-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7ac42-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ac42-113">Use this</span></span>|<span data-ttu-id="7ac42-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ac42-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ac42-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="7ac42-115">**Categories**</span></span>|<span data-ttu-id="7ac42-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="7ac42-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="7ac42-117">**Templates**</span></span>|<span data-ttu-id="7ac42-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="7ac42-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="7ac42-120">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**oracleDBBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="7ac42-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="7ac42-121">在**配置适配器**对话框中，单击**绑定属性**选项卡上，指定不同的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7ac42-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the different binding properties.</span></span>  
  
6.  <span data-ttu-id="7ac42-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-122">Click **OK**.</span></span>  
  
#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="7ac42-123">若要指定绑定属性使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="7ac42-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="7ac42-124">右键单击你的 BizTalk 项目，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-124">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="7ac42-125">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ac42-125">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7ac42-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ac42-126">Use this</span></span>|<span data-ttu-id="7ac42-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ac42-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ac42-128">**类别**</span><span class="sxs-lookup"><span data-stu-id="7ac42-128">**Categories**</span></span>|<span data-ttu-id="7ac42-129">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-129">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="7ac42-130">**模板**</span><span class="sxs-lookup"><span data-stu-id="7ac42-130">**Templates**</span></span>|<span data-ttu-id="7ac42-131">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-131">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="7ac42-132">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-132">Click **Add**.</span></span> <span data-ttu-id="7ac42-133">添加适配器元数据向导将打开。</span><span class="sxs-lookup"><span data-stu-id="7ac42-133">The Add Adapter Metadata Wizard opens.</span></span>  
  
4.  <span data-ttu-id="7ac42-134">在添加适配器元数据向导中，选择**WCF OracleDB**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-134">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="7ac42-135">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="7ac42-135">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7ac42-136">如果你已经在 BizTalk 中配置 WCF OracleDB 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="7ac42-136">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="7ac42-137">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7ac42-138">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**oracleDBBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="7ac42-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="7ac42-139">在**配置适配器**对话框中，单击**绑定属性**选项卡，然后指定的绑定值中，如果有的话，生成架构之前所需的。</span><span class="sxs-lookup"><span data-stu-id="7ac42-139">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="7ac42-140">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac42-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ac42-141">如果你选择现有 WCF OracleDB 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7ac42-141">If you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="7ac42-142">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="7ac42-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="7ac42-143">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7ac42-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="7ac42-144">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="7ac42-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="7ac42-145">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="7ac42-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="7ac42-146">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-146">Click **OK**.</span></span>  
  
## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="7ac42-147">指定将属性绑定从 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7ac42-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="7ac42-148">从 BizTalk Server 管理控制台中，你必须作为 WCF 自定义或 WCF OracleDB 端口配置的一部分指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7ac42-148">From the BizTalk Server Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  
  
#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="7ac42-149">若要指定的 WCF 自定义端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="7ac42-149">To specify binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="7ac42-150">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7ac42-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7ac42-151">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="7ac42-152">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="7ac42-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="7ac42-153">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ac42-154">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="7ac42-155">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ac42-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="7ac42-156">从**绑定类型**下拉列表中，选择**oracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-156">From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  
  
6.  <span data-ttu-id="7ac42-157">在**配置**框中，指定不同的绑定属性的值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  
  
#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a><span data-ttu-id="7ac42-158">若要指定 WCF OracleDB 端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="7ac42-158">To specify binding properties for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="7ac42-159">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7ac42-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7ac42-160">将 WCF OracleDB 适配器添加到 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7ac42-160">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="7ac42-161">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac42-161">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="7ac42-162">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="7ac42-163">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="7ac42-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="7ac42-164">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF OracleDB 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ac42-165">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="7ac42-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="7ac42-166">在传输属性对话框中，单击**绑定**选项卡，然后指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="7ac42-166">In the transport properties dialog box, click the **Binding** tab, and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ac42-167">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="7ac42-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="7ac42-168">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="7ac42-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac42-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ac42-169">See Also</span></span>  
[<span data-ttu-id="7ac42-170">开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="7ac42-170">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)