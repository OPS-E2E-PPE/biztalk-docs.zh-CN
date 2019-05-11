---
title: 在 BizTalk 中使用 WCF-SAP 适配器配置端口 |Microsoft Docs
description: 创建用于发送或接收来自 SAP 使用 mySAP 适配器的 BizTalk 适配器包 (BAP) 中的消息的 WCF SAP 端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 420683f8-2516-4c65-895d-fe535824d450
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e9d701851183e4c328317479d23951118b223d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373859"
---
# <a name="configure-a-port-using-the-wcf-sap-adapter"></a><span data-ttu-id="7b58e-103">使用 WCF-SAP 适配器配置端口</span><span class="sxs-lookup"><span data-stu-id="7b58e-103">Configure a port using the WCF-SAP adapter</span></span>
<span data-ttu-id="7b58e-104">本主题提供有关如何配置 WCF SAP 说明发送和接收端口执行 SAP 系统使用的出站和入站操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b58e-104">This topic provides instructions on how to configure WCF-SAP send and receive ports to perform outbound and inbound operations on SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7b58e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="7b58e-105">Prerequisites</span></span>  
<span data-ttu-id="7b58e-106">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。</span><span class="sxs-lookup"><span data-stu-id="7b58e-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="7b58e-107">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a><span data-ttu-id="7b58e-108">部署适配器将消息发送到 SAP</span><span class="sxs-lookup"><span data-stu-id="7b58e-108">Deploy adapters to send messages to SAP</span></span>  
<span data-ttu-id="7b58e-109">完成以下步骤以配置 WCF SAP 发送端口将消息发送到 SAP 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7b58e-109">Complete the following steps to configure a WCF-SAP send port for sending messages to SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="7b58e-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7b58e-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="7b58e-111">添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7b58e-111">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7b58e-112">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-112">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="7b58e-113">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="7b58e-114">展开你想要部署的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b58e-114">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
5. <span data-ttu-id="7b58e-115">右键单击**发送端口**，依次指向**新建**，并指向你想要根据 BizTalk Server 和 SAP 系统之间的通信的模式配置的端口的类型。</span><span class="sxs-lookup"><span data-stu-id="7b58e-115">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
6. <span data-ttu-id="7b58e-116">在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="7b58e-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7. <span data-ttu-id="7b58e-117">从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-117">From the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="7b58e-118">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b58e-118">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="7b58e-119">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="7b58e-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="7b58e-120">有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-120">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="7b58e-121">上**常规**选项卡上，在**操作**文字框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="7b58e-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="7b58e-122">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="7b58e-122">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) for a list of actions for each operation.</span></span> <span data-ttu-id="7b58e-123">例如，若要调用 RFC_CUSTOMER_GET 则操作将是：</span><span class="sxs-lookup"><span data-stu-id="7b58e-123">For example, the action to invoke the RFC_CUSTOMER_GET would be:</span></span>  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. <span data-ttu-id="7b58e-124">单击**绑定**选项卡，指定的绑定公开的属性值[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b58e-124">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7b58e-125">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-125">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="7b58e-126">绑定属性将显示根据配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="7b58e-126">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="7b58e-127">例如，绑定属性与入站操作不可用时配置的发送端口，因为的入站的操作需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="7b58e-127">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
   4. <span data-ttu-id="7b58e-128">单击**凭据**选项卡上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7b58e-128">Click the **Credentials** tab and do one of the following:</span></span>  
  
   -   <span data-ttu-id="7b58e-129">选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="7b58e-129">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
   -   <span data-ttu-id="7b58e-130">选择**使用单一登录**选项，并指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b58e-130">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
        <span data-ttu-id="7b58e-131">有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-131">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
        <span data-ttu-id="7b58e-132">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-132">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="7b58e-133">从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-133">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="7b58e-134">如果您选择创建**静态单向发送端口**在步骤 5 中，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-134">If you chose to create a **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="7b58e-135">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-135">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="7b58e-136">如果您选择创建**静态要求响应端口**在步骤 5 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-136">If you chose to create a **Static Solicit-Response Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="7b58e-137">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-137">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="7b58e-138">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-138">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="7b58e-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="7b58e-139">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a><span data-ttu-id="7b58e-140">部署适配器从 SAP 接收消息</span><span class="sxs-lookup"><span data-stu-id="7b58e-140">Deploy adapters to receive messages from SAP</span></span>  
<span data-ttu-id="7b58e-141">完成以下步骤以配置 WCF SAP 接收端口用于接收来自 SAP 系统使用消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7b58e-141">Complete the following steps to configure a WCF-SAP receive port for receiving messages from SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="7b58e-142">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7b58e-142">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="7b58e-143">添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7b58e-143">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7b58e-144">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-144">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="7b58e-145">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-145">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="7b58e-146">展开你想要部署的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b58e-146">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
5. <span data-ttu-id="7b58e-147">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**具体取决于BizTalk Server 和 SAP 系统之间的通信模式。</span><span class="sxs-lookup"><span data-stu-id="7b58e-147">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port** depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
6. <span data-ttu-id="7b58e-148">在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="7b58e-148">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7. <span data-ttu-id="7b58e-149">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-149">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="7b58e-150">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="7b58e-150">The **Receive Location Properties** dialog box appears.</span></span>  
  
8. <span data-ttu-id="7b58e-151">在中**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b58e-151">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="7b58e-152">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="7b58e-152">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="7b58e-153">从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-153">From the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="7b58e-154">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b58e-154">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="7b58e-155">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="7b58e-155">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="7b58e-156">有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-156">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="7b58e-157">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-157">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="7b58e-158">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-158">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="7b58e-159">绑定属性将显示根据配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="7b58e-159">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="7b58e-160">例如，绑定属性与入站操作不可用时配置的发送端口，因为的入站的操作需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="7b58e-160">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
   3. <span data-ttu-id="7b58e-161">单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7b58e-161">Click the **Other** tab, and do one of the following:</span></span>  
  
   4. <span data-ttu-id="7b58e-162">选择**用户帐户**，并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="7b58e-162">Select **User account**, and specify the user name and password to connect to an SAP system.</span></span>  
  
   5. <span data-ttu-id="7b58e-163">选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b58e-163">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
       <span data-ttu-id="7b58e-164">有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7b58e-164">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
       <span data-ttu-id="7b58e-165">单击**确定**回到**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="7b58e-165">Click **OK** to return to the **Receive Location Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="7b58e-166">从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="7b58e-166">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="7b58e-167">如果您选择创建**单向接收端口**在步骤 5 中，指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-167">If you chose to create **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="7b58e-168">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-168">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="7b58e-169">如果您选择创建**请求响应接收端口**在步骤 5 中，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-169">If you chose to create **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="7b58e-170">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-170">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="7b58e-171">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="7b58e-171">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="7b58e-172">单击**确定**中**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="7b58e-172">Click **OK** in the **Receive Location Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="7b58e-173">单击**确定**中**接收端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="7b58e-173">Click **OK** in the **Receive Port Properties** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b58e-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b58e-174">See also</span></span>
[<span data-ttu-id="7b58e-175">手动配置到 SAP 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="7b58e-175">Manually configure a physical port binding to the SAP adapter</span></span>](manually-configure-a-physical-port-binding-to-the-sap-adapter.md)