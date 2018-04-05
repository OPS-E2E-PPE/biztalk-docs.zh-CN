---
title: 配置 Siebel 适配器的连接 URI |Microsoft 文档
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
ms.openlocfilehash: 8017e5ccd2c033f26b03fe7443245d2fb88be960
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a><span data-ttu-id="a18d6-102">配置 Siebel 适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="a18d6-102">Configure the connection URI for the Siebel adapter</span></span>
<span data-ttu-id="a18d6-103">连接 URI 是用于连接到 Siebel 系统的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="a18d6-103">A connection URI is a connection string to connect to a Siebel system.</span></span> <span data-ttu-id="a18d6-104">连接 URI 包含与 Siebel 系统建立连接所需的各种参数。</span><span class="sxs-lookup"><span data-stu-id="a18d6-104">The connection URI contains various parameters required to establish connection with a Siebel system.</span></span> <span data-ttu-id="a18d6-105">必须指定此连接同时在设计时和运行的时的 URI。</span><span class="sxs-lookup"><span data-stu-id="a18d6-105">You must specify this connection URI both at the design time and the run time.</span></span> <span data-ttu-id="a18d6-106">在设计时，必须指定要连接到 Siebel 系统生成的元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="a18d6-106">At design time, you must specify the URI to connect to the Siebel system to generate the metadata.</span></span> <span data-ttu-id="a18d6-107">在运行时，必须指定要连接到 Siebel 系统以执行操作的 URI。</span><span class="sxs-lookup"><span data-stu-id="a18d6-107">At run time, you must specify the URI to connect to the Siebel system to perform operations.</span></span>  
  
## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="a18d6-108">输入在设计时连接 URI</span><span class="sxs-lookup"><span data-stu-id="a18d6-108">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="a18d6-109">为设计时，你必须指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a18d6-109">For design time, you must specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="a18d6-110">输入连接使用适配器服务外接程序中使用的 URI</span><span class="sxs-lookup"><span data-stu-id="a18d6-110">Enter the connection URI using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="a18d6-111">右键单击你的 BizTalk 项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="a18d6-112">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a18d6-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a18d6-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a18d6-113">Use this</span></span>|<span data-ttu-id="a18d6-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a18d6-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a18d6-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="a18d6-115">**Categories**</span></span>|<span data-ttu-id="a18d6-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="a18d6-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="a18d6-117">**Templates**</span></span>|<span data-ttu-id="a18d6-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="a18d6-119">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="a18d6-120">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="a18d6-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a18d6-121">在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a18d6-121">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  
  
6.  <span data-ttu-id="a18d6-122">在**配置适配器**对话框中，单击**URI 属性**选项卡上，并指定了不同参数的值。</span><span class="sxs-lookup"><span data-stu-id="a18d6-122">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="a18d6-123">有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-123">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="a18d6-124">在**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="a18d6-124">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="a18d6-125">有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-125">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
8.  <span data-ttu-id="a18d6-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-126">Click **OK**.</span></span>  
  
#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="a18d6-127">输入连接 URI 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="a18d6-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="a18d6-128">右键单击你的 BizTalk 项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-128">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="a18d6-129">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a18d6-129">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a18d6-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a18d6-130">Use this</span></span>|<span data-ttu-id="a18d6-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a18d6-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a18d6-132">**类别**</span><span class="sxs-lookup"><span data-stu-id="a18d6-132">**Categories**</span></span>|<span data-ttu-id="a18d6-133">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-133">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="a18d6-134">**模板**</span><span class="sxs-lookup"><span data-stu-id="a18d6-134">**Templates**</span></span>|<span data-ttu-id="a18d6-135">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-135">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="a18d6-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-136">Click **Add**.</span></span> <span data-ttu-id="a18d6-137">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="a18d6-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="a18d6-138">在添加适配器向导中，选择**WCF Siebel**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-138">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="a18d6-139">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="a18d6-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a18d6-140">如果你已经在 BizTalk 中配置 WCF Siebel 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="a18d6-140">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="a18d6-141">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-141">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a18d6-142">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="a18d6-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="a18d6-143">在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a18d6-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  
  
8.  <span data-ttu-id="a18d6-144">在**配置适配器**对话框中，单击**URI 属性**选项卡上，并指定了不同参数的值。</span><span class="sxs-lookup"><span data-stu-id="a18d6-144">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="a18d6-145">有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-145">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
9. <span data-ttu-id="a18d6-146">在**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="a18d6-146">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="a18d6-147">有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-147">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a18d6-148">如果你选择现有 WCF Siebel 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="a18d6-148">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="a18d6-149">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="a18d6-149">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="a18d6-150">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="a18d6-150">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="a18d6-151">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="a18d6-151">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="a18d6-152">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="a18d6-152">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
10. <span data-ttu-id="a18d6-153">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-153">Click **OK**.</span></span>  
  
## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="a18d6-154">输入连接 URI 在运行时</span><span class="sxs-lookup"><span data-stu-id="a18d6-154">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="a18d6-155">为运行时中，你必须指定 URI 中的 WCF 自定义或 WCF Siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a18d6-155">For run time, you must specify the URI as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="a18d6-156">输入 WCF 自定义端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="a18d6-156">Enter the connection URI for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="a18d6-157">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a18d6-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a18d6-158">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-158">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="a18d6-159">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="a18d6-159">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="a18d6-160">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-160">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="a18d6-161">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a18d6-161">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="a18d6-162">在**地址 (URI)**文本框中，指定连接 URI 以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a18d6-162">In the **Address (URI)** text box, specify the connection URI to connect to the Siebel system.</span></span> <span data-ttu-id="a18d6-163">有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-163">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
6.  <span data-ttu-id="a18d6-164">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**siebelBinding**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-164">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  
  
7.  <span data-ttu-id="a18d6-165">若要在创建发送端口， **WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a18d6-165">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="a18d6-166">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a18d6-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
    2.  <span data-ttu-id="a18d6-167">选择**使用单一登录**选项，然后指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a18d6-167">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
8.  <span data-ttu-id="a18d6-168">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-168">Click **OK**.</span></span>  
  
#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a><span data-ttu-id="a18d6-169">输入 WCF Siebel 端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="a18d6-169">Enter the connection URI for the WCF-Siebel port</span></span>  
  
1.  <span data-ttu-id="a18d6-170">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a18d6-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a18d6-171">添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a18d6-171">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a18d6-172">有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-172">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="a18d6-173">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="a18d6-174">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="a18d6-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="a18d6-175">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF Siebel 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-175">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a18d6-176">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a18d6-176">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="a18d6-177">单击**配置**按钮，然后提供的连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="a18d6-177">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="a18d6-178">有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="a18d6-178">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="a18d6-179">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="a18d6-179">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
8.  <span data-ttu-id="a18d6-180">若要在创建发送端口， **WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a18d6-180">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="a18d6-181">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a18d6-181">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
    2.  <span data-ttu-id="a18d6-182">选择**使用单一登录**选项，然后指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a18d6-182">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
9. <span data-ttu-id="a18d6-183">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a18d6-183">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18d6-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a18d6-184">See Also</span></span>  
[<span data-ttu-id="a18d6-185">构建基块创建带有 Siebel 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="a18d6-185">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)