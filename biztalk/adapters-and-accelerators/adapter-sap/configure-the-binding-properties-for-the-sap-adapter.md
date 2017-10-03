---
title: "配置 SAP 适配器的绑定属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a16a95818ed4d63fd97b9fca1f9ea86ebd14de80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a><span data-ttu-id="0ddb7-102">配置 SAP 适配器的绑定属性</span><span class="sxs-lookup"><span data-stu-id="0ddb7-102">Configure the binding properties for the SAP adapter</span></span>
<span data-ttu-id="0ddb7-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]面，使您能够控制其行为特征一部分的多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="0ddb7-104">本部分提供有关从 Visual Studio （设计时） 和设置的绑定属性的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台 （运行时间）。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console (run time).</span></span> <span data-ttu-id="0ddb7-105">在设计时，必须指定要生成架构的特定操作的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="0ddb7-106">在运行时，必须发送的一部分指定的绑定属性，或接收端口来发送或接收来自 SAP 系统的消息。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-106">At run time, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the SAP system.</span></span>  
  
 <span data-ttu-id="0ddb7-107">有关绑定属性的信息，包括一个绑定的属性列表[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
## <a name="enter-binding-properties-at-design-time"></a><span data-ttu-id="0ddb7-108">在设计时输入绑定属性</span><span class="sxs-lookup"><span data-stu-id="0ddb7-108">Enter Binding Properties at Design Time</span></span>  
 <span data-ttu-id="0ddb7-109">对于设计时，你可以指定使用的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-109">For design time, you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="0ddb7-110">输入使用适配器服务外接程序中使用的绑定属性</span><span class="sxs-lookup"><span data-stu-id="0ddb7-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="0ddb7-111">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-111">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="0ddb7-112">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ddb7-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="0ddb7-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0ddb7-113">Use this</span></span>|<span data-ttu-id="0ddb7-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0ddb7-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0ddb7-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="0ddb7-115">**Categories**</span></span>|<span data-ttu-id="0ddb7-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="0ddb7-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="0ddb7-117">**Templates**</span></span>|<span data-ttu-id="0ddb7-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="0ddb7-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="0ddb7-120">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0ddb7-121">在**配置适配器**对话框中，单击**绑定属性**选项卡上，然后指定不同的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  
  
6.  <span data-ttu-id="0ddb7-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-122">Click **OK**.</span></span>  
  
### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="0ddb7-123">输入绑定属性使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="0ddb7-123">Enter binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="0ddb7-124">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="0ddb7-125">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ddb7-125">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="0ddb7-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0ddb7-126">Use this</span></span>|<span data-ttu-id="0ddb7-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0ddb7-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0ddb7-128">**类别**</span><span class="sxs-lookup"><span data-stu-id="0ddb7-128">**Categories**</span></span>|<span data-ttu-id="0ddb7-129">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-129">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="0ddb7-130">**模板**</span><span class="sxs-lookup"><span data-stu-id="0ddb7-130">**Templates**</span></span>|<span data-ttu-id="0ddb7-131">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-131">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="0ddb7-132">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-132">Click **Add**.</span></span> <span data-ttu-id="0ddb7-133">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="0ddb7-134">在添加适配器向导中，选择**WCF SAP**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-134">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="0ddb7-135">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0ddb7-136">如果你已经在 BizTalk 中配置 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-136">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="0ddb7-137">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="0ddb7-138">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="0ddb7-139">单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-139">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="0ddb7-140">例如，你必须指定的值**GenerateFlatFileCompatibleIDoc**之前用于从 SAP 系统接收 IDOC 生成架构的属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-140">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="0ddb7-141">有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-141">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ddb7-142">如果你选择现有 WCF SAP 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-142">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="0ddb7-143">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="0ddb7-144">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="0ddb7-145">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="0ddb7-146">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="0ddb7-147">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-147">Click **OK**.</span></span>  
  
## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="0ddb7-148">在运行时输入绑定属性</span><span class="sxs-lookup"><span data-stu-id="0ddb7-148">Enter Binding Properties at Run Time</span></span>  
 <span data-ttu-id="0ddb7-149">对于运行时中，你可以指定的绑定属性作为 WCF 自定义端口或中的 WCF SAP 配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-149">For run time, you can specify the binding properties as part of the WCF-Custom port or WCF-SAP configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="0ddb7-150">输入 WCF 自定义端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="0ddb7-150">Enter binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="0ddb7-151">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0ddb7-152">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="0ddb7-153">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="0ddb7-154">在**端口属性**对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ddb7-155">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-155">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="0ddb7-156">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-156">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="0ddb7-157">从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-157">From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
6.  <span data-ttu-id="0ddb7-158">在**配置**框中，为不同的绑定属性中，指定值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-158">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  
  
### <a name="enter-binging-properties-for-the-wcf-sap-port"></a><span data-ttu-id="0ddb7-159">输入 WCF SAP 端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="0ddb7-159">Enter binging properties for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="0ddb7-160">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-160">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0ddb7-161">添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-161">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0ddb7-162">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-162">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="0ddb7-163">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-163">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="0ddb7-164">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-164">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="0ddb7-165">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-165">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ddb7-166">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-166">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="0ddb7-167">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-167">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ddb7-168">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-168">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="0ddb7-169">例如，绑定属性相关的入站操作不可用时配置发送端口，因为入站的操作需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-169">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
6.  <span data-ttu-id="0ddb7-170">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0ddb7-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddb7-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ddb7-171">See Also</span></span>  
[<span data-ttu-id="0ddb7-172">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="0ddb7-172">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)