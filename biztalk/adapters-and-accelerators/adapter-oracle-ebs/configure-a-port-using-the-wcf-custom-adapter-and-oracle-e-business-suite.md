---
title: 配置端口在 BizTalk 中使用 WCF 自定义适配器和 Oracle E-business Suite |Microsoft Docs
description: 使用 WCF 自定义适配器接收或发送消息从 BizTalk Server 中的 Oracle EBS
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83d0bb00-934c-40cf-8833-354e7ce7e927
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0d8c27421b02e183d8e9f3e1f72363cfbe1bcf3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376009"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite"></a><span data-ttu-id="5de71-103">使用 WCF 自定义适配器和 Oracle E-business Suite 配置端口</span><span class="sxs-lookup"><span data-stu-id="5de71-103">Configure a port using the WCF-custom adapter and Oracle E-Business Suite</span></span>
<span data-ttu-id="5de71-104">如何配置 WCF 自定义发送和接收端口，以执行对 Oracle E-business Suite 使用出站和入站操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5de71-104">How to configure WCF-Custom send and receive ports to perform outbound and inbound operations on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5de71-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="5de71-105">Prerequisites</span></span>  
<span data-ttu-id="5de71-106">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。</span><span class="sxs-lookup"><span data-stu-id="5de71-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="5de71-107">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5de71-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a><span data-ttu-id="5de71-108">部署适配器将消息发送到 Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="5de71-108">Deploy adapters to send messages to Oracle EBS</span></span>  
 <span data-ttu-id="5de71-109">执行以下步骤来配置 Wcf-custom 发送端口将消息发送到 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5de71-109">Perform the following steps to configure a WCF-Custom send port for sending messages to Oracle E-Business Suite using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="5de71-110">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5de71-110">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="5de71-111">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5de71-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="5de71-112">展开你想要部署的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5de71-112">Expand the application under which you want to deploy the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
4. <span data-ttu-id="5de71-113">右键单击**发送端口**，依次指向**新建**，然后指向你想要根据之间的通信的模式配置的端口类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="5de71-113">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Oracle E-Business Suite.</span></span>  
  
5. <span data-ttu-id="5de71-114">在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5de71-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="5de71-115">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5de71-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7. <span data-ttu-id="5de71-116">在中**Wcf-custom 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5de71-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="5de71-117">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定用于 Oracle E-business Suite 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="5de71-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for Oracle E-Business Suite.</span></span> <span data-ttu-id="5de71-118">有关连接 URI 的详细信息，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="5de71-118">For more information about the connection URI, see [Create the Oracle E-Business Suite Connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="5de71-119">上**常规**选项卡上，在**操作**文字框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="5de71-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="5de71-120">请参阅[的消息和消息架构 Oracle EBS 适配器](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)) 有关的每个操作的操作列表。</span><span class="sxs-lookup"><span data-stu-id="5de71-120">See [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)) for a list of actions for each operation.</span></span> <span data-ttu-id="5de71-121">例如，要调用的资产应用程序下的接口表 (FA_BOOKS) 上的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="5de71-121">For example, the action to invoke the Insert operation on an interface table (FA_BOOKS) under the Asset application is:</span></span>  
  
      ```  
      InterfaceTables/Insert/OFA/FA/FA_BOOKS  
      ```  
  
   3. <span data-ttu-id="5de71-122">单击**绑定**选项卡上，并从**绑定类型**列表中，选择**oracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="5de71-122">Click the **Binding** tab, and from the **Binding Type** list, select **oracleEBSBinding**.</span></span> <span data-ttu-id="5de71-123">您可以指定不同的绑定属性公开的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5de71-123">You can specify the different binding properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="5de71-124">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5de71-124">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="5de71-125">单击**凭据**选项卡，然后再执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5de71-125">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
      -   <span data-ttu-id="5de71-126">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="5de71-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to Oracle E-Business Suite.</span></span>  
  
          |<span data-ttu-id="5de71-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5de71-127">Use this</span></span>|<span data-ttu-id="5de71-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5de71-128">To do this</span></span>|  
          |--------------|----------------|  
          |<span data-ttu-id="5de71-129">**若要使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-129">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="5de71-130">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="5de71-130">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
          |<span data-ttu-id="5de71-131">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-131">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="5de71-132">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="5de71-132">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="5de71-133">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5de71-133">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
          |<span data-ttu-id="5de71-134">**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-134">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="5de71-135">指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="5de71-135">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
          |<span data-ttu-id="5de71-136">**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-136">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="5de71-137">指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="5de71-137">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="5de71-138">您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="5de71-138">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
      -   <span data-ttu-id="5de71-139">选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5de71-139">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
   5. <span data-ttu-id="5de71-140">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5de71-140">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8. <span data-ttu-id="5de71-141">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="5de71-141">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="5de71-142">如果选择了**静态单向发送端口**在步骤 4 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-142">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="5de71-143">从**发送管道**列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-143">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="5de71-144">如果选择了**静态要求响应端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-144">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="5de71-145">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-145">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="5de71-146">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-146">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="5de71-147">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="5de71-147">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a><span data-ttu-id="5de71-148">部署适配器，以接收来自 Oracle EBS 的消息</span><span class="sxs-lookup"><span data-stu-id="5de71-148">Deploy adapters to receive messages from Oracle EBS</span></span> 
 <span data-ttu-id="5de71-149">执行以下步骤来配置 WCF 自定义接收端口用于接收来自 Oracle E-business Suite 使用消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5de71-149">Perform the following steps to configure a WCF-Custom receive port for receiving messages from Oracle E-Business Suite using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="5de71-150">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5de71-150">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="5de71-151">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5de71-151">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="5de71-152">展开你想要部署的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5de71-152">Expand the application under which you want to deploy the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
