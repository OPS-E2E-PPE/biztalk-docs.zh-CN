---
title: "配置端口使用 BizTalk 中的 WCF 自定义适配器和 Oracle E-business Suite |Microsoft 文档"
description: "使用 WCF 自定义适配器来接收或从 BizTalk Server 中的 Oracle EBS 发送消息"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83d0bb00-934c-40cf-8833-354e7ce7e927
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f6071c4df6e60024483e897d577281b1f39487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite"></a><span data-ttu-id="73e34-103">配置端口使用 WCF 自定义适配器和 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="73e34-103">Configure a port using the WCF-custom adapter and Oracle E-Business Suite</span></span>
<span data-ttu-id="73e34-104">如何配置 WCF 自定义发送和接收端口执行 Oracle E-business Suite 使用的出站和入站操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73e34-104">How to configure WCF-Custom send and receive ports to perform outbound and inbound operations on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73e34-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="73e34-105">Prerequisites</span></span>  
<span data-ttu-id="73e34-106">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="73e34-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="73e34-107">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="73e34-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a><span data-ttu-id="73e34-108">部署适配器，以将消息发送到 Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="73e34-108">Deploy adapters to send messages to Oracle EBS</span></span>  
 <span data-ttu-id="73e34-109">执行以下步骤以配置 WCF 自定义发送端口将消息发送到 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73e34-109">Perform the following steps to configure a WCF-Custom send port for sending messages to Oracle E-Business Suite using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="73e34-110">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73e34-110">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="73e34-111">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="73e34-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="73e34-112">展开你想要部署的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73e34-112">Expand the application under which you want to deploy the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="73e34-113">右键单击**发送端口**，指向**新建**，然后指向你想要根据之间的通信模式配置的端口的类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="73e34-113">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Oracle E-Business Suite.</span></span>  
  
5.  <span data-ttu-id="73e34-114">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="73e34-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="73e34-115">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="73e34-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="73e34-116">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73e34-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="73e34-117">单击**常规**选项卡上，然后在**地址 (URI)**字段中，指定 Oracle E-business Suite 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="73e34-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for Oracle E-Business Suite.</span></span> <span data-ttu-id="73e34-118">有关连接 URI 的详细信息，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="73e34-118">For more information about the connection URI, see [Create the Oracle E-Business Suite Connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="73e34-119">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="73e34-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="73e34-120">请参阅[消息和 Oracle EBS 适配器的消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)) 有关的操作的每个操作的列表。</span><span class="sxs-lookup"><span data-stu-id="73e34-120">See [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)) for a list of actions for each operation.</span></span> <span data-ttu-id="73e34-121">例如，要调用该资产应用程序下接口表 (FA_BOOKS) 上的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="73e34-121">For example, the action to invoke the Insert operation on an interface table (FA_BOOKS) under the Asset application is:</span></span>  
  
        ```  
        InterfaceTables/Insert/OFA/FA/FA_BOOKS  
        ```  
  
    3.  <span data-ttu-id="73e34-122">单击**绑定**选项卡上，并从**绑定类型**列表中，选择**oracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="73e34-122">Click the **Binding** tab, and from the **Binding Type** list, select **oracleEBSBinding**.</span></span> <span data-ttu-id="73e34-123">你可以指定不同的绑定属性公开的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73e34-123">You can specify the different binding properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="73e34-124">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="73e34-124">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="73e34-125">单击**凭据**选项卡，，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="73e34-125">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="73e34-126">选择**不使用单一登录**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="73e34-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to Oracle E-Business Suite.</span></span>  
  
            |<span data-ttu-id="73e34-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="73e34-127">Use this</span></span>|<span data-ttu-id="73e34-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="73e34-128">To do this</span></span>|  
            |--------------|----------------|  
            |<span data-ttu-id="73e34-129">**使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-129">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="73e34-130">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="73e34-130">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
            |<span data-ttu-id="73e34-131">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-131">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="73e34-132">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="73e34-132">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="73e34-133">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="73e34-133">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
            |<span data-ttu-id="73e34-134">**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-134">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="73e34-135">指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="73e34-135">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
            |<span data-ttu-id="73e34-136">**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-136">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="73e34-137">指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="73e34-137">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="73e34-138">你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="73e34-138">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
        -   <span data-ttu-id="73e34-139">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="73e34-139">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
    5.  <span data-ttu-id="73e34-140">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="73e34-140">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="73e34-141">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="73e34-141">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="73e34-142">如果你选择了**静态单向发送端口**在步骤 4 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-142">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="73e34-143">从**发送管道**列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-143">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="73e34-144">如果你选择了**静态请求-响应端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-144">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="73e34-145">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-145">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="73e34-146">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-146">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="73e34-147">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="73e34-147">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a><span data-ttu-id="73e34-148">部署适配器从 Oracle EBS 接收消息</span><span class="sxs-lookup"><span data-stu-id="73e34-148">Deploy adapters to receive messages from Oracle EBS</span></span> 
 <span data-ttu-id="73e34-149">执行以下步骤来配置 WCF 自定义接收端口来接收消息从 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73e34-149">Perform the following steps to configure a WCF-Custom receive port for receiving messages from Oracle E-Business Suite using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="73e34-150">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73e34-150">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="73e34-151">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="73e34-151">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="73e34-152">展开你想要部署的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73e34-152">Expand the application under which you want to deploy the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="73e34-153">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**，具体取决于模式之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="73e34-153">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Oracle E-Business Suite.</span></span>  
  
