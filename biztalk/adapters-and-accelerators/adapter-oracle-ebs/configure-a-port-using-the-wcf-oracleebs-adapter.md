---
title: 配置端口在 BizTalk 中使用 WCF OracleEBS 适配器 |Microsoft 文档
description: 使用 WCF OracleEBS 适配器来接收或从 BizTalk Server 中的 Oracle EBS 发送消息
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4c5c10-79a6-48d3-b4ee-dddf837f020b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bebd38c72164da8e3a1a0e158232999b23b02fc0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218397"
---
# <a name="configure-a-port-using-the-wcf-oracleebs-adapter"></a><span data-ttu-id="0077c-103">配置使用 WCF OracleEBS 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="0077c-103">Configure a port using the WCF-OracleEBS adapter</span></span>
<span data-ttu-id="0077c-104">如何配置 WCF OracleEBS 发送和接收端口上 Oracle E-business Suite 使用执行出站和入站操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0077c-104">How to configure WCF-OracleEBS send and receive ports to perform outbound and inbound operations on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0077c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="0077c-105">Prerequisites</span></span>  
<span data-ttu-id="0077c-106">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="0077c-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="0077c-107">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0077c-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a><span data-ttu-id="0077c-108">部署适配器，以将消息发送到 Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="0077c-108">Deploy adapters to send messages to Oracle EBS</span></span> 
 <span data-ttu-id="0077c-109">执行以下步骤以配置 WCF OracleEBS 发送端口将消息发送到 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0077c-109">Perform the following steps to configure a WCF-OracleEBS send port for sending messages to Oracle E-Business Suite using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>    
 
1.  <span data-ttu-id="0077c-110">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0077c-110">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0077c-111">添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0077c-111">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0077c-112">[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)列出的步骤。</span><span class="sxs-lookup"><span data-stu-id="0077c-112">[Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md) lists the steps.</span></span>
  
3.  <span data-ttu-id="0077c-113">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0077c-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="0077c-114">展开你想要部署的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0077c-114">Expand the application under which you want to deploy the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
5.  <span data-ttu-id="0077c-115">右键单击**发送端口**，指向**新建**，然后指向你想要根据之间的通信模式配置的端口的类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="0077c-115">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Oracle E-Business Suite.</span></span>  
  
