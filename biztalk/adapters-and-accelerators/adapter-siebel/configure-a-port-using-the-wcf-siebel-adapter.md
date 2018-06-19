---
title: 配置端口使用 WCF Siebel 适配器 |Microsoft 文档
description: 创建要在 BizTalk Server 中使用 Siebel eBusiness 应用程序适配器的 WCF Siebel 发送端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6314104-c742-440c-b530-b5a82295353a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486e33b6c8f61a315548a84f145dc45824300710
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222437"
---
# <a name="configure-a-port-using-the-wcf-siebel-adapter"></a><span data-ttu-id="fed4e-103">配置使用 WCF Siebel 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="fed4e-103">Configure a port using the WCF-Siebel adapter</span></span>
<span data-ttu-id="fed4e-104">如何配置 WCF Siebel 发送端口，以执行 Siebel 系统使用的出站操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fed4e-104">How to configure WCF-Siebel send ports to perform outbound operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fed4e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="fed4e-105">Prerequisites</span></span>  
<span data-ttu-id="fed4e-106">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="fed4e-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="fed4e-107">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fed4e-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-for-sending-messages-to-a-siebel-system"></a><span data-ttu-id="fed4e-108">部署用于将消息发送到 Siebel 系统的适配器</span><span class="sxs-lookup"><span data-stu-id="fed4e-108">Deploy adapters for sending messages to a Siebel system</span></span>  
 <span data-ttu-id="fed4e-109">执行以下步骤以配置 WCF Siebel 发送端口将消息发送到 Siebel 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fed4e-109">Perform the following steps to configure a WCF-Siebel send port for sending messages to a Siebel system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="fed4e-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fed4e-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="fed4e-111">添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fed4e-111">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="fed4e-112">有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="fed4e-112">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="fed4e-113">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="fed4e-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="fed4e-114">展开你想要部署的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fed4e-114">Expand the application under which you wish to deploy the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
5.  <span data-ttu-id="fed4e-115">右键单击**发送端口**，指向**新建**，并指向你想要配置具体取决于 BizTalk Server 和 Siebel 系统之间的通信模式的端口的类型。</span><span class="sxs-lookup"><span data-stu-id="fed4e-115">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the Siebel system.</span></span>  
  
6.  <span data-ttu-id="fed4e-116">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="fed4e-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="fed4e-117">从**类型**下拉列表中，选择 WCF Siebel 适配器前面添加和单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fed4e-117">From the **Type** drop-down list, select the WCF-Siebel adapter you added earlier and click **Configure**.</span></span>  
  
8.  <span data-ttu-id="fed4e-118">在传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fed4e-118">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="fed4e-119">单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。</span><span class="sxs-lookup"><span data-stu-id="fed4e-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="fed4e-120">有关连接 URI 的详细信息，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="fed4e-120">For more information about the connection URI, see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="fed4e-121">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="fed4e-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="fed4e-122">请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="fed4e-122">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span> <span data-ttu-id="fed4e-123">例如，要调用帐户在业务组件上的插入操作的操作是：</span><span class="sxs-lookup"><span data-stu-id="fed4e-123">For example, the action to invoke the Insert operation on the Account business component is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    3.  <span data-ttu-id="fed4e-124">单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="fed4e-124">Click the **Binding** tab and specify values for the binding properties.</span></span> <span data-ttu-id="fed4e-125">有关详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fed4e-125">For more information, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="fed4e-126">单击**凭据**选项卡，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fed4e-126">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="fed4e-127">选择**不使用单一登录**选项，并指定用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="fed4e-127">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
        -   <span data-ttu-id="fed4e-128">选择**使用单一登录**选项，然后指定关联 ESSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fed4e-128">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
         <span data-ttu-id="fed4e-129">有关与 BizTalk Server 安全性的详细信息，请参阅[Siebel 适配器和 BizTalk Server 使用的安全](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="fed4e-129">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="fed4e-130">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fed4e-130">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="fed4e-131">从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="fed4e-131">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="fed4e-132">如果你在步骤 5 中选择静态单向发送端口，指定发送管道。</span><span class="sxs-lookup"><span data-stu-id="fed4e-132">If you chose Static One-Way Send Port in step 5, specify a send pipeline.</span></span> <span data-ttu-id="fed4e-133">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="fed4e-133">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="fed4e-134">如果你在步骤 5 中选择静态请求-响应端口，指定发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="fed4e-134">If you chose Static Solicit-Response Port in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="fed4e-135">从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="fed4e-135">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="fed4e-136">从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="fed4e-136">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="fed4e-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fed4e-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed4e-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fed4e-138">See Also</span></span>  
[<span data-ttu-id="fed4e-139">手动配置到 Siebel 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="fed4e-139">Manually configure a physical port binding to the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)