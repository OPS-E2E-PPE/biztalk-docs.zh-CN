---
title: 配置 SQL 适配器的凭据登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c20e177-0e64-4df3-a3dd-dca3fcf314db
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1644132db366e22e0c55fcd293bcfa82506a0c82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370017"
---
# <a name="configure-the-sign-in-credentials-for-the-sql-adapter"></a><span data-ttu-id="b7f61-102">配置 SQL 适配器的凭据登录</span><span class="sxs-lookup"><span data-stu-id="b7f61-102">Configure the sign in credentials for the SQL adapter</span></span>
<span data-ttu-id="b7f61-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]要求适配器客户端提供客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="b7f61-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="b7f61-104">若要使用 SQL Server 用户进行身份验证和建立连接，适配器将使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="b7f61-104">The adapter uses these credentials to authenticate the user with SQL Server and to establish a connection.</span></span>  

 <span data-ttu-id="b7f61-105">适配器客户端可以提供的客户端凭据同时使用时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及何时使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7f61-105">Adapter clients can provide the client credentials both when using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and when using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b7f61-106">当使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，生成元数据所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="b7f61-106">When using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], credentials are required to generate the metadata.</span></span> <span data-ttu-id="b7f61-107">当使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，凭据所需 SQL 服务器上执行操作。</span><span class="sxs-lookup"><span data-stu-id="b7f61-107">When using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, credentials are required to perform operations on SQL Server.</span></span>  

 <span data-ttu-id="b7f61-108">本部分提供有关指定在客户端凭据的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7f61-108">This section provides information about specifying client credentials in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

## <a name="enter-credentials-from-visual-studio"></a><span data-ttu-id="b7f61-109">从 Visual Studio 中输入凭据</span><span class="sxs-lookup"><span data-stu-id="b7f61-109">Enter credentials from Visual Studio</span></span>  
 <span data-ttu-id="b7f61-110">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，可以指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b7f61-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="using-consume-adapter-service-add-in"></a><span data-ttu-id="b7f61-111">使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="b7f61-111">Using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="b7f61-112">右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-112">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="b7f61-113">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7f61-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="b7f61-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b7f61-114">Use this</span></span>|<span data-ttu-id="b7f61-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7f61-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b7f61-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="b7f61-116">**Categories**</span></span>|<span data-ttu-id="b7f61-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="b7f61-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="b7f61-118">**Templates**</span></span>|<span data-ttu-id="b7f61-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="b7f61-120">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="b7f61-121">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="b7f61-122">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7f61-122">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, do one of the following:</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="b7f61-123">与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-123">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

    |<span data-ttu-id="b7f61-124">单击此选项</span><span class="sxs-lookup"><span data-stu-id="b7f61-124">Click this</span></span>|<span data-ttu-id="b7f61-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7f61-125">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="b7f61-126">**无**</span><span class="sxs-lookup"><span data-stu-id="b7f61-126">**None**</span></span>|<span data-ttu-id="b7f61-127">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-127">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="b7f61-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b7f61-128">**Windows**</span></span>|<span data-ttu-id="b7f61-129">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-129">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="b7f61-130">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b7f61-130">**Username**</span></span>|<span data-ttu-id="b7f61-131">指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="b7f61-131">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="b7f61-132">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7f61-132">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="b7f61-133">**注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7f61-133">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  

6.  <span data-ttu-id="b7f61-134">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b7f61-134">Click **OK**.</span></span>  

### <a name="using-add-adapter-metadata-wizard"></a><span data-ttu-id="b7f61-135">使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="b7f61-135">Using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="b7f61-136">右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-136">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="b7f61-137">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7f61-137">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="b7f61-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b7f61-138">Use this</span></span>    |           <span data-ttu-id="b7f61-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7f61-139">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="b7f61-140">**类别**</span><span class="sxs-lookup"><span data-stu-id="b7f61-140">**Categories**</span></span> |     <span data-ttu-id="b7f61-141">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-141">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="b7f61-142">**模板**</span><span class="sxs-lookup"><span data-stu-id="b7f61-142">**Templates**</span></span>  | <span data-ttu-id="b7f61-143">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-143">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="b7f61-144">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-144">Click **Add**.</span></span> <span data-ttu-id="b7f61-145">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="b7f61-145">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="b7f61-146">在添加适配器向导中，选择**WCF-SQL**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-146">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="b7f61-147">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="b7f61-147">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="b7f61-148">如果已配置 BizTalk 中的 WCF SQL 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="b7f61-148">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="b7f61-149">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="b7f61-149">Click **Next**.</span></span>  