6.  <span data-ttu-id="0077c-116">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="0077c-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="0077c-117">从**类型**下拉列表中，选择 WCF OracleEBS，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0077c-117">From the **Type** drop-down list, select WCF-OracleEBS, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="0077c-118">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0077c-118">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0077c-119">单击**常规**选项卡上，单击**配置**按钮，然后提供的连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="0077c-119">Click the **General** tab, click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="0077c-120">有关连接 URI 的详细信息，请参阅[配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="0077c-120">For more information about the connection URI, see [Configure the Connection URI for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md).</span></span>  
  
    2.  <span data-ttu-id="0077c-121">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="0077c-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="0077c-122">请参阅[消息和 Oracle EBS 适配器的消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="0077c-122">See [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) for a list of actions for each operation.</span></span> <span data-ttu-id="0077c-123">例如，要调用该资产应用程序下接口表 (FA_BOOKS) 上的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="0077c-123">For example, the action to invoke the Insert operation on an interface table (FA_BOOKS) under the Asset application is:</span></span>  
  
        ```  
        InterfaceTables/Insert/OFA/FA/FA_BOOKS  
        ```  
  
    3.  <span data-ttu-id="0077c-124">单击**绑定**选项卡上，并指定为公开的绑定属性的值[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0077c-124">Click the **Binding** tab and specify values for the binding properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="0077c-125">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0077c-125">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0077c-126">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="0077c-126">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="0077c-127">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="0077c-127">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    4.  <span data-ttu-id="0077c-128">单击**凭据**选项卡，，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0077c-128">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="0077c-129">选择**不使用单一登录**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="0077c-129">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to Oracle E-Business Suite.</span></span>  
  
            |<span data-ttu-id="0077c-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0077c-130">Use this</span></span>|<span data-ttu-id="0077c-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0077c-131">To do this</span></span>|  
            |--------------|----------------|  
            |<span data-ttu-id="0077c-132">**使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-132">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="0077c-133">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0077c-133">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
            |<span data-ttu-id="0077c-134">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-134">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="0077c-135">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0077c-135">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="0077c-136">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0077c-136">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
            |<span data-ttu-id="0077c-137">**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-137">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="0077c-138">指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="0077c-138">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
            |<span data-ttu-id="0077c-139">**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-139">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="0077c-140">指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0077c-140">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="0077c-141">你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="0077c-141">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
        -   <span data-ttu-id="0077c-142">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0077c-142">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
    5.  <span data-ttu-id="0077c-143">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0077c-143">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="0077c-144">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="0077c-144">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="0077c-145">如果你选择了**静态单向发送端口**在步骤 5 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-145">If you chose **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="0077c-146">从**发送管道**列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-146">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="0077c-147">如果你选择了**静态请求-响应端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-147">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="0077c-148">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-148">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="0077c-149">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-149">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
12. <span data-ttu-id="0077c-150">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0077c-150">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a><span data-ttu-id="0077c-151">部署适配器从 Oracle EBS 接收消息</span><span class="sxs-lookup"><span data-stu-id="0077c-151">Deploy adapters to receive messages from Oracle EBS</span></span>  
 <span data-ttu-id="0077c-152">执行以下步骤来配置 WCF OracleEBS 接收端口来接收消息从 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0077c-152">Perform the following steps to configure a WCF-OracleEBS receive port for receiving messages from Oracle E-Business Suite using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="0077c-153">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0077c-153">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0077c-154">添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0077c-154">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0077c-155">有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="0077c-155">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="0077c-156">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0077c-156">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="0077c-157">展开你想要部署的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0077c-157">Expand the application under which you want to deploy the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
5.  <span data-ttu-id="0077c-158">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**，具体取决于模式之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="0077c-158">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Oracle E-Business Suite.</span></span>  
  
6.  <span data-ttu-id="0077c-159">在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="0077c-159">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7.  <span data-ttu-id="0077c-160">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="0077c-160">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="0077c-161">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="0077c-161">The **Receive Location Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="0077c-162">在**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0077c-162">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0077c-163">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="0077c-163">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="0077c-164">从**类型**下拉列表中，选择 WCF OracleEBS，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0077c-164">From the **Type** drop-down list, select WCF-OracleEBS, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="0077c-165">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0077c-165">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0077c-166">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="0077c-166">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="0077c-167">有关连接 URI 的详细信息，请参阅[配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="0077c-167">For more information about the connection URI, see [Configure the Connection URI for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md).</span></span>  
  
    2.  <span data-ttu-id="0077c-168">单击**绑定**选项卡上，并指定绑定以公开的属性的值[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0077c-168">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="0077c-169">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0077c-169">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0077c-170">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="0077c-170">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="0077c-171">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="0077c-171">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    3.  <span data-ttu-id="0077c-172">单击**行为**选项卡以设置事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="0077c-172">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="0077c-173">有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和与 Oracle E-business Suite 的事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="0077c-173">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).</span></span>  
  
    4.  <span data-ttu-id="0077c-174">单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0077c-174">Click the **Others** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="0077c-175">选择**用户帐户**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="0077c-175">Select **User account** option, and specify the user name and password to connect to Oracle E-Business Suite.</span></span>  
  
            |<span data-ttu-id="0077c-176">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0077c-176">Use this</span></span>|<span data-ttu-id="0077c-177">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0077c-177">To do this</span></span>|  
            |--------------|----------------|  
            |<span data-ttu-id="0077c-178">**使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-178">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="0077c-179">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0077c-179">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
            |<span data-ttu-id="0077c-180">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-180">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="0077c-181">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0077c-181">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="0077c-182">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0077c-182">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
            |<span data-ttu-id="0077c-183">**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-183">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="0077c-184">指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="0077c-184">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
            |<span data-ttu-id="0077c-185">**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="0077c-185">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="0077c-186">指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0077c-186">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="0077c-187">你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="0077c-187">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
        -   <span data-ttu-id="0077c-188">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0077c-188">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
    5.  <span data-ttu-id="0077c-189">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0077c-189">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="0077c-190">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="0077c-190">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="0077c-191">如果你选择了**单向接收端口**在步骤 5 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-191">If you chose **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="0077c-192">从**接收管道**列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-192">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="0077c-193">如果你选择了**请求响应接收端口**在步骤 5 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-193">If you chose **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="0077c-194">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-194">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="0077c-195">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="0077c-195">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="0077c-196">在**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0077c-196">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="0077c-197">在**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0077c-197">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0077c-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0077c-198">See Also</span></span>  
 <span data-ttu-id="0077c-199">[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0077c-199">[Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md) </span></span>  
 [<span data-ttu-id="0077c-200">将连接到 Oracle E-business Suite 使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="0077c-200">Connecting to Oracle E-Business Suite Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)