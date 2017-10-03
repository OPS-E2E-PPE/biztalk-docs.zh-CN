---
title: "配置 SQL 适配器的绑定属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2edbd90-039a-48b4-a6fc-d825b4957207
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42576a59aae28c78250f5eba19558072e0e526d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-the-sql-adapter"></a><span data-ttu-id="74a90-102">配置 SQL 适配器的绑定属性</span><span class="sxs-lookup"><span data-stu-id="74a90-102">Configure the binding properties for the SQL adapter</span></span>
<span data-ttu-id="74a90-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]面，使您能够控制其行为特征一部分的多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="74a90-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="74a90-104">本部分提供有关设置中的绑定属性的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="74a90-104">This section provides information about setting the binding properties from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="74a90-105">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你必须指定绑定属性，以生成针对特定操作的架构。</span><span class="sxs-lookup"><span data-stu-id="74a90-105">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="74a90-106">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须指定的绑定属性作为一部分发送或接收来发送或接收消息从 SQL Server 的端口。</span><span class="sxs-lookup"><span data-stu-id="74a90-106">From [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must specify the binding properties as part of the send or receive port for sending or receiving messages from SQL Server.</span></span>  
  
 <span data-ttu-id="74a90-107">有关绑定属性的信息，包括一个绑定的属性列表[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="74a90-107">For information about the binding properties, including a list of binding properties for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="enter-the-binding-properties-in-visual-studio"></a><span data-ttu-id="74a90-108">在 Visual Studio 中输入的绑定属性</span><span class="sxs-lookup"><span data-stu-id="74a90-108">Enter the binding properties in Visual Studio</span></span>  
 <span data-ttu-id="74a90-109">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你可以指定使用的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="74a90-109">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="using-consume-adapter-service-add-in"></a><span data-ttu-id="74a90-110">使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="74a90-110">Using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="74a90-111">右键单击你的 BizTalk 项目，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="74a90-111">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="74a90-112">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74a90-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="74a90-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="74a90-113">Use this</span></span>|<span data-ttu-id="74a90-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="74a90-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="74a90-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="74a90-115">**Categories**</span></span>|<span data-ttu-id="74a90-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="74a90-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="74a90-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="74a90-117">**Templates**</span></span>|<span data-ttu-id="74a90-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="74a90-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="74a90-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="74a90-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="74a90-120">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="74a90-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="74a90-121">在**配置适配器**对话框中，单击**绑定属性**选项卡上，然后指定不同的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="74a90-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  
  
6.  <span data-ttu-id="74a90-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="74a90-122">Click **OK**.</span></span>  
  
### <a name="using-add-adapter-metadata-wizard"></a><span data-ttu-id="74a90-123">使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="74a90-123">Using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="74a90-124">右键单击 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="74a90-124">Right-click the BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="74a90-125">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74a90-125">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="74a90-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="74a90-126">Use this</span></span>|<span data-ttu-id="74a90-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="74a90-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="74a90-128">**类别**</span><span class="sxs-lookup"><span data-stu-id="74a90-128">**Categories**</span></span>|<span data-ttu-id="74a90-129">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="74a90-129">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="74a90-130">**模板**</span><span class="sxs-lookup"><span data-stu-id="74a90-130">**Templates**</span></span>|<span data-ttu-id="74a90-131">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="74a90-131">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="74a90-132">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="74a90-132">Click **Add**.</span></span> <span data-ttu-id="74a90-133">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="74a90-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="74a90-134">在添加适配器向导中，选择**WCF SQL**。</span><span class="sxs-lookup"><span data-stu-id="74a90-134">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="74a90-135">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="74a90-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="74a90-136">如果你已经在 BizTalk 中配置 WCF SQL 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="74a90-136">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="74a90-137">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="74a90-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="74a90-138">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="74a90-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="74a90-139">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="74a90-139">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="74a90-140">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="74a90-140">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74a90-141">如果你选择现有 WCF SQL 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="74a90-141">If you selected an existing WCF-SQL send port, you need not specify the binding properties.</span></span> <span data-ttu-id="74a90-142">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="74a90-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="74a90-143">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="74a90-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="74a90-144">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="74a90-144">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="74a90-145">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="74a90-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="74a90-146">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="74a90-146">Click **OK**.</span></span>  
  
## <a name="enter-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="74a90-147">从 BizTalk Server 管理控制台输入绑定属性</span><span class="sxs-lookup"><span data-stu-id="74a90-147">Enter binding properties from the BizTalk Server Administration console</span></span>  
 <span data-ttu-id="74a90-148">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，可以将 WCF 自定义或 WCF SQL 端口配置的一部分指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="74a90-148">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the binding properties as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  
  
### <a name="enter-binding-properties-for-wcf-custom-port"></a><span data-ttu-id="74a90-149">输入 WCF 自定义端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="74a90-149">Enter binding properties for WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="74a90-150">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="74a90-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="74a90-151">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="74a90-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="74a90-152">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="74a90-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="74a90-153">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="74a90-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74a90-154">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="74a90-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="74a90-155">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="74a90-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="74a90-156">从**绑定类型**列表中，选择**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="74a90-156">From the **Binding Type** list, select **sqlBinding**.</span></span>  
  
6.  <span data-ttu-id="74a90-157">在**配置**框中，为不同的绑定属性中，指定值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="74a90-157">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  
  
### <a name="enter-binding-properties-for-the-wcf-sql-port"></a><span data-ttu-id="74a90-158">输入 WCF SQL 端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="74a90-158">Enter binding properties for the WCF-SQL port</span></span>  
  
1.  <span data-ttu-id="74a90-159">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="74a90-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="74a90-160">添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="74a90-160">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="74a90-161">有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="74a90-161">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="74a90-162">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="74a90-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="74a90-163">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="74a90-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="74a90-164">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加了 WCF SQL 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="74a90-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74a90-165">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="74a90-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="74a90-166">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="74a90-166">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74a90-167">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="74a90-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="74a90-168">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="74a90-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
6.  <span data-ttu-id="74a90-169">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="74a90-169">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a90-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74a90-170">See Also</span></span>  
[<span data-ttu-id="74a90-171">开发具有 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="74a90-171">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)