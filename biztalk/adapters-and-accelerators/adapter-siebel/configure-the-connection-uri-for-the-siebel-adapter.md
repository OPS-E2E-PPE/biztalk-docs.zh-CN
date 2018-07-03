---
title: 配置 Siebel 适配器的连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying
ms.assetid: b89b60e9-0f3b-4305-865e-9d3b40d04648
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070925b09cf4e4896097be1aa88bc57fcd625626
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992390"
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a><span data-ttu-id="fabee-102">配置 Siebel 适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="fabee-102">Configure the connection URI for the Siebel adapter</span></span>
<span data-ttu-id="fabee-103">一个连接 URI 是一个连接字符串以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="fabee-103">A connection URI is a connection string to connect to a Siebel system.</span></span> <span data-ttu-id="fabee-104">连接 URI 包含建立与 Siebel 系统的连接所需的各种参数。</span><span class="sxs-lookup"><span data-stu-id="fabee-104">The connection URI contains various parameters required to establish connection with a Siebel system.</span></span> <span data-ttu-id="fabee-105">必须指定此连接在设计时和运行的时的 URI。</span><span class="sxs-lookup"><span data-stu-id="fabee-105">You must specify this connection URI both at the design time and the run time.</span></span> <span data-ttu-id="fabee-106">在设计时，必须指定要连接到 Siebel 系统生成的元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="fabee-106">At design time, you must specify the URI to connect to the Siebel system to generate the metadata.</span></span> <span data-ttu-id="fabee-107">在运行时，必须指定要连接到 Siebel 系统以执行操作的 URI。</span><span class="sxs-lookup"><span data-stu-id="fabee-107">At run time, you must specify the URI to connect to the Siebel system to perform operations.</span></span>  

## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="fabee-108">输入连接 URI 在设计时</span><span class="sxs-lookup"><span data-stu-id="fabee-108">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="fabee-109">对于设计时，你必须指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fabee-109">For design time, you must specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="fabee-110">输入连接 URI 使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="fabee-110">Enter the connection URI using Consume Adapter Service Add-in</span></span>  

1. <span data-ttu-id="fabee-111">右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="fabee-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="fabee-112">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fabee-112">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="fabee-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fabee-113">Use this</span></span>    |             <span data-ttu-id="fabee-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fabee-114">To do this</span></span>             |
   |----------------|------------------------------------|
   | <span data-ttu-id="fabee-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="fabee-115">**Categories**</span></span> | <span data-ttu-id="fabee-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="fabee-116">Click **Consume Adapter Service**.</span></span> |
   | <span data-ttu-id="fabee-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="fabee-117">**Templates**</span></span>  | <span data-ttu-id="fabee-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="fabee-118">Click **Consume Adapter Service**.</span></span> |


3. <span data-ttu-id="fabee-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="fabee-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4. <span data-ttu-id="fabee-120">在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="fabee-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

5. <span data-ttu-id="fabee-121">在中**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="fabee-121">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

6. <span data-ttu-id="fabee-122">在中**配置适配器**对话框中，单击**URI 属性**选项卡上，并指定不同的参数的值。</span><span class="sxs-lookup"><span data-stu-id="fabee-122">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="fabee-123">有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-123">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

7. <span data-ttu-id="fabee-124">在中**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="fabee-124">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="fabee-125">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-125">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

8. <span data-ttu-id="fabee-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fabee-126">Click **OK**.</span></span>  

#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="fabee-127">输入连接 URI 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="fabee-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="fabee-128">右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="fabee-128">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="fabee-129">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fabee-129">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="fabee-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fabee-130">Use this</span></span>    |           <span data-ttu-id="fabee-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fabee-131">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="fabee-132">**类别**</span><span class="sxs-lookup"><span data-stu-id="fabee-132">**Categories**</span></span> |     <span data-ttu-id="fabee-133">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="fabee-133">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="fabee-134">**模板**</span><span class="sxs-lookup"><span data-stu-id="fabee-134">**Templates**</span></span>  | <span data-ttu-id="fabee-135">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="fabee-135">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="fabee-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="fabee-136">Click **Add**.</span></span> <span data-ttu-id="fabee-137">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="fabee-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="fabee-138">在添加适配器向导中，选择**Wcf-siebel**。</span><span class="sxs-lookup"><span data-stu-id="fabee-138">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="fabee-139">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="fabee-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="fabee-140">如果已配置 BizTalk 中的 WCF Siebel 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="fabee-140">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="fabee-141">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="fabee-141">Click **Next**.</span></span>  