4. <span data-ttu-id="5de71-153">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**，具体取决于之间的通信模式[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="5de71-153">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Oracle E-Business Suite.</span></span>  
  
5. <span data-ttu-id="5de71-154">在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5de71-154">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="5de71-155">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="5de71-155">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="5de71-156">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="5de71-156">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="5de71-157">在中**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5de71-157">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="5de71-158">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="5de71-158">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="5de71-159">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5de71-159">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="5de71-160">在中**Wcf-custom 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5de71-160">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="5de71-161">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定用于 Oracle E-business Suite 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="5de71-161">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for Oracle E-Business Suite.</span></span> <span data-ttu-id="5de71-162">有关连接 URI 的详细信息，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="5de71-162">For more information about the connection URI, see [Create the Oracle E-Business Suite Connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="5de71-163">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**oracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="5de71-163">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleEBSBinding**.</span></span> <span data-ttu-id="5de71-164">您可以指定不同的绑定属性公开的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5de71-164">You can specify the different binding properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="5de71-165">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5de71-165">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
   3. <span data-ttu-id="5de71-166">单击**行为**选项卡以设置事务隔离级别。</span><span class="sxs-lookup"><span data-stu-id="5de71-166">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="5de71-167">有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和事务超时与电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="5de71-167">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).</span></span>  
  
   4. <span data-ttu-id="5de71-168">单击**他人**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5de71-168">Click the **Others** tab, and do one of the following:</span></span>  
  
      -   <span data-ttu-id="5de71-169">选择**用户帐户**选项，然后指定用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="5de71-169">Select **User account** option, and specify the user name and password to connect to Oracle E-Business Suite.</span></span>  
  
          |<span data-ttu-id="5de71-170">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5de71-170">Use this</span></span>|<span data-ttu-id="5de71-171">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5de71-171">To do this</span></span>|  
          |--------------|----------------|  
          |<span data-ttu-id="5de71-172">**若要使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-172">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="5de71-173">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="5de71-173">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
          |<span data-ttu-id="5de71-174">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-174">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="5de71-175">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="5de71-175">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="5de71-176">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5de71-176">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
          |<span data-ttu-id="5de71-177">**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-177">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="5de71-178">指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="5de71-178">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
          |<span data-ttu-id="5de71-179">**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="5de71-179">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="5de71-180">指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="5de71-180">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="5de71-181">您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="5de71-181">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
      -   <span data-ttu-id="5de71-182">选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5de71-182">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
   5. <span data-ttu-id="5de71-183">若要返回到**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5de71-183">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="5de71-184">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="5de71-184">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="5de71-185">如果选择了**单向接收端口**在步骤 4 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-185">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="5de71-186">从**接收管道**列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-186">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="5de71-187">如果选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-187">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="5de71-188">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-188">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="5de71-189">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="5de71-189">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="5de71-190">在中**接收位置属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5de71-190">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="5de71-191">在中**接收端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5de71-191">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de71-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="5de71-192">See Also</span></span>  
 <span data-ttu-id="5de71-193">[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5de71-193">[Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md) </span></span>  
 [<span data-ttu-id="5de71-194">将连接到 Oracle E-business Suite 使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="5de71-194">Connecting to Oracle E-Business Suite Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)