6. <span data-ttu-id="b7f61-150">在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-150">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="b7f61-151">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7f61-151">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, do one of the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b7f61-152">与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-152">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   |  <span data-ttu-id="b7f61-153">单击此选项</span><span class="sxs-lookup"><span data-stu-id="b7f61-153">Click this</span></span>  |                                                                                                                                                               <span data-ttu-id="b7f61-154">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7f61-154">To do this</span></span>                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="b7f61-155">**无**</span><span class="sxs-lookup"><span data-stu-id="b7f61-155">**None**</span></span>   |                                                                                                                                         <span data-ttu-id="b7f61-156">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-156">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="b7f61-157">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b7f61-157">**Windows**</span></span>  |                                                                                                                                         <span data-ttu-id="b7f61-158">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-158">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="b7f61-159">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b7f61-159">**Username**</span></span> | <span data-ttu-id="b7f61-160">指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="b7f61-160">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="b7f61-161">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7f61-161">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="b7f61-162">**注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7f61-162">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span> |


8. <span data-ttu-id="b7f61-163">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b7f61-163">Click **OK**.</span></span>  

## <a name="enter-credentials-from-the-biztalk-server-administration-console"></a><span data-ttu-id="b7f61-164">从 BizTalk Server 管理控制台中输入凭据</span><span class="sxs-lookup"><span data-stu-id="b7f61-164">Enter credentials from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="b7f61-165">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，可以为 WCF 自定义或 WCF SQL 端口配置的一部分指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="b7f61-165">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the credentials as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  

### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="b7f61-166">WCF 自定义端口输入凭据</span><span class="sxs-lookup"><span data-stu-id="b7f61-166">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="b7f61-167">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7f61-167">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="b7f61-168">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-168">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="b7f61-169">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="b7f61-169">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="b7f61-170">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-170">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b7f61-171">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-171">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="b7f61-172">如果要创建的发送端口，请在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7f61-172">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="b7f61-173">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-173">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7f61-174">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7f61-174">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="b7f61-175">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7f61-175">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7f61-176">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-176">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="b7f61-177">选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7f61-177">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

5. <span data-ttu-id="b7f61-178">如果要创建接收端口，请在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7f61-178">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="b7f61-179">选择**用户帐户**选项，然后指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-179">Select the **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7f61-180">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7f61-180">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="b7f61-181">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7f61-181">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7f61-182">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-182">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="b7f61-183">选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7f61-183">Select the **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

6. <span data-ttu-id="b7f61-184">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b7f61-184">Click **OK**.</span></span>  

### <a name="enter-credentials-for-the-wcf-sql-port"></a><span data-ttu-id="b7f61-185">输入凭据的 WCF SQL 端口</span><span class="sxs-lookup"><span data-stu-id="b7f61-185">Enter credentials for the WCF-SQL port</span></span>  

1. <span data-ttu-id="b7f61-186">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7f61-186">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="b7f61-187">添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7f61-187">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b7f61-188">有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-188">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="b7f61-189">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-189">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="b7f61-190">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="b7f61-190">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="b7f61-191">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 WCF SQL 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-191">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b7f61-192">若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="b7f61-192">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="b7f61-193">如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7f61-193">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="b7f61-194">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-194">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7f61-195">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7f61-195">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="b7f61-196">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7f61-196">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7f61-197">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-197">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="b7f61-198">选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7f61-198">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

6. <span data-ttu-id="b7f61-199">如果要创建接收端口，在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7f61-199">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="b7f61-200">选择**用户帐户**选项，然后指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7f61-200">Select the **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7f61-201">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7f61-201">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="b7f61-202">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7f61-202">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7f61-203">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f61-203">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="b7f61-204">选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7f61-204">Select the **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

7. <span data-ttu-id="b7f61-205">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b7f61-205">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b7f61-206">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7f61-206">See Also</span></span>  
[<span data-ttu-id="b7f61-207">若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="b7f61-207">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)