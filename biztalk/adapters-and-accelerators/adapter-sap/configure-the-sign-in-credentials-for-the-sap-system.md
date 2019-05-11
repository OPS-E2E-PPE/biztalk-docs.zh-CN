---
title: 配置 SAP 系统的凭据登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b99e0dbce9bc4adca6cfebd50b7aeda023b64a17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373677"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a><span data-ttu-id="4423d-102">配置 SAP 系统的凭据登录</span><span class="sxs-lookup"><span data-stu-id="4423d-102">Configure the sign in credentials for the SAP system</span></span>
<span data-ttu-id="4423d-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求适配器客户端提供客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="4423d-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="4423d-104">SAP 系统与用户进行身份验证和建立连接，适配器将使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="4423d-104">The adapter uses these credentials to authenticate the user with the SAP system and to establish a connection.</span></span>  

 <span data-ttu-id="4423d-105">适配器客户端可以在设计时提供客户端凭据这两个或运行时。</span><span class="sxs-lookup"><span data-stu-id="4423d-105">Adapter clients can provide the client credentials both at design time or run time.</span></span> <span data-ttu-id="4423d-106">在设计时，需要凭据以生成元数据。</span><span class="sxs-lookup"><span data-stu-id="4423d-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="4423d-107">在运行时，需要凭据来执行 SAP 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="4423d-107">At run time, credentials are required to perform operations on the SAP system.</span></span> <span data-ttu-id="4423d-108">本部分提供有关在设计时和运行的时指定客户端凭据的信息。</span><span class="sxs-lookup"><span data-stu-id="4423d-108">This section provides information about specifying client credentials at design time and run time.</span></span>  

## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="4423d-109">在设计时输入的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="4423d-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="4423d-110">对于设计时，你可以指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4423d-110">For design time, you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="enter-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="4423d-111">输入使用适配器服务外接程序使用的凭据</span><span class="sxs-lookup"><span data-stu-id="4423d-111">Enter credentials using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="4423d-112">右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="4423d-112">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="4423d-113">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4423d-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="4423d-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4423d-114">Use this</span></span>|<span data-ttu-id="4423d-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4423d-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4423d-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="4423d-116">**Categories**</span></span>|<span data-ttu-id="4423d-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="4423d-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="4423d-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="4423d-118">**Templates**</span></span>|<span data-ttu-id="4423d-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="4423d-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="4423d-120">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="4423d-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="4423d-121">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="4423d-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="4423d-122">在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

6.  <span data-ttu-id="4423d-123">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4423d-123">Click **OK**.</span></span>  

### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="4423d-124">输入凭据使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="4423d-124">Enter credentials using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="4423d-125">右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="4423d-125">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="4423d-126">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4423d-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="4423d-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4423d-127">Use this</span></span>    |           <span data-ttu-id="4423d-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4423d-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="4423d-129">**类别**</span><span class="sxs-lookup"><span data-stu-id="4423d-129">**Categories**</span></span> |     <span data-ttu-id="4423d-130">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="4423d-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="4423d-131">**模板**</span><span class="sxs-lookup"><span data-stu-id="4423d-131">**Templates**</span></span>  | <span data-ttu-id="4423d-132">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="4423d-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="4423d-133">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="4423d-133">Click **Add**.</span></span> <span data-ttu-id="4423d-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="4423d-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="4423d-135">在添加适配器向导中，选择**WCF-SAP**。</span><span class="sxs-lookup"><span data-stu-id="4423d-135">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="4423d-136">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4423d-136">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="4423d-137">如果已配置 BizTalk 中的 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="4423d-137">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="4423d-138">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="4423d-138">Click **Next**.</span></span>  

6. <span data-ttu-id="4423d-139">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="4423d-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="4423d-140">在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

8. <span data-ttu-id="4423d-141">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4423d-141">Click **OK**.</span></span>  

## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="4423d-142">在运行时输入客户端凭据</span><span class="sxs-lookup"><span data-stu-id="4423d-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="4423d-143">对于运行时中，你可以指定客户端凭据中的 WCF 自定义或 WCF SAP 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4423d-143">For run time, you can specify the client credentials as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="4423d-144">WCF 自定义端口输入凭据</span><span class="sxs-lookup"><span data-stu-id="4423d-144">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="4423d-145">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4423d-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="4423d-146">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="4423d-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="4423d-147">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="4423d-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="4423d-148">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="4423d-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4423d-149">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="4423d-149">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="4423d-150">为发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423d-150">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="4423d-151">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-151">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  

   -   <span data-ttu-id="4423d-152">选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4423d-152">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

5. <span data-ttu-id="4423d-153">为接收端口，在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423d-153">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="4423d-154">选择**用户帐户**选项，然后指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-154">Select **User account** option, and specify the user name and password to connect to an SAP system.</span></span>  

   -   <span data-ttu-id="4423d-155">选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="4423d-155">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  

6. <span data-ttu-id="4423d-156">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4423d-156">Click **OK**.</span></span>  

### <a name="enter-credentials-for-the-wcf-sap-port"></a><span data-ttu-id="4423d-157">为 WCF SAP 端口输入凭据</span><span class="sxs-lookup"><span data-stu-id="4423d-157">Enter credentials for the WCF-SAP port</span></span>  

1. <span data-ttu-id="4423d-158">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4423d-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="4423d-159">添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4423d-159">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="4423d-160">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="4423d-160">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="4423d-161">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="4423d-161">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="4423d-162">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="4423d-162">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="4423d-163">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="4423d-163">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4423d-164">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="4423d-164">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="4423d-165">如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423d-165">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="4423d-166">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="4423d-167">选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4423d-167">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

6. <span data-ttu-id="4423d-168">如果要创建接收端口，请在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423d-168">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="4423d-169">选择**用户帐户**选项，然后指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-169">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="4423d-170">选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4423d-170">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

7. <span data-ttu-id="4423d-171">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4423d-171">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="4423d-172">此外支持企业单一登录 (SSO) 系统。</span><span class="sxs-lookup"><span data-stu-id="4423d-172">also supports the Enterprise Single Sign-On (SSO) system.</span></span> <span data-ttu-id="4423d-173">SSO 选项仅适用于 BizTalk 方案中，在其中[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]可识别的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="4423d-173">SSO is only applicable in the BizTalk scenario, in which the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] is aware of SSO affiliate applications.</span></span> <span data-ttu-id="4423d-174">有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4423d-174">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4423d-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="4423d-175">See Also</span></span>  
[<span data-ttu-id="4423d-176">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="4423d-176">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)