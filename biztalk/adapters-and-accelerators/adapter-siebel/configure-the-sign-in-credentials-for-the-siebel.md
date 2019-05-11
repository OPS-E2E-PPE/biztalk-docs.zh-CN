---
title: 配置用于 Siebel 的登录凭据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865f7fe900d009db7ac79ba933f484cae3fd3e00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371837"
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a><span data-ttu-id="e31e5-102">配置用于 Siebel 的登录凭据</span><span class="sxs-lookup"><span data-stu-id="e31e5-102">Configure the sign in credentials for the Siebel</span></span>
<span data-ttu-id="e31e5-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]要求适配器客户端提供客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="e31e5-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="e31e5-104">适配器使用这些凭据与 Siebel 系统用户进行身份验证并建立连接。</span><span class="sxs-lookup"><span data-stu-id="e31e5-104">The adapter uses these credentials to authenticate the user with the Siebel system and to establish a connection.</span></span>  

 <span data-ttu-id="e31e5-105">适配器客户端可以提供客户端凭据在设计时或运行时。</span><span class="sxs-lookup"><span data-stu-id="e31e5-105">Adapter clients can provide the client credentials either at design time or run time.</span></span> <span data-ttu-id="e31e5-106">在设计时，需要凭据以生成元数据。</span><span class="sxs-lookup"><span data-stu-id="e31e5-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="e31e5-107">在运行时，需要凭据以执行 Siebel 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="e31e5-107">At run time, credentials are required to perform operations on the Siebel system.</span></span> <span data-ttu-id="e31e5-108">本部分提供有关在设计时和运行的时指定客户端凭据的信息。</span><span class="sxs-lookup"><span data-stu-id="e31e5-108">This section provides information about specifying client credentials at design time and run time.</span></span>  

## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="e31e5-109">在设计时输入的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="e31e5-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="e31e5-110">对于设计时，你必须指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e31e5-110">For design time, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="e31e5-111">输入使用适配器服务外接程序使用的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="e31e5-111">Enter client credentials using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="e31e5-112">右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-112">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="e31e5-113">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e31e5-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="e31e5-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e31e5-114">Use this</span></span>|<span data-ttu-id="e31e5-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e31e5-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e31e5-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="e31e5-116">**Categories**</span></span>|<span data-ttu-id="e31e5-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="e31e5-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="e31e5-118">**Templates**</span></span>|<span data-ttu-id="e31e5-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="e31e5-120">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="e31e5-121">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**siebelBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **siebelBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="e31e5-122">在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e31e5-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

6.  <span data-ttu-id="e31e5-123">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e31e5-123">Click **OK**.</span></span>  

#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="e31e5-124">输入客户端凭据使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="e31e5-124">Enter client credentials using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="e31e5-125">右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="e31e5-126">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e31e5-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="e31e5-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e31e5-127">Use this</span></span>    |           <span data-ttu-id="e31e5-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e31e5-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="e31e5-129">**类别**</span><span class="sxs-lookup"><span data-stu-id="e31e5-129">**Categories**</span></span> |     <span data-ttu-id="e31e5-130">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="e31e5-131">**模板**</span><span class="sxs-lookup"><span data-stu-id="e31e5-131">**Templates**</span></span>  | <span data-ttu-id="e31e5-132">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="e31e5-133">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-133">Click **Add**.</span></span> <span data-ttu-id="e31e5-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="e31e5-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="e31e5-135">在添加适配器向导中，选择**Wcf-siebel**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="e31e5-136">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e31e5-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="e31e5-137">如果已配置 BizTalk 中的 WCF Siebel 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="e31e5-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="e31e5-138">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="e31e5-138">Click **Next**.</span></span>  

6. <span data-ttu-id="e31e5-139">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**siebelBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **siebelBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="e31e5-140">在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e31e5-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

8. <span data-ttu-id="e31e5-141">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e31e5-141">Click **OK**.</span></span>  

## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="e31e5-142">在运行时输入客户端凭据</span><span class="sxs-lookup"><span data-stu-id="e31e5-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="e31e5-143">对于运行时中，你必须指定客户端凭据中的 WCF 自定义或 Wcf-siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e31e5-143">For run time, you must specify the client credentials as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

#### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="e31e5-144">WCF 自定义端口输入凭据</span><span class="sxs-lookup"><span data-stu-id="e31e5-144">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="e31e5-145">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e31e5-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="e31e5-146">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**.</span><span class="sxs-lookup"><span data-stu-id="e31e5-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="e31e5-147">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="e31e5-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="e31e5-148">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="e31e5-149">为发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e31e5-149">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="e31e5-150">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e31e5-150">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   -   <span data-ttu-id="e31e5-151">选择**使用单一登录**选项，并指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31e5-151">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

5. <span data-ttu-id="e31e5-152">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e31e5-152">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="e31e5-153">此外支持企业单一登录 (ESSO) 系统。</span><span class="sxs-lookup"><span data-stu-id="e31e5-153">also supports the Enterprise Single Sign-On (ESSO) system.</span></span> <span data-ttu-id="e31e5-154">ESSO 是仅适用于 BizTalk 方案中，WCF 适配器是在其中了解的 ESSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31e5-154">ESSO is only applicable in the BizTalk scenario, in which the WCF adapter is aware of ESSO affiliate applications.</span></span> <span data-ttu-id="e31e5-155">有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Siebel 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e31e5-155">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>

#### <a name="enter-credentials-for-the-wcf-siebel-port"></a><span data-ttu-id="e31e5-156">为 WCF Siebel 端口输入凭据</span><span class="sxs-lookup"><span data-stu-id="e31e5-156">Enter credentials for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="e31e5-157">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e31e5-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="e31e5-158">添加到 WCF 的 Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e31e5-158">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e31e5-159">有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="e31e5-159">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="e31e5-160">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**.</span><span class="sxs-lookup"><span data-stu-id="e31e5-160">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="e31e5-161">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="e31e5-161">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="e31e5-162">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 Wcf-siebel 端口，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e31e5-162">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="e31e5-163">对于发送端口，在传输属性对话框中，单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e31e5-163">For a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="e31e5-164">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e31e5-164">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   -   <span data-ttu-id="e31e5-165">选择**使用单一登录**选项，并指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31e5-165">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

6. <span data-ttu-id="e31e5-166">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e31e5-166">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="e31e5-167">此外支持企业单一登录 (ESSO) 系统。</span><span class="sxs-lookup"><span data-stu-id="e31e5-167">also supports the Enterprise Single Sign-On (ESSO) system.</span></span> <span data-ttu-id="e31e5-168">ESSO 是仅适用于 BizTalk 方案中，WCF 适配器是在其中了解的 ESSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e31e5-168">ESSO is only applicable in the BizTalk scenario, in which the WCF adapter is aware of ESSO affiliate applications.</span></span> <span data-ttu-id="e31e5-169">有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Siebel 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e31e5-169">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e31e5-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="e31e5-170">See Also</span></span>  
[<span data-ttu-id="e31e5-171">若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="e31e5-171">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)