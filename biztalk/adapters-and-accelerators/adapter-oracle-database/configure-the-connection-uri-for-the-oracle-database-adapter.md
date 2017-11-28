---
title: "配置 Oracle 数据库适配器的连接 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at design time
- connection URI, specifying at run time
ms.assetid: 9f302b67-0bcc-44d1-9517-10d402873540
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63cede1957c2f5f34396bbe2251a98cfc3965e7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-the-oracle-database-adapter"></a><span data-ttu-id="7f73b-102">配置 Oracle 数据库适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="7f73b-102">Configure the connection URI for the Oracle Database adapter</span></span>
<span data-ttu-id="7f73b-103">连接 URI 是包含连接到 Oracle 数据库所需的参数的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7f73b-103">A connection URI is a connection string that contains parameters required to connect to the Oracle database.</span></span> <span data-ttu-id="7f73b-104">在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要连接到 Oracle 数据库生成的元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="7f73b-104">While using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the URI to connect to the Oracle database to generate the metadata.</span></span> <span data-ttu-id="7f73b-105">配置业务流程使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须指定要连接到 Oracle 数据库以执行操作的 URI。</span><span class="sxs-lookup"><span data-stu-id="7f73b-105">While configuring an orchestration using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the URI to connect to the Oracle database to perform operations.</span></span>  
  
## <a name="specifying-the-connection-uri-from-visual-studio"></a><span data-ttu-id="7f73b-106">指定连接 URI 从 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7f73b-106">Specifying the Connection URI from Visual Studio</span></span>  
 <span data-ttu-id="7f73b-107">从 Visual Studio 中，你必须指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f73b-107">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="7f73b-108">若要指定使用适配器服务外接程序中使用的连接 URI</span><span class="sxs-lookup"><span data-stu-id="7f73b-108">To specify the Connection URI using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="7f73b-109">右键单击你的 BizTalk 项目，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-109">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="7f73b-110">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f73b-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7f73b-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7f73b-111">Use this</span></span>|<span data-ttu-id="7f73b-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7f73b-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f73b-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="7f73b-113">**Categories**</span></span>|<span data-ttu-id="7f73b-114">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-114">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="7f73b-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="7f73b-115">**Templates**</span></span>|<span data-ttu-id="7f73b-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-116">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="7f73b-117">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-117">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="7f73b-118">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleDBBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-118">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="7f73b-119">在**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库：</span><span class="sxs-lookup"><span data-stu-id="7f73b-119">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="7f73b-120">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="7f73b-120">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="7f73b-121">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="7f73b-121">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
6.  <span data-ttu-id="7f73b-122">单击**URI 属性**选项卡，然后指定不同的参数的值。</span><span class="sxs-lookup"><span data-stu-id="7f73b-122">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="7f73b-123">有关连接 URI 的详细信息为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="7f73b-123">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="7f73b-124">单击**绑定属性**选项卡，然后指定的绑定值中，如果有的话，生成架构之前所需的。</span><span class="sxs-lookup"><span data-stu-id="7f73b-124">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="7f73b-125">有关绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="7f73b-125">For more information about binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
8.  <span data-ttu-id="7f73b-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-126">Click **OK**.</span></span>  
  
