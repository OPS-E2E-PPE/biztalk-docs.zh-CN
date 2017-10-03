---
title: "配置 Oracle 数据库的登录凭据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Enter the credentials
helpviewer_keywords:
- credentials, specifying at run time
- credentials, specifying at design time
ms.assetid: d8f62829-ce77-4d82-a411-2eeefb6fe75a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eda20ad4e04a9962e471ab98eb0bc5695b391007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-database"></a><span data-ttu-id="79273-102">配置登录凭据用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="79273-102">Configure the sign in credentials for the Oracle Database</span></span>
<span data-ttu-id="79273-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]需要适配器客户端提供客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="79273-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="79273-104">适配器使用这些凭据与 Oracle 数据库用户进行身份验证并建立连接。</span><span class="sxs-lookup"><span data-stu-id="79273-104">The adapter uses these credentials to authenticate the user with the Oracle database and to establish a connection.</span></span>  
  
 <span data-ttu-id="79273-105">适配器客户端可以提供在使用时的客户端凭据同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及何时使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="79273-105">Adapter clients can provide the client credentials both when using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and when using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="79273-106">使用时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，需要使用凭据才能生成元数据。</span><span class="sxs-lookup"><span data-stu-id="79273-106">When using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], credentials are required to generate the metadata.</span></span> <span data-ttu-id="79273-107">使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，所需的凭据在 Oracle 数据库上执行操作。</span><span class="sxs-lookup"><span data-stu-id="79273-107">When using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, credentials are required to perform operations on the Oracle database.</span></span> <span data-ttu-id="79273-108">本主题提供有关指定在客户端凭据的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="79273-108">This topic provides information about specifying client credentials in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="specifying-client-credentials-from-visual-studio"></a><span data-ttu-id="79273-109">指定从 Visual Studio 的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="79273-109">Specifying Client Credentials from Visual Studio</span></span>  
 <span data-ttu-id="79273-110">从 Visual Studio 中，你必须指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="79273-110">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="79273-111">若要指定使用适配器服务外接程序中使用的凭据</span><span class="sxs-lookup"><span data-stu-id="79273-111">To specify credentials using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="79273-112">右键单击你的 BizTalk 项目，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="79273-112">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="79273-113">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79273-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="79273-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="79273-114">Use this</span></span>|<span data-ttu-id="79273-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="79273-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="79273-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="79273-116">**Categories**</span></span>|<span data-ttu-id="79273-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="79273-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="79273-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="79273-118">**Templates**</span></span>|<span data-ttu-id="79273-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="79273-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="79273-120">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="79273-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="79273-121">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleDBBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="79273-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="79273-122">在**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库：</span><span class="sxs-lookup"><span data-stu-id="79273-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="79273-123">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="79273-123">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="79273-124">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="79273-124">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
6.  <span data-ttu-id="79273-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="79273-125">Click **OK**.</span></span>  
  
#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="79273-126">若要使用添加适配器元数据向导指定凭据</span><span class="sxs-lookup"><span data-stu-id="79273-126">To specify credentials using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="79273-127">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="79273-127">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="79273-128">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79273-128">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="79273-129">使用此选项</span><span class="sxs-lookup"><span data-stu-id="79273-129">Use this</span></span>|<span data-ttu-id="79273-130">执行的操作</span><span class="sxs-lookup"><span data-stu-id="79273-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="79273-131">**类别**</span><span class="sxs-lookup"><span data-stu-id="79273-131">**Categories**</span></span>|<span data-ttu-id="79273-132">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="79273-132">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="79273-133">**模板**</span><span class="sxs-lookup"><span data-stu-id="79273-133">**Templates**</span></span>|<span data-ttu-id="79273-134">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="79273-134">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="79273-135">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="79273-135">Click **Add**.</span></span> <span data-ttu-id="79273-136">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="79273-136">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="79273-137">在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**WCF OracleDB**。</span><span class="sxs-lookup"><span data-stu-id="79273-137">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleDB**.</span></span> <span data-ttu-id="79273-138">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="79273-138">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="79273-139">如果你已经在 BizTalk 中配置 WCF OracleDB 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="79273-139">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="79273-140">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="79273-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="79273-141">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleDBBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="79273-141">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="79273-142">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库：</span><span class="sxs-lookup"><span data-stu-id="79273-142">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="79273-143">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="79273-143">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="79273-144">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="79273-144">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
8.  <span data-ttu-id="79273-145">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="79273-145">Click **OK**.</span></span>  
  
## <a name="specifying-client-credentials-from-the-biztalk-server-administration-console"></a><span data-ttu-id="79273-146">指定从 BizTalk Server 管理控制台的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="79273-146">Specifying Client Credentials from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="79273-147">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须作为 WCF 自定义或 WCF OracleDB 端口配置的一部分指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="79273-147">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the credentials as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  
  
#### <a name="to-specify-client-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="79273-148">若要指定 WCF 自定义端口的客户端凭据</span><span class="sxs-lookup"><span data-stu-id="79273-148">To specify client credentials for the WCF-Custom Port</span></span>  
  
1.  <span data-ttu-id="79273-149">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="79273-149">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="79273-150">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="79273-150">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="79273-151">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="79273-151">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="79273-152">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="79273-152">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="79273-153">为发送端口，在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="79273-153">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="79273-154">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="79273-154">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="79273-155">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="79273-155">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="79273-156">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="79273-156">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="79273-157">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="79273-157">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="79273-158">接收端口，在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="79273-158">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="79273-159">选择**用户帐户**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="79273-159">Select **User account** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="79273-160">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="79273-160">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="79273-161">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="79273-161">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="79273-162">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="79273-162">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="79273-163">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="79273-163">Click **OK**.</span></span>  
  
#### <a name="to-specify-credentials-for-the-wcf-oracledb-port"></a><span data-ttu-id="79273-164">若要指定凭据，以便 WCF OracleDB 端口</span><span class="sxs-lookup"><span data-stu-id="79273-164">To specify credentials for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="79273-165">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="79273-165">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="79273-166">添加到 WCF OracleDB 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="79273-166">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="79273-167">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="79273-167">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="79273-168">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="79273-168">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="79273-169">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="79273-169">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="79273-170">在端口属性对话框中，从**类型**下拉列表中，选择**WCF OracleDB**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="79273-170">In the port properties dialog box, from the **Type** drop-down list, select **WCF-OracleDB**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79273-171">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="79273-171">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="79273-172">在端口属性对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="79273-172">In the port properties dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  
  
6.  <span data-ttu-id="79273-173">如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="79273-173">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="79273-174">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="79273-174">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="79273-175">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="79273-175">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="79273-176">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="79273-176">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="79273-177">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="79273-177">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
7.  <span data-ttu-id="79273-178">如果您创建接收端口，则在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="79273-178">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="79273-179">选择**用户帐户**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="79273-179">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="79273-180">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="79273-180">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="79273-181">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="79273-181">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="79273-182">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="79273-182">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
8.  <span data-ttu-id="79273-183">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="79273-183">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79273-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79273-184">See Also</span></span>  
<span data-ttu-id="79273-185">[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="79273-185">[Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span></span>  
 [<span data-ttu-id="79273-186">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="79273-186">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)