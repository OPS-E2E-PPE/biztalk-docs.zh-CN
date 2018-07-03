---
title: 用于 Oracle E-business Suite 中配置的绑定属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1e2d60ede3e41c08b15d3839f6ece41a68aa373
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989174"
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a><span data-ttu-id="954a3-102">用于 Oracle E-business Suite 中配置的绑定属性</span><span class="sxs-lookup"><span data-stu-id="954a3-102">Configure the binding properties for Oracle E-Business Suite</span></span>
<span data-ttu-id="954a3-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示，您可以控制某些行为特征的多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="954a3-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="954a3-104">本部分提供有关设置中的绑定属性的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="954a3-104">This section provides information about setting the binding properties from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="954a3-105">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，生成对特定操作的架构时，必须指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="954a3-105">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="954a3-106">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须指定的绑定属性作为一部分发送或接收端口来发送或接收来自 Oracle E-business Suite 的消息。</span><span class="sxs-lookup"><span data-stu-id="954a3-106">From [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must specify the binding properties as part of the send or receive port for sending or receiving messages from Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="954a3-107">有关绑定属性的信息，其中包括一系列的绑定属性[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="954a3-107">For information about the binding properties, including a list of binding properties for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  

## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="954a3-108">指定从 Visual Studio 绑定属性</span><span class="sxs-lookup"><span data-stu-id="954a3-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="954a3-109">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定使用的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="954a3-109">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="954a3-110">若要指定使用适配器服务外接程序使用的绑定属性</span><span class="sxs-lookup"><span data-stu-id="954a3-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="954a3-111">右键单击 BizTalk 项目中，然后依次**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="954a3-111">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="954a3-112">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="954a3-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="954a3-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="954a3-113">Use this</span></span>|<span data-ttu-id="954a3-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="954a3-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="954a3-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="954a3-115">**Categories**</span></span>|<span data-ttu-id="954a3-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="954a3-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="954a3-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="954a3-117">**Templates**</span></span>|<span data-ttu-id="954a3-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="954a3-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="954a3-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="954a3-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="954a3-120">在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**oracleEBSBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="954a3-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **oracleEBSBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="954a3-121">在中**配置适配器**对话框中，单击**绑定属性**选项卡，然后指定不同的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="954a3-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  

6.  <span data-ttu-id="954a3-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="954a3-122">Click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="954a3-123">若要指定绑定属性使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="954a3-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="954a3-124">右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="954a3-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="954a3-125">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="954a3-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="954a3-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="954a3-126">Use this</span></span>    |           <span data-ttu-id="954a3-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="954a3-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="954a3-128">**类别**</span><span class="sxs-lookup"><span data-stu-id="954a3-128">**Categories**</span></span> |     <span data-ttu-id="954a3-129">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="954a3-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="954a3-130">**模板**</span><span class="sxs-lookup"><span data-stu-id="954a3-130">**Templates**</span></span>  | <span data-ttu-id="954a3-131">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="954a3-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="954a3-132">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="954a3-132">Click **Add**.</span></span> <span data-ttu-id="954a3-133">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="954a3-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="954a3-134">在中[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**Wcf-oracleebs**。</span><span class="sxs-lookup"><span data-stu-id="954a3-134">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleEBS**.</span></span> <span data-ttu-id="954a3-135">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="954a3-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="954a3-136">如果已配置 BizTalk 中的 WCF OracleEBS 端口，请从端口列表中选择的端口。</span><span class="sxs-lookup"><span data-stu-id="954a3-136">If you already have a WCF-OracleEBS port configured in BizTalk, select the port from the Port list.</span></span>  

5. <span data-ttu-id="954a3-137">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="954a3-137">Click **Next**.</span></span>  

6. <span data-ttu-id="954a3-138">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="954a3-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleEBSBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="954a3-139">单击**绑定属性**选项卡，并指定的绑定值，如果有，生成架构之前所需的。</span><span class="sxs-lookup"><span data-stu-id="954a3-139">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="954a3-140">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="954a3-140">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="954a3-141">如果您选择的现有 WCF OracleEBS 发送端口，则需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="954a3-141">If you selected an existing WCF-OracleEBS send port, you need not specify the binding properties.</span></span> <span data-ttu-id="954a3-142">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="954a3-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="954a3-143">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="954a3-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="954a3-144">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="954a3-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="954a3-145">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="954a3-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="954a3-146">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="954a3-146">Click **OK**.</span></span>  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="954a3-147">指定 BizTalk Server 管理控制台中的绑定属性</span><span class="sxs-lookup"><span data-stu-id="954a3-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="954a3-148">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，必须为 WCF 自定义或 WCF OracleEBS 端口配置的一部分指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="954a3-148">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="954a3-149">若要指定的 WCF 自定义端口绑定属性</span><span class="sxs-lookup"><span data-stu-id="954a3-149">To specify binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="954a3-150">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="954a3-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="954a3-151">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="954a3-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="954a3-152">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="954a3-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="954a3-153">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="954a3-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="954a3-154">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="954a3-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="954a3-155">在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="954a3-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="954a3-156">从**绑定类型**列表中，选择**oracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="954a3-156">From the **Binding Type** list, select **oracleEBSBinding**.</span></span>  

6. <span data-ttu-id="954a3-157">在中**配置**框中，指定不同的绑定属性的值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="954a3-157">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a><span data-ttu-id="954a3-158">若要指定的 WCF OracleEBS 端口绑定属性</span><span class="sxs-lookup"><span data-stu-id="954a3-158">To specify binding properties for the WCF-OracleEBS port</span></span>  

1. <span data-ttu-id="954a3-159">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="954a3-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="954a3-160">添加 WCF OracleEBS 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="954a3-160">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="954a3-161">有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="954a3-161">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="954a3-162">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="954a3-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="954a3-163">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="954a3-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="954a3-164">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 Wcf-oracleebs 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="954a3-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="954a3-165">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="954a3-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="954a3-166">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="954a3-166">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="954a3-167">绑定属性将显示根据配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="954a3-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="954a3-168">例如，与通知相关的绑定属性不可用时配置的发送端口，因为通知的入站的操作并且需要进行接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="954a3-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="954a3-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="954a3-169">See Also</span></span>  
 [<span data-ttu-id="954a3-170">若要创建 Oracle E-business Suite 的应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="954a3-170">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)