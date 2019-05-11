---
title: 步骤 5：配置贸易合作伙伴网页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149e4a2ad60cc082890b0beb8a5517142e4a27c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244392"
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a><span data-ttu-id="214e9-102">步骤 5：配置贸易合作伙伴网页</span><span class="sxs-lookup"><span data-stu-id="214e9-102">Step 5: Configure the Trading Partner Web Pages</span></span>
<span data-ttu-id="214e9-103">![步骤 5 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")</span><span class="sxs-lookup"><span data-stu-id="214e9-103">![Step 5 of 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")</span></span>  
  
 <span data-ttu-id="214e9-104">在此步骤中，您可以执行以下任务设置贸易伙伴网页：</span><span class="sxs-lookup"><span data-stu-id="214e9-104">In this step, you perform the following tasks to set up trading partner Web pages:</span></span>  
  
-   <span data-ttu-id="214e9-105">启用 HTTP 传输所需的 BTS HTTP Receive ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="214e9-105">Enable the BTS HTTP Receive ISAPI filter that is required for HTTP transport.</span></span>  
  
-   <span data-ttu-id="214e9-106">设置文件夹和一个 aspx 页以将 997 确认路由到合作伙伴组织 Fabrikam 使用 HTTP 传输。</span><span class="sxs-lookup"><span data-stu-id="214e9-106">Set up a folder and an aspx page to route the 997 acknowledgment to the partner organization Fabrikam using HTTP transport.</span></span> <span data-ttu-id="214e9-107">Fabrikam 虚拟目录将 997 确认到\\_997ToFabrikam 文件夹，997 发送端口的 Destination_URL 设置中调出。</span><span class="sxs-lookup"><span data-stu-id="214e9-107">The Fabrikam virtual directory drops the 997 acknowledgment into the \\_997ToFabrikam folder, which is called out in the Destination_URL setting of the 997 send port.</span></span>  
  
-   <span data-ttu-id="214e9-108">设置 ASPX 页以原始消息路由至本组织 Contoso。</span><span class="sxs-lookup"><span data-stu-id="214e9-108">Set up the ASPX page to route the original message to the home organization Contoso.</span></span> <span data-ttu-id="214e9-109">Contoso 虚拟目录使用 BTSHttpReceive.dll 接收 AS2 消息并将其提交到接收位置。</span><span class="sxs-lookup"><span data-stu-id="214e9-109">The Contoso virtual directory uses BTSHttpReceive.dll to receive the AS2 message and submit it to the receive location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="214e9-110">本主题中提供的过程适用于 IIS 7.0。</span><span class="sxs-lookup"><span data-stu-id="214e9-110">The procedures provided in this topic are for IIS 7.0.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="214e9-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="214e9-111">Prerequisites</span></span>  
 <span data-ttu-id="214e9-112">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="214e9-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="214e9-113">若要启用 BTS ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="214e9-113">To enable the BTS ISAPI Filter</span></span>  
  
1. <span data-ttu-id="214e9-114">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="214e9-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2. <span data-ttu-id="214e9-115">选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在**操作**窗格中，单击**添加脚本映射**.</span><span class="sxs-lookup"><span data-stu-id="214e9-115">Select the root Web server entry and in the **Features View**, double-click **Handler Mappings** and then in the **Actions** pane, click **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="214e9-116">在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。</span><span class="sxs-lookup"><span data-stu-id="214e9-116">Configuring the script mapping at the Web server level will cause this mapping to apply to all child Web sites.</span></span> <span data-ttu-id="214e9-117">如果你想要将映射限制到特定网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。</span><span class="sxs-lookup"><span data-stu-id="214e9-117">If you wish to restrict the mapping to a specific Web site or virtual folder, select the target site or folder instead of the Web server.</span></span>  
  
3. <span data-ttu-id="214e9-118">在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。</span><span class="sxs-lookup"><span data-stu-id="214e9-118">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4. <span data-ttu-id="214e9-119">在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="214e9-119">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span> <span data-ttu-id="214e9-120">选择**BtsHttpReceive.dll**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="214e9-120">Select **BtsHttpReceive.dll**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="214e9-121">输入`BizTalk HTTP Receive`中`Name`字段中，然后依次**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="214e9-121">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6. <span data-ttu-id="214e9-122">在中**请求限制**对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。</span><span class="sxs-lookup"><span data-stu-id="214e9-122">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="214e9-123">输入`POST`作为谓词。</span><span class="sxs-lookup"><span data-stu-id="214e9-123">Enter `POST` as the verb.</span></span>  
  
7. <span data-ttu-id="214e9-124">上**访问**选项卡上，选择**脚本**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="214e9-124">On the **Access** tab, select **Script**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="214e9-125">单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="214e9-125">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
9. <span data-ttu-id="214e9-126">右键单击 BTSHttpReceive.dll 条目，然后选择**编辑功能权限**。</span><span class="sxs-lookup"><span data-stu-id="214e9-126">Right-click the BTSHttpReceive.dll entry, and then select **Edit Feature Permissions**.</span></span>  
  
10. <span data-ttu-id="214e9-127">絋粄**读**，**脚本**并**Execute**未选中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="214e9-127">Ensure that **Read**, **Script** and **Execute** are selected, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="214e9-128">单击**功能视图**，然后双击**ISAPI 和 CGI 限制**。</span><span class="sxs-lookup"><span data-stu-id="214e9-128">Click **Features View**, and then double-click **ISAPI and CGI Restrictions**.</span></span>  
  
