---
title: 配置在 BizTalk 中使用 WCF SQL 适配器的端口 |Microsoft 文档
description: 创建 WCF SQL 发送和接收要在 BizTalk Server 中使用 SQL Server 适配器的端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cdc032-3160-43de-9510-7ca69506083e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a2ca9bda40aa016efba95b89948f1d12bc49f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226405"
---
# <a name="configure-a-port-using-the-wcf-sql-adapter"></a><span data-ttu-id="f51be-103">配置使用 WCF SQL 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="f51be-103">Configure a port using the WCF-SQL adapter</span></span>
<span data-ttu-id="f51be-104">本主题提供有关如何配置 WCF SQL 说明发送和接收端口上使用 SQL Server 执行出站和入站操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f51be-104">This topic provides instructions on how to configure WCF-SQL send and receive ports to perform outbound and inbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f51be-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="f51be-105">Prerequisites</span></span>  
<span data-ttu-id="f51be-106">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="f51be-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="f51be-107">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f51be-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a><span data-ttu-id="f51be-108">部署适配器，以将消息发送到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="f51be-108">Deploy adapters to send messages to SQL Server</span></span>  
 <span data-ttu-id="f51be-109">执行以下步骤以配置 WCF SQL 发送端口将消息发送到 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f51be-109">Perform the following steps to configure a WCF-SQL send port for sending messages to SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="f51be-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f51be-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f51be-111">添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f51be-111">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f51be-112">有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-112">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="f51be-113">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f51be-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="f51be-114">展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f51be-114">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
5.  <span data-ttu-id="f51be-115">右键单击**发送端口**，指向**新建**，然后指向你想要根据之间的通信模式配置的端口的类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="f51be-115">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
6.  <span data-ttu-id="f51be-116">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="f51be-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="f51be-117">从**类型**下拉列表中，选择更早版本，添加了 WCF SQL 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f51be-117">From the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="f51be-118">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f51be-118">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f51be-119">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="f51be-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="f51be-120">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-120">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="f51be-121">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="f51be-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="f51be-122">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="f51be-122">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="f51be-123">例如，要调用的 SQL Server 数据库中的表上的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="f51be-123">For example, the action to invoke the Insert operation on a table in a SQL Server database is:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="f51be-124">员工是 SQL Server 数据库中表的名称。</span><span class="sxs-lookup"><span data-stu-id="f51be-124">Employee is the name of a table in SQL Server database.</span></span>  
  
    3.  <span data-ttu-id="f51be-125">单击**绑定**选项卡上，并指定绑定以公开的属性的值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f51be-125">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f51be-126">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-126">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f51be-127">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="f51be-127">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="f51be-128">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="f51be-128">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    4.  <span data-ttu-id="f51be-129">单击**凭据**选项卡，，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f51be-129">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="f51be-130">选择**不使用单一登录**选项，以及指定的用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="f51be-130">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="f51be-131">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f51be-131">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="f51be-132">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f51be-132">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="f51be-133">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-133">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
        -   <span data-ttu-id="f51be-134">选择**使用单一登录**选项，，然后指定关联企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f51be-134">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
             <span data-ttu-id="f51be-135">有关与 BizTalk Server 安全性的详细信息，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-135">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="f51be-136">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f51be-136">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="f51be-137">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="f51be-137">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="f51be-138">如果你选择创建**静态单向发送端口**在步骤 5 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-138">If you chose to create **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="f51be-139">从**发送管道**列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-139">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="f51be-140">如果你选择创建**静态请求-响应端口**在步骤 5 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-140">If you chose to create **Static Solicit-Response Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="f51be-141">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-141">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="f51be-142">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-142">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
12. <span data-ttu-id="f51be-143">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f51be-143">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a><span data-ttu-id="f51be-144">部署适配器从 SQL Server 接收消息</span><span class="sxs-lookup"><span data-stu-id="f51be-144">Deploy adapters to receive messages from SQL Server</span></span>  
 <span data-ttu-id="f51be-145">执行以下步骤来配置 WCF SQL 接收端口来接收消息从 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f51be-145">Perform the following steps to configure a WCF-SQL receive port for receiving messages from SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="f51be-146">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f51be-146">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f51be-147">添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f51be-147">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f51be-148">有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-148">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="f51be-149">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f51be-149">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="f51be-150">展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f51be-150">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
5.  <span data-ttu-id="f51be-151">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**，具体取决于模式之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="f51be-151">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
6.  <span data-ttu-id="f51be-152">在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="f51be-152">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7.  <span data-ttu-id="f51be-153">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="f51be-153">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="f51be-154">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="f51be-154">The **Receive Location Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="f51be-155">在**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f51be-155">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f51be-156">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="f51be-156">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="f51be-157">从**类型**下拉列表中，选择更早版本，添加了 WCF SQL 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f51be-157">From the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="f51be-158">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f51be-158">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f51be-159">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="f51be-159">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="f51be-160">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-160">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="f51be-161">单击**绑定**选项卡上，并指定绑定以公开的属性的值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f51be-161">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f51be-162">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-162">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f51be-163">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="f51be-163">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="f51be-164">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="f51be-164">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    3.  <span data-ttu-id="f51be-165">单击**行为**选项卡以设置事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="f51be-165">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="f51be-166">有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和与 SQL 的事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-166">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
    4.  <span data-ttu-id="f51be-167">单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f51be-167">Click the **Other** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="f51be-168">选择**用户帐户**，并指定的用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="f51be-168">Select **User account**, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="f51be-169">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f51be-169">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="f51be-170">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f51be-170">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="f51be-171">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-171">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
        -   <span data-ttu-id="f51be-172">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f51be-172">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
             <span data-ttu-id="f51be-173">有关实施与安全性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f51be-173">For more information about security with respect to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="f51be-174">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f51be-174">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="f51be-175">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="f51be-175">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="f51be-176">如果你选择创建**单向接收端口**在步骤 5 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-176">If you chose to create **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="f51be-177">从**接收管道**列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-177">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="f51be-178">如果你选择创建**请求响应接收端口**在步骤 5 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-178">If you chose to create **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="f51be-179">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-179">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="f51be-180">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="f51be-180">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="f51be-181">在**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f51be-181">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="f51be-182">在**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f51be-182">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51be-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f51be-183">See Also</span></span>  
[<span data-ttu-id="f51be-184">手动配置到 SQL 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="f51be-184">Manually configure a physical port binding to the SQL adapter </span></span>](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)