5.  <span data-ttu-id="73e34-154">在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="73e34-154">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="73e34-155">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="73e34-155">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="73e34-156">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="73e34-156">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="73e34-157">在**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73e34-157">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="73e34-158">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="73e34-158">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="73e34-159">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="73e34-159">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="73e34-160">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73e34-160">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="73e34-161">单击**常规**选项卡上，然后在**地址 (URI)**字段中，指定 Oracle E-business Suite 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="73e34-161">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for Oracle E-Business Suite.</span></span> <span data-ttu-id="73e34-162">有关连接 URI 的详细信息，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="73e34-162">For more information about the connection URI, see [Create the Oracle E-Business Suite Connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="73e34-163">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**oracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="73e34-163">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleEBSBinding**.</span></span> <span data-ttu-id="73e34-164">你可以指定不同的绑定属性公开的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73e34-164">You can specify the different binding properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="73e34-165">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="73e34-165">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="73e34-166">单击**行为**选项卡以设置事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="73e34-166">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="73e34-167">有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和与 E-business Suite 的事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="73e34-167">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).</span></span>  
  
    4.  <span data-ttu-id="73e34-168">单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="73e34-168">Click the **Others** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="73e34-169">选择**用户帐户**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="73e34-169">Select **User account** option, and specify the user name and password to connect to Oracle E-Business Suite.</span></span>  
  
            |<span data-ttu-id="73e34-170">使用此选项</span><span class="sxs-lookup"><span data-stu-id="73e34-170">Use this</span></span>|<span data-ttu-id="73e34-171">执行的操作</span><span class="sxs-lookup"><span data-stu-id="73e34-171">To do this</span></span>|  
            |--------------|----------------|  
            |<span data-ttu-id="73e34-172">**使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-172">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="73e34-173">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="73e34-173">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
            |<span data-ttu-id="73e34-174">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-174">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="73e34-175">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="73e34-175">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="73e34-176">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="73e34-176">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
            |<span data-ttu-id="73e34-177">**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-177">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="73e34-178">指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="73e34-178">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
            |<span data-ttu-id="73e34-179">**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="73e34-179">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="73e34-180">指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="73e34-180">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="73e34-181">你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="73e34-181">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
        -   <span data-ttu-id="73e34-182">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="73e34-182">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
    5.  <span data-ttu-id="73e34-183">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="73e34-183">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="73e34-184">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="73e34-184">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="73e34-185">如果你选择了**单向接收端口**在步骤 4 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-185">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="73e34-186">从**接收管道**列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-186">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="73e34-187">如果你选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-187">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="73e34-188">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-188">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="73e34-189">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="73e34-189">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="73e34-190">在**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="73e34-190">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="73e34-191">在**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="73e34-191">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e34-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73e34-192">See Also</span></span>  
 <span data-ttu-id="73e34-193">[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="73e34-193">[Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md) </span></span>  
 [<span data-ttu-id="73e34-194">将连接到 Oracle E-business Suite 使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="73e34-194">Connecting to Oracle E-Business Suite Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)