12. <span data-ttu-id="214e9-129">确保 BTSHTTPReceive.dll 条目存在，并且**限制**设置为**允许**。</span><span class="sxs-lookup"><span data-stu-id="214e9-129">Ensure that an entry for BTSHTTPReceive.dll exists, and that **Restriction** is set to **Allowed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="214e9-130">创建脚本映射时，将自动创建 btshttpreceive.dll 的 ISAPI 和 CGI 限制条目。</span><span class="sxs-lookup"><span data-stu-id="214e9-130">The ISAPI and CGI Restriction entry for BTSHTTPReceive.dll is created automatically when you create the script map.</span></span>  
  
### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="214e9-131">若要配置 Fabrikam 网页</span><span class="sxs-lookup"><span data-stu-id="214e9-131">To configure the Fabrikam Web page</span></span>  
  
1. <span data-ttu-id="214e9-132">在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="214e9-132">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2. <span data-ttu-id="214e9-133">在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="214e9-133">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="214e9-134">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="214e9-134">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="214e9-135">版本号可能会有所不同，具体取决于版本的[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]在计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="214e9-135">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3. <span data-ttu-id="214e9-136">选择**应用程序池**，在**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="214e9-136">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4. <span data-ttu-id="214e9-137">在中**高级设置**对话框中，将**启用 32 位应用程序**到**True**。</span><span class="sxs-lookup"><span data-stu-id="214e9-137">In the **Advanced Settings** dialog box, set **Enable 32-Bit Applications** to **True**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="214e9-138">如果你希望 IIS 在 32 位模式下运行，仅在 64 位计算机上需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="214e9-138">This step is required only on a 64-bit machine if you want IIS to run in a 32-bit mode.</span></span>  
  
5. <span data-ttu-id="214e9-139">选择**标识**，然后单击**省略号 （...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="214e9-139">Select **Identity** and then click the **ellipsis (…)** button.</span></span>  
  
6. <span data-ttu-id="214e9-140">在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="214e9-140">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
7. <span data-ttu-id="214e9-141">输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。</span><span class="sxs-lookup"><span data-stu-id="214e9-141">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
8. <span data-ttu-id="214e9-142">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="214e9-142">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="214e9-143">右键单击**Default Web Site**，然后选择**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="214e9-143">Right-click the **Default Web Site**, and then select **Add Application**.</span></span>  
  
9. <span data-ttu-id="214e9-144">在中**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="214e9-144">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
10. <span data-ttu-id="214e9-145">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="214e9-145">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
11. <span data-ttu-id="214e9-146">单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 tutorial\fabrikam 作为**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="214e9-146">Click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam for the **Physical path**.</span></span>  
  
12. <span data-ttu-id="214e9-147">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="214e9-147">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="214e9-148">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="214e9-148">Click **Close**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="214e9-149">在 IIS 管理器中，选择 Fabrikam 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="214e9-149">In IIS Manager, select the Fabrikam virtual directory and in **Features View**, double-click **Authentication**.</span></span>  
  
14. <span data-ttu-id="214e9-150">在中**身份验证**，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="214e9-150">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="214e9-151">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="214e9-151">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="214e9-152">若要配置 Contoso 网页</span><span class="sxs-lookup"><span data-stu-id="214e9-152">To configure the Contoso Web page</span></span>  
  
1. <span data-ttu-id="214e9-153">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="214e9-153">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="214e9-154">右键单击**Default Web Site** ，然后选择**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="214e9-154">Right-click the **Default Web Site** and then select **Add Application**.</span></span>  
  
2. <span data-ttu-id="214e9-155">在中**添加应用程序**对话框框中，输入**Contoso**中**别名**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="214e9-155">In the **Add Application** dialog box, enter **Contoso** in **Alias**, and then click **Select**.</span></span>  
  
3. <span data-ttu-id="214e9-156">在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="214e9-156">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="214e9-157">BizTalkAppPool 以前创建的配置 Fabrikam 网页时，应设置为是 administrators 组的成员的用户的标识。</span><span class="sxs-lookup"><span data-stu-id="214e9-157">The BizTalkAppPool was created previously when configuring the Fabrikam Web page, and should be set to the identity of a user that is a member of the administrators group.</span></span>  
  
4. <span data-ttu-id="214e9-158">单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]httpreceive 作为**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="214e9-158">Click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
5. <span data-ttu-id="214e9-159">单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="214e9-159">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="214e9-160">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="214e9-160">Click **Close**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="214e9-161">在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="214e9-161">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
7. <span data-ttu-id="214e9-162">在中**身份验证**，选择**匿名身份验证**，并验证**状态**是**已启用**。</span><span class="sxs-lookup"><span data-stu-id="214e9-162">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="214e9-163">如果**状态**是**禁用**，单击**启用**中**操作**窗格。</span><span class="sxs-lookup"><span data-stu-id="214e9-163">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="214e9-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="214e9-164">Next Steps</span></span>  
 <span data-ttu-id="214e9-165">配置接收位置 (**Receive_AS2**) 以从 Fabrikam 接收 AS2 消息中所述[步骤 6:配置 EDI-AS2 接收位置](../core/step-6-configure-the-edi-as2-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="214e9-165">You configure the receive location (**Receive_AS2**) to receive the AS2 message from Fabrikam, as described in [Step 6: Configure the EDI-AS2 Receive Location](../core/step-6-configure-the-edi-as2-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214e9-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="214e9-166">See Also</span></span>  
 [<span data-ttu-id="214e9-167">教程 3：AS2 教程</span><span class="sxs-lookup"><span data-stu-id="214e9-167">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)
