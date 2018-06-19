---
title: 配置端口使用 BizTalk 中的 WCF 自定义适配器和 SQL 适配器 |Microsoft 文档
description: 创建 WCF 自定义发送和接收要在 BizTalk Server 中使用 SQL Server 适配器的端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d44d9932-0a5e-4072-a480-2f8dc544ca79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c2a47cf267bd3316600ad68a241a204090f3da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226029"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter"></a><span data-ttu-id="1702c-103">配置使用 WCF 自定义适配器和 SQL 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="1702c-103">Configure a port using the WCF-custom adapter and SQL adapter</span></span>
<span data-ttu-id="1702c-104">配置 WCF 自定义发送和接收端口到执行 SQL Server 使用的出站和入站操作步骤[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1702c-104">Steps to configure WCF-Custom send and receive ports to perform outbound and inbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1702c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="1702c-105">Prerequisites</span></span>  
<span data-ttu-id="1702c-106">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="1702c-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="1702c-107">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1702c-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a><span data-ttu-id="1702c-108">部署适配器，以将消息发送到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1702c-108">Deploy adapters to send messages to SQL Server</span></span>  
 <span data-ttu-id="1702c-109">执行以下步骤以配置 WCF 自定义发送端口将消息发送到 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1702c-109">Perform the following steps to configure a WCF-Custom send port for sending messages to SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>    
 
1.  <span data-ttu-id="1702c-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1702c-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="1702c-111">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1702c-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="1702c-112">展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1702c-112">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="1702c-113">右键单击**发送端口**，指向**新建**，然后指向你想要根据之间的通信模式配置的端口的类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1702c-113">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
5.  <span data-ttu-id="1702c-114">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1702c-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="1702c-115">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1702c-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="1702c-116">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1702c-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1702c-117">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="1702c-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="1702c-118">有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-118">For more information about the connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="1702c-119">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="1702c-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="1702c-120">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="1702c-120">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="1702c-121">例如，要调用的 SQL Server 数据库中的表上的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="1702c-121">For example, the action to invoke the Insert operation on a table in a SQL Server database is:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="1702c-122">员工是 SQL Server 数据库中表的名称。</span><span class="sxs-lookup"><span data-stu-id="1702c-122">Employee is the name of a table in SQL Server database.</span></span>  
  
    3.  <span data-ttu-id="1702c-123">单击**绑定**选项卡上，并从**绑定类型**列表中，选择**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="1702c-123">Click the **Binding** tab, and from the **Binding Type** list, select **sqlBinding**.</span></span> <span data-ttu-id="1702c-124">你可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1702c-124">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="1702c-125">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-125">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="1702c-126">单击**凭据**选项卡，，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1702c-126">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="1702c-127">选择**不使用单一登录**选项，以及指定的用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1702c-127">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="1702c-128">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="1702c-128">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="1702c-129">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="1702c-129">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="1702c-130">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-130">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
        -   <span data-ttu-id="1702c-131">选择**使用单一登录**选项，，然后指定关联企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1702c-131">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
             <span data-ttu-id="1702c-132">有关与 BizTalk Server 安全性的详细信息，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-132">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="1702c-133">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1702c-133">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="1702c-134">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="1702c-134">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="1702c-135">如果你选择了**静态单向发送端口**在步骤 4 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-135">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="1702c-136">从**发送管道**列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-136">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="1702c-137">如果你选择了**静态请求-响应端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-137">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="1702c-138">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-138">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="1702c-139">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-139">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="1702c-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="1702c-140">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a><span data-ttu-id="1702c-141">部署适配器从 SQL Server 接收消息</span><span class="sxs-lookup"><span data-stu-id="1702c-141">Deploy adapters to receive messages from SQL Server</span></span>
 <span data-ttu-id="1702c-142">执行以下步骤来配置 WCF 自定义接收端口来接收消息从 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1702c-142">Perform the following steps to configure a WCF-Custom receive port for receiving messages from SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="1702c-143">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1702c-143">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="1702c-144">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1702c-144">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="1702c-145">展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1702c-145">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="1702c-146">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**，具体取决于模式之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1702c-146">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
5.  <span data-ttu-id="1702c-147">在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1702c-147">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="1702c-148">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1702c-148">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="1702c-149">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="1702c-149">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="1702c-150">在**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1702c-150">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1702c-151">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="1702c-151">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="1702c-152">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1702c-152">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="1702c-153">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1702c-153">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1702c-154">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="1702c-154">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="1702c-155">有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-155">For more information about the connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="1702c-156">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="1702c-156">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sqlBinding**.</span></span> <span data-ttu-id="1702c-157">你可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1702c-157">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="1702c-158">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-158">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="1702c-159">单击**行为**选项卡以设置事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="1702c-159">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="1702c-160">有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和与 SQL 的事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-160">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
    4.  <span data-ttu-id="1702c-161">单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1702c-161">Click the **Other** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="1702c-162">选择**用户帐户**，并指定的用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1702c-162">Select **User account**, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="1702c-163">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="1702c-163">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="1702c-164">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="1702c-164">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="1702c-165">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-165">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
        -   <span data-ttu-id="1702c-166">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1702c-166">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
             <span data-ttu-id="1702c-167">有关实施与安全性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1702c-167">For more information about security with respect to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="1702c-168">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1702c-168">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="1702c-169">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="1702c-169">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="1702c-170">如果你选择了**单向接收端口**在步骤 4 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-170">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="1702c-171">从**接收管道**列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-171">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="1702c-172">如果你选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-172">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="1702c-173">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-173">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="1702c-174">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="1702c-174">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="1702c-175">在**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1702c-175">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="1702c-176">在**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1702c-176">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1702c-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1702c-177">See Also</span></span>  
[<span data-ttu-id="1702c-178">手动配置到 SQL 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="1702c-178">Manually configure a physical port binding to the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)