6. <span data-ttu-id="fabee-142">在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="fabee-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="fabee-143">在中**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="fabee-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

8. <span data-ttu-id="fabee-144">在中**配置适配器**对话框中，单击**URI 属性**选项卡上，并指定不同的参数的值。</span><span class="sxs-lookup"><span data-stu-id="fabee-144">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="fabee-145">有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-145">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

9. <span data-ttu-id="fabee-146">在中**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="fabee-146">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="fabee-147">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-147">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fabee-148">如果选择现有的 WCF Siebel 发送端口，则不需要指定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="fabee-148">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="fabee-149">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="fabee-149">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="fabee-150">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="fabee-150">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="fabee-151">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="fabee-151">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="fabee-152">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="fabee-152">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

10. <span data-ttu-id="fabee-153">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fabee-153">Click **OK**.</span></span>  

## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="fabee-154">输入连接 URI 在运行时</span><span class="sxs-lookup"><span data-stu-id="fabee-154">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="fabee-155">对于运行时中，你必须指定 URI 中的 WCF 自定义或 Wcf-siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fabee-155">For run time, you must specify the URI as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="fabee-156">输入 WCF 自定义端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="fabee-156">Enter the connection URI for the WCF-Custom port</span></span>  

1. <span data-ttu-id="fabee-157">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fabee-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="fabee-158">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fabee-158">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="fabee-159">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="fabee-159">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="fabee-160">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fabee-160">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="fabee-161">在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fabee-161">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  

5. <span data-ttu-id="fabee-162">在中**地址 (URI)** 文本框中，指定连接到 Siebel 系统连接 URI。</span><span class="sxs-lookup"><span data-stu-id="fabee-162">In the **Address (URI)** text box, specify the connection URI to connect to the Siebel system.</span></span> <span data-ttu-id="fabee-163">有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-163">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

6. <span data-ttu-id="fabee-164">在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**siebelBinding**。</span><span class="sxs-lookup"><span data-stu-id="fabee-164">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  

7. <span data-ttu-id="fabee-165">若要创建的发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fabee-165">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="fabee-166">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="fabee-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   2.  <span data-ttu-id="fabee-167">选择**使用单一登录**选项，并指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fabee-167">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

8. <span data-ttu-id="fabee-168">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fabee-168">Click **OK**.</span></span>  

#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a><span data-ttu-id="fabee-169">输入 WCF Siebel 端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="fabee-169">Enter the connection URI for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="fabee-170">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fabee-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="fabee-171">添加到 WCF 的 Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fabee-171">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="fabee-172">有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-172">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="fabee-173">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fabee-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="fabee-174">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="fabee-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="fabee-175">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 Wcf-siebel 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fabee-175">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="fabee-176">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fabee-176">In the transport properties dialog box, click the **General** tab.</span></span>  

6. <span data-ttu-id="fabee-177">单击**配置**按钮，并提供连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="fabee-177">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="fabee-178">有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="fabee-178">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

7. <span data-ttu-id="fabee-179">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="fabee-179">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

8. <span data-ttu-id="fabee-180">若要创建的发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fabee-180">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="fabee-181">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="fabee-181">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   2.  <span data-ttu-id="fabee-182">选择**使用单一登录**选项，并指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fabee-182">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

9. <span data-ttu-id="fabee-183">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fabee-183">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fabee-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="fabee-184">See Also</span></span>  
[<span data-ttu-id="fabee-185">若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="fabee-185">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)