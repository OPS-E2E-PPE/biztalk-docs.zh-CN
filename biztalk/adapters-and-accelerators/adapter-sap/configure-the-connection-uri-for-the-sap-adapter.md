---
title: "配置 SAP 适配器的连接 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at run time
- connection URI, specifying at design time
ms.assetid: 8df8e4a7-13f7-48c0-8af2-451253ced7e7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b614f3a300dbda213cd45ba7eaf9215802bc48c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-the-sap-adapter"></a><span data-ttu-id="f817f-102">配置 SAP 适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="f817f-102">Configure the connection URI for the SAP adapter</span></span>
<span data-ttu-id="f817f-103">连接 URI 是用于连接到 SAP 系统的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f817f-103">A connection URI is a connection string to connect to an SAP system.</span></span> <span data-ttu-id="f817f-104">它包含与某个 SAP 系统建立连接所需的各种参数。</span><span class="sxs-lookup"><span data-stu-id="f817f-104">It contains various parameters required to establish connection with an SAP system.</span></span> <span data-ttu-id="f817f-105">在设计时，必须指定要连接到 SAP 系统生成的元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="f817f-105">At design time, you must specify the URI to connect to the SAP system to generate the metadata.</span></span> <span data-ttu-id="f817f-106">在运行时，必须指定要连接到 SAP 系统以执行操作的 URI。</span><span class="sxs-lookup"><span data-stu-id="f817f-106">At run time, you must specify the URI to connect to the SAP system to perform operations.</span></span>  
  
## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="f817f-107">输入在设计时连接 URI</span><span class="sxs-lookup"><span data-stu-id="f817f-107">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="f817f-108">对于设计时，你可以指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f817f-108">For design time, you can specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="f817f-109">输入连接使用适配器服务外接程序中使用的 URI</span><span class="sxs-lookup"><span data-stu-id="f817f-109">Enter the connection URI using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="f817f-110">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="f817f-110">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="f817f-111">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f817f-111">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f817f-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f817f-112">Use this</span></span>|<span data-ttu-id="f817f-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f817f-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f817f-114">**类别**</span><span class="sxs-lookup"><span data-stu-id="f817f-114">**Categories**</span></span>|<span data-ttu-id="f817f-115">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="f817f-115">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="f817f-116">**模板**</span><span class="sxs-lookup"><span data-stu-id="f817f-116">**Templates**</span></span>|<span data-ttu-id="f817f-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="f817f-117">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="f817f-118">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f817f-118">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="f817f-119">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="f817f-119">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="f817f-120">在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-120">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list boxes, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
6.  <span data-ttu-id="f817f-121">单击**URI 属性**选项卡上，并指定了不同参数的值。</span><span class="sxs-lookup"><span data-stu-id="f817f-121">Click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="f817f-122">有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-122">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="f817f-123">单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="f817f-123">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="f817f-124">例如，你必须指定的值**GenerateFlatFileCompatibleIDoc**之前用于从 SAP 系统接收 IDOC 生成架构的属性。</span><span class="sxs-lookup"><span data-stu-id="f817f-124">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="f817f-125">有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-125">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
8.  <span data-ttu-id="f817f-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f817f-126">Click **OK**.</span></span>  
  
### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="f817f-127">输入连接 URI 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="f817f-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="f817f-128">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="f817f-128">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="f817f-129">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f817f-129">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f817f-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f817f-130">Use this</span></span>|<span data-ttu-id="f817f-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f817f-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f817f-132">**类别**</span><span class="sxs-lookup"><span data-stu-id="f817f-132">**Categories**</span></span>|<span data-ttu-id="f817f-133">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="f817f-133">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="f817f-134">**模板**</span><span class="sxs-lookup"><span data-stu-id="f817f-134">**Templates**</span></span>|<span data-ttu-id="f817f-135">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="f817f-135">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="f817f-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="f817f-136">Click **Add**.</span></span> <span data-ttu-id="f817f-137">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="f817f-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="f817f-138">在添加适配器向导中，选择**WCF SAP**。</span><span class="sxs-lookup"><span data-stu-id="f817f-138">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="f817f-139">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f817f-139">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f817f-140">如果你已经在 BizTalk 中配置 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="f817f-140">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="f817f-141">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="f817f-141">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f817f-142">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="f817f-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="f817f-143">在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list boxes, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
8.  <span data-ttu-id="f817f-144">单击**URI 属性**选项卡上，并指定了不同参数的值。</span><span class="sxs-lookup"><span data-stu-id="f817f-144">Click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="f817f-145">有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-145">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
9. <span data-ttu-id="f817f-146">单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。</span><span class="sxs-lookup"><span data-stu-id="f817f-146">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="f817f-147">例如，你必须指定的值**GenerateFlatFileCompatibleIDoc**之前用于从 SAP 系统接收 IDOC 生成架构的属性。</span><span class="sxs-lookup"><span data-stu-id="f817f-147">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="f817f-148">有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-148">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f817f-149">如果你选择现有 WCF SAP 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="f817f-149">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="f817f-150">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="f817f-150">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="f817f-151">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="f817f-151">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="f817f-152">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="f817f-152">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="f817f-153">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="f817f-153">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
10. <span data-ttu-id="f817f-154">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f817f-154">Click **OK**.</span></span>  
  
## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="f817f-155">输入连接 URI 在运行时</span><span class="sxs-lookup"><span data-stu-id="f817f-155">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="f817f-156">对于运行时中，你可以指定 URI 中的 WCF 自定义或 WCF SAP 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f817f-156">For run time, you can specify the URI as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="f817f-157">输入 WCF 自定义端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="f817f-157">Enter the connection URI for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="f817f-158">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f817f-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f817f-159">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="f817f-159">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="f817f-160">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="f817f-160">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="f817f-161">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f817f-161">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f817f-162">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="f817f-162">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="f817f-163">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f817f-163">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="f817f-164">在**地址 (URI)**文本框中，指定连接 URI 以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-164">In the **Address (URI)** text box, specify the connection URI to connect to the SAP system.</span></span> <span data-ttu-id="f817f-165">有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-165">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
6.  <span data-ttu-id="f817f-166">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="f817f-166">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
7.  <span data-ttu-id="f817f-167">如果您创建发送端口，则在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f817f-167">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="f817f-168">选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-168">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="f817f-169">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f817f-169">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
8.  <span data-ttu-id="f817f-170">如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f817f-170">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="f817f-171">选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-171">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="f817f-172">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f817f-172">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
9. <span data-ttu-id="f817f-173">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f817f-173">Click **OK**.</span></span>  
  
### <a name="enter-the-connection-uri-for-the-wcf-sap-port"></a><span data-ttu-id="f817f-174">输入 WCF SAP 端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="f817f-174">Enter the connection URI for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="f817f-175">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f817f-175">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f817f-176">添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f817f-176">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f817f-177">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-177">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="f817f-178">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="f817f-178">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="f817f-179">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="f817f-179">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="f817f-180">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f817f-180">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f817f-181">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="f817f-181">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="f817f-182">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f817f-182">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="f817f-183">单击**配置**按钮，然后提供的连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="f817f-183">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="f817f-184">有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f817f-184">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="f817f-185">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="f817f-185">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f817f-186">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="f817f-186">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="f817f-187">例如，绑定属性相关的入站操作不可用时配置发送端口，因为入站的操作需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="f817f-187">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
8.  <span data-ttu-id="f817f-188">如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f817f-188">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="f817f-189">选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-189">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="f817f-190">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f817f-190">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
9. <span data-ttu-id="f817f-191">如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f817f-191">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="f817f-192">选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="f817f-192">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="f817f-193">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f817f-193">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
10. <span data-ttu-id="f817f-194">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f817f-194">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f817f-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f817f-195">See Also</span></span>  
[<span data-ttu-id="f817f-196">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="f817f-196">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)