#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="7f73b-127">若要指定连接 URI 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="7f73b-127">To specify the Connection URI using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="7f73b-128">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-128">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="7f73b-129">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f73b-129">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7f73b-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7f73b-130">Use this</span></span>|<span data-ttu-id="7f73b-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7f73b-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f73b-132">**类别**</span><span class="sxs-lookup"><span data-stu-id="7f73b-132">**Categories**</span></span>|<span data-ttu-id="7f73b-133">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-133">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="7f73b-134">**模板**</span><span class="sxs-lookup"><span data-stu-id="7f73b-134">**Templates**</span></span>|<span data-ttu-id="7f73b-135">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-135">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="7f73b-136">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-136">Click **Add**.</span></span> <span data-ttu-id="7f73b-137">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="7f73b-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="7f73b-138">在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**WCF OracleDB**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-138">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleDB**.</span></span> <span data-ttu-id="7f73b-139">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="7f73b-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f73b-140">如果你已经在 BizTalk 中配置 WCF OracleDB 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="7f73b-140">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="7f73b-141">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-141">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7f73b-142">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleDBBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="7f73b-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="7f73b-143">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库：</span><span class="sxs-lookup"><span data-stu-id="7f73b-143">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="7f73b-144">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="7f73b-144">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="7f73b-145">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="7f73b-145">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
8.  <span data-ttu-id="7f73b-146">单击**URI 属性**选项卡，然后指定不同的参数的值。</span><span class="sxs-lookup"><span data-stu-id="7f73b-146">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="7f73b-147">有关连接 URI 的详细信息为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="7f73b-147">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
9. <span data-ttu-id="7f73b-148">单击**绑定属性**选项卡，然后指定的绑定值中，如果有的话，生成架构之前所需的。</span><span class="sxs-lookup"><span data-stu-id="7f73b-148">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="7f73b-149">有关绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="7f73b-149">For more information about binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
10. <span data-ttu-id="7f73b-150">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-150">Click **OK**.</span></span>  
  
## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a><span data-ttu-id="7f73b-151">指定连接 URI 从 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7f73b-151">Specifying the Connection URI from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="7f73b-152">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须作为 WCF 自定义或 WCF OracleDB 端口配置的一部分指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="7f73b-152">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the credentials as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="7f73b-153">若要指定 WCF 自定义端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="7f73b-153">To specify the Connection URI for the WCF-Custom Port</span></span>  
  
1.  <span data-ttu-id="7f73b-154">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7f73b-154">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7f73b-155">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-155">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="7f73b-156">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="7f73b-156">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="7f73b-157">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-157">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="7f73b-158">为发送端口，在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f73b-158">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="7f73b-159">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f73b-159">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="7f73b-160">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="7f73b-160">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="7f73b-161">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="7f73b-161">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="7f73b-162">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f73b-162">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="7f73b-163">接收端口，在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f73b-163">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="7f73b-164">选择**用户帐户**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f73b-164">Select **User account** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="7f73b-165">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="7f73b-165">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="7f73b-166">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="7f73b-166">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="7f73b-167">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f73b-167">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="7f73b-168">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-168">Click **OK**.</span></span>  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-oracledb-port"></a><span data-ttu-id="7f73b-169">若要指定 WCF OracleDB 端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="7f73b-169">To specify the Connection URI for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="7f73b-170">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7f73b-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7f73b-171">添加到 WCF OracleDB 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7f73b-171">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7f73b-172">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7f73b-172">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="7f73b-173">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="7f73b-174">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="7f73b-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="7f73b-175">在端口属性对话框中，从**类型**下拉列表中，选择**WCF OracleDB**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-175">In the port properties dialog box, from the **Type** drop-down list, select **WCF-OracleDB**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f73b-176">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-176">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="7f73b-177">在端口属性对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-177">In the port properties dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  
  
6.  <span data-ttu-id="7f73b-178">如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f73b-178">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="7f73b-179">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f73b-179">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="7f73b-180">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="7f73b-180">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="7f73b-181">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="7f73b-181">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="7f73b-182">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f73b-182">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
7.  <span data-ttu-id="7f73b-183">如果您创建接收端口，则在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f73b-183">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="7f73b-184">选择**用户帐户**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f73b-184">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="7f73b-185">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="7f73b-185">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="7f73b-186">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="7f73b-186">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="7f73b-187">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f73b-187">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
8.  <span data-ttu-id="7f73b-188">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7f73b-188">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f73b-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f73b-189">See Also</span></span>  
<span data-ttu-id="7f73b-190">[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="7f73b-190">[Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span></span>  
 [<span data-ttu-id="7f73b-191">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="7f73b-191">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)