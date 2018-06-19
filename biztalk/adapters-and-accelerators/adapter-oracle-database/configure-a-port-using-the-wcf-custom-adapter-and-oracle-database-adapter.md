---
title: 配置端口使用 WCF 自定义适配器和 Oracle 数据库适配器 |Microsoft 文档
description: 创建 WCF 自定义发送和接收要在 BizTalk Server 中使用 Oracle 数据库适配器的端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c99ff526-ad97-4095-812f-0ce88b071e7f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7831ab57e7cae268aa1f47f380c69ef854b092b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215853"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter"></a><span data-ttu-id="a9c8e-103">配置使用 WCF 自定义适配器和 Oracle 数据库适配器的端口</span><span class="sxs-lookup"><span data-stu-id="a9c8e-103">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>
<span data-ttu-id="a9c8e-104">如何配置 WCF 自定义发送和接收端口来执行对 Oracle 数据库使用的出站和入站操作[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-104">How to configure WCF-Custom send and receive ports to perform outbound and inbound operations on the Oracle database using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a9c8e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="a9c8e-105">Prerequisites</span></span>  
<span data-ttu-id="a9c8e-106">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="a9c8e-107">请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)有关权限的指南。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-107">See [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) for permissions guidance.</span></span>
  
## <a name="deploy-adapters-for-sending-messages-to-an-oracle-database"></a><span data-ttu-id="a9c8e-108">部署用于将消息发送到 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="a9c8e-108">Deploy adapters for sending messages to an Oracle database</span></span>  
  
1.  <span data-ttu-id="a9c8e-109">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a9c8e-110">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-110">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="a9c8e-111">展开你想要部署的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-111">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="a9c8e-112">右键单击**发送端口**，指向**新建**，并指向一种你想要根据之间的通信模式配置的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-112">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
5.  <span data-ttu-id="a9c8e-113">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-113">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="a9c8e-114">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-114">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="a9c8e-115">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9c8e-115">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a9c8e-116">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 Oracle 数据库的连接 URI。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-116">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the Oracle database.</span></span> <span data-ttu-id="a9c8e-117">有关连接 URI 的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-117">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="a9c8e-118">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-118">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="a9c8e-119">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-119">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) for a list of actions for each operation.</span></span> <span data-ttu-id="a9c8e-120">例如，要调用插入操作 Oracle 数据库中的 HR 模式下的员工表的操作是：</span><span class="sxs-lookup"><span data-stu-id="a9c8e-120">For example, the action to invoke the Insert operation an EMPLOYEE table under the HR schema in an Oracle database is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
        ```  
  
    3.  <span data-ttu-id="a9c8e-121">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**oracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-121">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span> <span data-ttu-id="a9c8e-122">你可以指定不同的绑定属性公开的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-122">You can specify the different binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="a9c8e-123">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-123">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="a9c8e-124">单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a9c8e-124">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="a9c8e-125">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-125">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
            -   <span data-ttu-id="a9c8e-126">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-126">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
            -   <span data-ttu-id="a9c8e-127">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-127">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
        -   <span data-ttu-id="a9c8e-128">选择**使用单一登录**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-128">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
         <span data-ttu-id="a9c8e-129">有关与 BizTalk Server 安全性的详细信息，请参阅[安全性与 Oracle 数据库适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-129">For more information about security with respect to BizTalk Server, see [Security with the Oracle Database adapter and BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span>  
  
         <span data-ttu-id="a9c8e-130">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-130">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="a9c8e-131">从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-131">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="a9c8e-132">如果你选择了**静态单向发送端口**在步骤 4 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-132">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="a9c8e-133">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-133">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="a9c8e-134">如果你选择了**静态请求-响应端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-134">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="a9c8e-135">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-135">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="a9c8e-136">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-136">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="a9c8e-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-137">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-for-receiving-messages-from-an-oracle-database"></a><span data-ttu-id="a9c8e-138">部署用于从 Oracle 数据库中接收消息的适配器</span><span class="sxs-lookup"><span data-stu-id="a9c8e-138">Deploy adapters for receiving messages from an Oracle database</span></span>  
  
1.  <span data-ttu-id="a9c8e-139">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-139">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a9c8e-140">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-140">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="a9c8e-141">展开你想要部署的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-141">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="a9c8e-142">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**，具体取决于BizTalk Server 和 Oracle 数据库之间的通信模式。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-142">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between BizTalk Server and the Oracle database.</span></span>  
  
5.  <span data-ttu-id="a9c8e-143">在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-143">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="a9c8e-144">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-144">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="a9c8e-145">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-145">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="a9c8e-146">在**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9c8e-146">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a9c8e-147">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-147">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="a9c8e-148">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-148">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a9c8e-149">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9c8e-149">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a9c8e-150">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 Oracle 数据库的连接 URI。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-150">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the Oracle database.</span></span> <span data-ttu-id="a9c8e-151">有关连接 URI 的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-151">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="a9c8e-152">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**oracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-152">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span> <span data-ttu-id="a9c8e-153">你可以指定不同的绑定属性公开的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-153">You can specify the different binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="a9c8e-154">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-154">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="a9c8e-155">单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a9c8e-155">Click the **Others** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="a9c8e-156">选择**用户帐户**，并指定的用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-156">Select **User account**, and specify the user name and password to connect to an Oracle database.</span></span>  
  
            -   <span data-ttu-id="a9c8e-157">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-157">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
            -   <span data-ttu-id="a9c8e-158">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-158">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
        -   <span data-ttu-id="a9c8e-159">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-159">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
         <span data-ttu-id="a9c8e-160">有关与 BizTalk Server 安全性的详细信息，请参阅[安全性与 Oracle 数据库适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-160">For more information about security with respect to BizTalk Server, see [Security with the Oracle Database adapter and BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span>
  
         <span data-ttu-id="a9c8e-161">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-161">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="a9c8e-162">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-162">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="a9c8e-163">如果你选择了**单向接收端口**在步骤 4 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-163">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="a9c8e-164">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-164">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="a9c8e-165">如果你选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-165">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="a9c8e-166">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-166">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="a9c8e-167">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-167">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="a9c8e-168">在**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-168">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="a9c8e-169">在**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a9c8e-169">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c8e-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9c8e-170">See Also</span></span>  
<span data-ttu-id="a9c8e-171">[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a9c8e-171">[Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md) </span></span>  
 [<span data-ttu-id="a9c8e-172">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="a9c8e-172">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)