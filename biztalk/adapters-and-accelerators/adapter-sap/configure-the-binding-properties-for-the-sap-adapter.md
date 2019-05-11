---
title: 配置 SAP 适配器的绑定属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecdb5cf06e16c6844addea9e4b7f8fb5f8903bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373875"
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a><span data-ttu-id="ae3d9-102">配置 SAP 适配器的绑定属性</span><span class="sxs-lookup"><span data-stu-id="ae3d9-102">Configure the binding properties for the SAP adapter</span></span>
<span data-ttu-id="ae3d9-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示，您可以控制某些行为特征的多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="ae3d9-104">本部分提供有关从 Visual Studio （设计时） 和设置的绑定属性的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台 （运行时间）。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console (run time).</span></span> <span data-ttu-id="ae3d9-105">在设计时，必须指定要为特定的操作生成架构的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="ae3d9-106">在运行时，必须指定的绑定属性作为一部分发送或接收端口来发送或接收来自 SAP 系统的消息。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-106">At run time, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the SAP system.</span></span>  

 <span data-ttu-id="ae3d9-107">有关绑定属性的信息，其中包括一系列的绑定属性[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

## <a name="enter-binding-properties-at-design-time"></a><span data-ttu-id="ae3d9-108">在设计时输入绑定属性</span><span class="sxs-lookup"><span data-stu-id="ae3d9-108">Enter Binding Properties at Design Time</span></span>  
 <span data-ttu-id="ae3d9-109">对于设计时，你可以指定使用的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-109">For design time, you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="ae3d9-110">输入使用适配器服务外接程序使用的绑定属性</span><span class="sxs-lookup"><span data-stu-id="ae3d9-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="ae3d9-111">右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-111">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="ae3d9-112">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae3d9-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="ae3d9-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ae3d9-113">Use this</span></span>|<span data-ttu-id="ae3d9-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ae3d9-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ae3d9-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="ae3d9-115">**Categories**</span></span>|<span data-ttu-id="ae3d9-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="ae3d9-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="ae3d9-117">**Templates**</span></span>|<span data-ttu-id="ae3d9-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="ae3d9-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="ae3d9-120">在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="ae3d9-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="ae3d9-121">在中**配置适配器**对话框中，单击**绑定属性**选项卡，然后指定不同的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  

6.  <span data-ttu-id="ae3d9-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-122">Click **OK**.</span></span>  

### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ae3d9-123">输入绑定属性使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="ae3d9-123">Enter binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="ae3d9-124">右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="ae3d9-125">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae3d9-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="ae3d9-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ae3d9-126">Use this</span></span>    |           <span data-ttu-id="ae3d9-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ae3d9-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="ae3d9-128">**类别**</span><span class="sxs-lookup"><span data-stu-id="ae3d9-128">**Categories**</span></span> |     <span data-ttu-id="ae3d9-129">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="ae3d9-130">**模板**</span><span class="sxs-lookup"><span data-stu-id="ae3d9-130">**Templates**</span></span>  | <span data-ttu-id="ae3d9-131">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="ae3d9-132">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-132">Click **Add**.</span></span> <span data-ttu-id="ae3d9-133">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="ae3d9-134">在添加适配器向导中，选择**WCF-SAP**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-134">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="ae3d9-135">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="ae3d9-136">如果已配置 BizTalk 中的 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-136">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="ae3d9-137">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-137">Click **Next**.</span></span>  

6. <span data-ttu-id="ae3d9-138">在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="ae3d9-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="ae3d9-139">单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-139">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="ae3d9-140">例如，您必须指定的值**GenerateFlatFileCompatibleIDoc**之前生成用于从 SAP 系统接收 IDOC 的架构属性。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-140">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="ae3d9-141">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-141">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ae3d9-142">如果选择现有的 WCF SAP 发送端口，则不需要指定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-142">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="ae3d9-143">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="ae3d9-144">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="ae3d9-145">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="ae3d9-146">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="ae3d9-147">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-147">Click **OK**.</span></span>  

## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="ae3d9-148">在运行时输入绑定属性</span><span class="sxs-lookup"><span data-stu-id="ae3d9-148">Enter Binding Properties at Run Time</span></span>  
 <span data-ttu-id="ae3d9-149">对于运行时中，你可以指定的绑定属性作为 WCF 自定义端口或中的 WCF SAP 配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-149">For run time, you can specify the binding properties as part of the WCF-Custom port or WCF-SAP configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="ae3d9-150">输入 WCF 自定义端口绑定属性</span><span class="sxs-lookup"><span data-stu-id="ae3d9-150">Enter binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="ae3d9-151">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ae3d9-152">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ae3d9-153">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="ae3d9-154">在中**端口属性**对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ae3d9-155">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-155">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="ae3d9-156">在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-156">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="ae3d9-157">从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-157">From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  

6. <span data-ttu-id="ae3d9-158">在中**配置**框中，指定不同的绑定属性的值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-158">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  

### <a name="enter-binging-properties-for-the-wcf-sap-port"></a><span data-ttu-id="ae3d9-159">输入 WCF SAP 端口绑定属性</span><span class="sxs-lookup"><span data-stu-id="ae3d9-159">Enter binging properties for the WCF-SAP port</span></span>  

1. <span data-ttu-id="ae3d9-160">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-160">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ae3d9-161">添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-161">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ae3d9-162">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-162">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="ae3d9-163">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-163">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ae3d9-164">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-164">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="ae3d9-165">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-165">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ae3d9-166">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-166">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="ae3d9-167">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-167">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ae3d9-168">绑定属性将显示根据配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-168">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="ae3d9-169">例如，绑定属性与入站操作不可用时配置的发送端口，因为的入站的操作需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-169">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  

6. <span data-ttu-id="ae3d9-170">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ae3d9-170">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ae3d9-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae3d9-171">See Also</span></span>  
[<span data-ttu-id="ae3d9-172">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="ae3d9-172">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)