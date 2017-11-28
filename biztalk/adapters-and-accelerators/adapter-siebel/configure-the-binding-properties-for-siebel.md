---
title: "为 Siebel 配置的绑定属性 |Microsoft 文档"
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
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26e9e89319a14317113b730adb189f2f17587f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-siebel"></a><span data-ttu-id="67791-102">为 Siebel 配置的绑定属性</span><span class="sxs-lookup"><span data-stu-id="67791-102">Configure the binding properties for Siebel</span></span>
<span data-ttu-id="67791-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]面，使您能够控制其行为特征一部分的多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="67791-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="67791-104">本部分提供有关从 Visual Studio （设计时） 和设置的绑定属性的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台 （运行时间）。</span><span class="sxs-lookup"><span data-stu-id="67791-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console (run time).</span></span> <span data-ttu-id="67791-105">在设计时，必须指定要生成架构的特定操作的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="67791-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="67791-106">在运行时，必须发送端口将消息发送到 Siebel 系统的一部分指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="67791-106">At run time, you must specify the binding properties as part of the send port for sending messages to the Siebel system.</span></span>  
  
 <span data-ttu-id="67791-107">有关绑定属性的信息，包括一个绑定的属性列表[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="67791-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="enter-the-binding-properties-at-design-time"></a><span data-ttu-id="67791-108">在设计时输入的绑定属性</span><span class="sxs-lookup"><span data-stu-id="67791-108">Enter the binding properties at design time</span></span>  
 <span data-ttu-id="67791-109">为设计时，必须指定的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]对话框。</span><span class="sxs-lookup"><span data-stu-id="67791-109">For design time, you must specify the binding properties from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] dialog box.</span></span>  
  
#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="67791-110">输入使用适配器服务外接程序中使用的绑定属性</span><span class="sxs-lookup"><span data-stu-id="67791-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="67791-111">右键单击你的 BizTalk 项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="67791-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="67791-112">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67791-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="67791-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="67791-113">Use this</span></span>|<span data-ttu-id="67791-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="67791-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="67791-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="67791-115">**Categories**</span></span>|<span data-ttu-id="67791-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="67791-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="67791-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="67791-117">**Templates**</span></span>|<span data-ttu-id="67791-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="67791-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="67791-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="67791-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="67791-120">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="67791-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="67791-121">在**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="67791-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="67791-122">有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="67791-122">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
6.  <span data-ttu-id="67791-123">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="67791-123">Click **OK**.</span></span>  
  
#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="67791-124">输入绑定属性使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="67791-124">Enter binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="67791-125">右键单击你的 BizTalk 项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="67791-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="67791-126">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67791-126">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="67791-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="67791-127">Use this</span></span>|<span data-ttu-id="67791-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="67791-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="67791-129">**类别**</span><span class="sxs-lookup"><span data-stu-id="67791-129">**Categories**</span></span>|<span data-ttu-id="67791-130">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="67791-130">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="67791-131">**模板**</span><span class="sxs-lookup"><span data-stu-id="67791-131">**Templates**</span></span>|<span data-ttu-id="67791-132">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="67791-132">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="67791-133">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="67791-133">Click **Add**.</span></span> <span data-ttu-id="67791-134">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="67791-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="67791-135">在添加适配器向导中，选择**WCF Siebel**。</span><span class="sxs-lookup"><span data-stu-id="67791-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="67791-136">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="67791-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="67791-137">如果你已经在 BizTalk 中配置 WCF Siebel 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="67791-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="67791-138">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="67791-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="67791-139">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="67791-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="67791-140">在**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="67791-140">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="67791-141">有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="67791-141">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67791-142">如果你选择现有 WCF Siebel 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="67791-142">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="67791-143">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="67791-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="67791-144">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="67791-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="67791-145">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="67791-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="67791-146">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="67791-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="67791-147">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="67791-147">Click **OK**.</span></span>  
  
## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="67791-148">在运行时输入绑定属性</span><span class="sxs-lookup"><span data-stu-id="67791-148">Enter binding properties at run time</span></span>  
 <span data-ttu-id="67791-149">对于运行时中，你必须指定绑定属性作为 WCF 自定义或中的 WCF Siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="67791-149">For run time, you must specify the binding properties as part of the WCF-Custom or the WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="67791-150">输入 WCF 自定义端口的绑定属性</span><span class="sxs-lookup"><span data-stu-id="67791-150">Enter binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="67791-151">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="67791-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="67791-152">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**.</span><span class="sxs-lookup"><span data-stu-id="67791-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="67791-153">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="67791-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="67791-154">在**端口属性**对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="67791-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="67791-155">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="67791-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="67791-156">从**绑定类型**下拉列表中，选择**siebelBinding**。</span><span class="sxs-lookup"><span data-stu-id="67791-156">From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  
  
6.  <span data-ttu-id="67791-157">在**配置**框中，指定不同的绑定属性的值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="67791-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  
  
#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a><span data-ttu-id="67791-158">绑定属性为端口输入端口 WCF Siebel</span><span class="sxs-lookup"><span data-stu-id="67791-158">Enter binding properties for the WCF-Siebel port</span></span>  
  
1.  <span data-ttu-id="67791-159">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="67791-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="67791-160">添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="67791-160">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="67791-161">有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="67791-161">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="67791-162">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**.</span><span class="sxs-lookup"><span data-stu-id="67791-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="67791-163">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="67791-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="67791-164">在**端口属性**对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF Siebel 端口，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="67791-164">In the **Port Properties** dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="67791-165">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="67791-165">In the transport properties dialog box, click the **Binding** tab and specify values for the binding properties.</span></span>  
  
6.  <span data-ttu-id="67791-166">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="67791-166">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67791-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67791-167">See Also</span></span>  
[<span data-ttu-id="67791-168">构建基块创建带有 Siebel 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="67791-168">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)