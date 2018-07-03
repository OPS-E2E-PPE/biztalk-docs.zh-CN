---
title: 在 BizTalk 中使用 Wcf-oracledb 适配器配置端口 |Microsoft Docs
description: 创建 Wcf-oracledb 发送和接收端口，以在 BizTalk Server 中使用 Oracle DB 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eafefb-9b30-4801-9be9-6034ae0d3b7d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee5b39d077c48317e557072c54ba032ebe82a24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009174"
---
# <a name="configure-a-port-using-the-wcf-oracledb-adapter"></a><span data-ttu-id="021f9-103">使用 Wcf-oracledb 适配器配置端口</span><span class="sxs-lookup"><span data-stu-id="021f9-103">Configure a port using the WCF-OracleDB adapter</span></span>
<span data-ttu-id="021f9-104">如何配置 Wcf-oracledb 发送和接收端口，以执行对 Oracle 数据库使用的出站和入站操作[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="021f9-104">How to configure WCF-OracleDB send and receive ports to perform outbound and inbound operations on the Oracle database using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="021f9-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="021f9-105">Prerequisites</span></span>  
<span data-ttu-id="021f9-106">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。</span><span class="sxs-lookup"><span data-stu-id="021f9-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="021f9-107">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="021f9-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-adapters-to-send-messages-to-oracle-database"></a><span data-ttu-id="021f9-108">部署适配器将消息发送到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="021f9-108">Deploy adapters to send messages to Oracle Database</span></span>  
  
1. <span data-ttu-id="021f9-109">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="021f9-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="021f9-110">添加 Wcf-oracledb 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="021f9-110">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="021f9-111">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-111">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="021f9-112">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="021f9-112">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="021f9-113">展开你想要部署的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="021f9-113">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
5. <span data-ttu-id="021f9-114">右键单击**发送端口**，依次指向**新建**，然后指向你想要根据之间的通信的模式配置的端口类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="021f9-114">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
6. <span data-ttu-id="021f9-115">在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="021f9-115">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7. <span data-ttu-id="021f9-116">从**类型**下拉列表中，选择 Wcf-oracledb，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="021f9-116">From the **Type** drop-down list, select WCF-OracleDB, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="021f9-117">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="021f9-117">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="021f9-118">单击**常规**选项卡上，单击**配置**按钮，并提供连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="021f9-118">Click the **General** tab, click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="021f9-119">有关连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-119">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="021f9-120">上**常规**选项卡上，在**操作**文字框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="021f9-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="021f9-121">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="021f9-121">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) for a list of actions for each operation.</span></span> <span data-ttu-id="021f9-122">例如，要调用在 Oracle 数据库中的 HR 架构下的雇员表的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="021f9-122">For example, the action to invoke the Insert operation an EMPLOYEE table under the HR schema in an Oracle database is:</span></span>  
  
      ```  
      http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
      ```  
  
   3. <span data-ttu-id="021f9-123">单击**绑定**选项卡上，并为公开的绑定属性指定值[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="021f9-123">Click the **Binding** tab and specify values for the binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="021f9-124">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-124">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
      > [!NOTE]
      >  <span data-ttu-id="021f9-125">绑定属性将显示根据配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="021f9-125">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="021f9-126">例如，与通知相关的绑定属性不可用时配置的发送端口，因为通知的入站的操作并且需要进行接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="021f9-126">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
   4. <span data-ttu-id="021f9-127">单击**凭据**选项卡，然后再执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="021f9-127">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
      -   <span data-ttu-id="021f9-128">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="021f9-128">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
          -   <span data-ttu-id="021f9-129">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="021f9-129">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
          -   <span data-ttu-id="021f9-130">若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="021f9-130">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
      -   <span data-ttu-id="021f9-131">选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="021f9-131">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
   5. <span data-ttu-id="021f9-132">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="021f9-132">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="021f9-133">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="021f9-133">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="021f9-134">如果选择了**静态单向发送端口**在步骤 5 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-134">If you chose **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="021f9-135">从**发送管道**列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-135">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="021f9-136">如果选择了**静态要求响应端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-136">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="021f9-137">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-137">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="021f9-138">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-138">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
12. <span data-ttu-id="021f9-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="021f9-139">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-database"></a><span data-ttu-id="021f9-140">部署适配器从 Oracle 数据库接收消息</span><span class="sxs-lookup"><span data-stu-id="021f9-140">Deploy adapters to receive messages from Oracle Database</span></span>  
  
1. <span data-ttu-id="021f9-141">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="021f9-141">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="021f9-142">添加 Wcf-oracledb 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="021f9-142">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="021f9-143">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-143">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="021f9-144">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="021f9-144">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="021f9-145">展开你想要部署的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="021f9-145">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
5. <span data-ttu-id="021f9-146">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**，具体取决于之间的通信模式[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="021f9-146">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
6. <span data-ttu-id="021f9-147">在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="021f9-147">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7. <span data-ttu-id="021f9-148">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="021f9-148">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="021f9-149">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="021f9-149">The **Receive Location Properties** dialog box appears.</span></span>  
  
8. <span data-ttu-id="021f9-150">在中**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="021f9-150">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="021f9-151">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="021f9-151">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="021f9-152">从**类型**下拉列表中，选择 Wcf-oracledb，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="021f9-152">From the **Type** drop-down list, select WCF-OracleDB, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="021f9-153">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="021f9-153">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="021f9-154">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="021f9-154">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="021f9-155">有关连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-155">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="021f9-156">单击**绑定**选项卡，指定的绑定公开的属性值[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="021f9-156">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="021f9-157">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-157">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
      > [!NOTE]
      >  <span data-ttu-id="021f9-158">绑定属性将显示根据配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="021f9-158">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="021f9-159">例如，与通知相关的绑定属性不可用时配置的发送端口，因为通知的入站的操作并且需要进行接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="021f9-159">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
   3. <span data-ttu-id="021f9-160">单击**行为**选项卡以设置事务隔离级别。</span><span class="sxs-lookup"><span data-stu-id="021f9-160">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="021f9-161">有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)。</span><span class="sxs-lookup"><span data-stu-id="021f9-161">For more information about setting transaction isolation level, see [Configure transaction isolation level and transaction timeout](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).</span></span>  
  
   4. <span data-ttu-id="021f9-162">单击**他人**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="021f9-162">Click the **Others** tab, and do one of the following:</span></span>  
  
      -   <span data-ttu-id="021f9-163">选择**用户帐户**选项，然后指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="021f9-163">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
          -   <span data-ttu-id="021f9-164">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="021f9-164">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
          -   <span data-ttu-id="021f9-165">若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="021f9-165">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
      -   <span data-ttu-id="021f9-166">选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="021f9-166">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
   5. <span data-ttu-id="021f9-167">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="021f9-167">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="021f9-168">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="021f9-168">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="021f9-169">如果选择了**单向接收端口**在步骤 5 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-169">If you chose **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="021f9-170">从**接收管道**列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-170">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="021f9-171">如果选择了**请求响应接收端口**在步骤 5 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-171">If you chose **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="021f9-172">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-172">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="021f9-173">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="021f9-173">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="021f9-174">在中**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="021f9-174">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="021f9-175">在中**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="021f9-175">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021f9-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="021f9-176">See Also</span></span>  
   [<span data-ttu-id="021f9-177">手动配置到 Oracle 数据库适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="021f9-177">Manually configure a physical port binding to the Oracle Database Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)
 
 [<span data-ttu-id="021f9-178">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="021f9-178">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)