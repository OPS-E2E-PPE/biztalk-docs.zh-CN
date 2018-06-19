---
title: 配置 SAP 系统的凭据登录 |Microsoft 文档
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
ms.openlocfilehash: 2a6ace75f66bb7fdd4cfb3362f7d019ab99d73bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217805"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a><span data-ttu-id="91ccb-102">配置 SAP 系统的凭据登录</span><span class="sxs-lookup"><span data-stu-id="91ccb-102">Configure the sign in credentials for the SAP system</span></span>
<span data-ttu-id="91ccb-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]需要适配器客户端提供客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="91ccb-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="91ccb-104">适配器使用这些凭据进行身份验证与 SAP 系统用户并建立连接。</span><span class="sxs-lookup"><span data-stu-id="91ccb-104">The adapter uses these credentials to authenticate the user with the SAP system and to establish a connection.</span></span>  
  
 <span data-ttu-id="91ccb-105">适配器客户端可以在设计时提供客户端凭据这两个或运行时间。</span><span class="sxs-lookup"><span data-stu-id="91ccb-105">Adapter clients can provide the client credentials both at design time or run time.</span></span> <span data-ttu-id="91ccb-106">在设计时，需要使用凭据才能生成元数据。</span><span class="sxs-lookup"><span data-stu-id="91ccb-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="91ccb-107">在运行时，需要凭据在 SAP 系统上执行操作。</span><span class="sxs-lookup"><span data-stu-id="91ccb-107">At run time, credentials are required to perform operations on the SAP system.</span></span> <span data-ttu-id="91ccb-108">本部分提供有关在设计时和运行的时指定客户端凭据的信息。</span><span class="sxs-lookup"><span data-stu-id="91ccb-108">This section provides information about specifying client credentials at design time and run time.</span></span>  
  
## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="91ccb-109">在设计时输入的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="91ccb-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="91ccb-110">对于设计时，你可以指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="91ccb-110">For design time, you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="91ccb-111">输入使用适配器服务外接程序中使用的凭据</span><span class="sxs-lookup"><span data-stu-id="91ccb-111">Enter credentials using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="91ccb-112">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-112">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="91ccb-113">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="91ccb-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="91ccb-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="91ccb-114">Use this</span></span>|<span data-ttu-id="91ccb-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="91ccb-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="91ccb-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="91ccb-116">**Categories**</span></span>|<span data-ttu-id="91ccb-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="91ccb-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="91ccb-118">**Templates**</span></span>|<span data-ttu-id="91ccb-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="91ccb-120">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="91ccb-121">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="91ccb-122">在**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
6.  <span data-ttu-id="91ccb-123">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-123">Click **OK**.</span></span>  
  
### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="91ccb-124">输入凭据使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="91ccb-124">Enter credentials using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="91ccb-125">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-125">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="91ccb-126">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="91ccb-126">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="91ccb-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="91ccb-127">Use this</span></span>|<span data-ttu-id="91ccb-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="91ccb-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="91ccb-129">**类别**</span><span class="sxs-lookup"><span data-stu-id="91ccb-129">**Categories**</span></span>|<span data-ttu-id="91ccb-130">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-130">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="91ccb-131">**模板**</span><span class="sxs-lookup"><span data-stu-id="91ccb-131">**Templates**</span></span>|<span data-ttu-id="91ccb-132">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-132">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="91ccb-133">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-133">Click **Add**.</span></span> <span data-ttu-id="91ccb-134">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="91ccb-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="91ccb-135">在添加适配器向导中，选择**WCF SAP**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-135">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="91ccb-136">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="91ccb-136">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="91ccb-137">如果你已经在 BizTalk 中配置 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="91ccb-137">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="91ccb-138">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="91ccb-139">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="91ccb-140">在**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
8.  <span data-ttu-id="91ccb-141">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-141">Click **OK**.</span></span>  
  
## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="91ccb-142">在运行时输入客户端凭据</span><span class="sxs-lookup"><span data-stu-id="91ccb-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="91ccb-143">对于运行时中，你可以指定客户端凭据中的 WCF 自定义或 WCF SAP 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="91ccb-143">For run time, you can specify the client credentials as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="91ccb-144">输入 WCF 自定义端口的凭据</span><span class="sxs-lookup"><span data-stu-id="91ccb-144">Enter credentials for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="91ccb-145">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="91ccb-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="91ccb-146">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="91ccb-147">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="91ccb-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="91ccb-148">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91ccb-149">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-149">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="91ccb-150">为发送端口，在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="91ccb-150">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="91ccb-151">选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-151">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="91ccb-152">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="91ccb-152">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="91ccb-153">接收端口，在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="91ccb-153">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="91ccb-154">选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-154">Select **User account** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="91ccb-155">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="91ccb-155">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="91ccb-156">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-156">Click **OK**.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-sap-port"></a><span data-ttu-id="91ccb-157">输入 WCF SAP 端口的凭据</span><span class="sxs-lookup"><span data-stu-id="91ccb-157">Enter credentials for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="91ccb-158">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="91ccb-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="91ccb-159">添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="91ccb-159">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="91ccb-160">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="91ccb-160">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="91ccb-161">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-161">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="91ccb-162">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="91ccb-162">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="91ccb-163">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-163">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91ccb-164">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-164">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="91ccb-165">如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="91ccb-165">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="91ccb-166">选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="91ccb-167">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="91ccb-167">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
6.  <span data-ttu-id="91ccb-168">如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="91ccb-168">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="91ccb-169">选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-169">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="91ccb-170">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="91ccb-170">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
7.  <span data-ttu-id="91ccb-171">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="91ccb-171">Click **OK**.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="91ccb-172">此外支持企业单一登录 (SSO) 系统。</span><span class="sxs-lookup"><span data-stu-id="91ccb-172"> also supports the Enterprise Single Sign-On (SSO) system.</span></span> <span data-ttu-id="91ccb-173">SSO 是仅适用于 BizTalk 方案中，在其中[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]是感知的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="91ccb-173">SSO is only applicable in the BizTalk scenario, in which the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] is aware of SSO affiliate applications.</span></span> <span data-ttu-id="91ccb-174">有关与 BizTalk Server 安全性的详细信息，请参阅[安全性与 SAP 适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="91ccb-174">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91ccb-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91ccb-175">See Also</span></span>  
[<span data-ttu-id="91ccb-176">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="91ccb-176">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)