---
title: "如何设置博士 Edwards OneWorld 传输属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: 6d38088b-a496-414e-aae6-d28c5d6398b6
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7abac3b468b8c76b8214e400366144b39f1e2741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a><span data-ttu-id="33ae2-102">如何设置博士 Edwards OneWorld 传输属性</span><span class="sxs-lookup"><span data-stu-id="33ae2-102">How to Set JD Edwards OneWorld Transport Properties</span></span>
<span data-ttu-id="33ae2-103">JD Edwards OneWorld 传输属性系统定义用于设计和运行时登录。</span><span class="sxs-lookup"><span data-stu-id="33ae2-103">The JD Edwards OneWorld Transport Property System Definition is used for design and run-time logon.</span></span> <span data-ttu-id="33ae2-104">在设计时，将这些凭据设置为浏览 JD Edwards OneWorld 业务函数，并在运行时进行调用。</span><span class="sxs-lookup"><span data-stu-id="33ae2-104">You set these credentials to browse JD Edwards OneWorld business functions at design time and make calls at run time.</span></span>  
  
 <span data-ttu-id="33ae2-105">在建立与 JD Edwards OneWorld 的连接后，将参数传递给连接对象（用户、密码、环境）。</span><span class="sxs-lookup"><span data-stu-id="33ae2-105">When a connection is made to JD Edwards OneWorld, parameters are passed to the connection object (User, Password, Environment).</span></span> <span data-ttu-id="33ae2-106">它将返回 JD Edwards OneWorld 应用程序业务函数的一个实例。</span><span class="sxs-lookup"><span data-stu-id="33ae2-106">It returns an instance of the JD Edwards OneWorld aApplication business function.</span></span> <span data-ttu-id="33ae2-107">通过企业/应用程序服务器名称及服务侦听到的已定义的 TCP/IP 端口可进一步定义这些凭据。</span><span class="sxs-lookup"><span data-stu-id="33ae2-107">The credentials are further defined by the name of the enterprise/application server, and the defined TCP/IP port on which the service listens.</span></span>  
  
 <span data-ttu-id="33ae2-108">从名为 jdeinterop.ini 文件读取企业服务器名称和端口。</span><span class="sxs-lookup"><span data-stu-id="33ae2-108">The enterprise server name and port are read from a file that is named jdeinterop.ini.</span></span> <span data-ttu-id="33ae2-109">这些值必须是相同的系统定义设置中。</span><span class="sxs-lookup"><span data-stu-id="33ae2-109">These values must be the same as those that are in the System Definition settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33ae2-110">所有条目都要区分大小写。</span><span class="sxs-lookup"><span data-stu-id="33ae2-110">All entries are case sensitive.</span></span>  
  
## <a name="setting-properties"></a><span data-ttu-id="33ae2-111">设置属性</span><span class="sxs-lookup"><span data-stu-id="33ae2-111">Setting Properties</span></span>  
 <span data-ttu-id="33ae2-112">在**传输属性**对话框中，你可以设置特定于服务器系统和你尝试访问的对象的连接和凭据参数。</span><span class="sxs-lookup"><span data-stu-id="33ae2-112">In the **Transport Properties** dialog box, you set the connection and credential parameters that are specific to the server system and the objects you are trying to access.</span></span>  
  
 <span data-ttu-id="33ae2-113">此过程中的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="33ae2-113">The steps in this process are as follows:</span></span>  
  
#### <a name="to-set-transport-properties"></a><span data-ttu-id="33ae2-114">设置传输属性</span><span class="sxs-lookup"><span data-stu-id="33ae2-114">To set transport properties</span></span>  
  
1.  <span data-ttu-id="33ae2-115">提供凭据。</span><span class="sxs-lookup"><span data-stu-id="33ae2-115">Provide credentials.</span></span>  
  
     <span data-ttu-id="33ae2-116">您可以使用以下方法之一访问 JD Edwards OneWorld 系统：</span><span class="sxs-lookup"><span data-stu-id="33ae2-116">You can access the JD Edwards OneWorld system using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="33ae2-117">登录凭据 （密码、 用户名称）： 如果你使用此方法，请转到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="33ae2-117">Logon credentials (Password, User name): If you use this method, go to step 5.</span></span>  
  
    -   <span data-ttu-id="33ae2-118">单一登录。</span><span class="sxs-lookup"><span data-stu-id="33ae2-118">Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="33ae2-119">若要使用单一登录 (SSO)，选择**是**中**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="33ae2-119">To use Single Sign-On (SSO), select **Yes** in the **Use SSO**.</span></span>  
  
     <span data-ttu-id="33ae2-120">有关如何设置 SSO 的详细信息，请参阅[使用单一登录](../core/using-single-sign-on3.md)。</span><span class="sxs-lookup"><span data-stu-id="33ae2-120">For more information about how to set up SSO, see [Using Single Sign-On](../core/using-single-sign-on3.md).</span></span>  
  
3.  <span data-ttu-id="33ae2-121">在列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="33ae2-121">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="33ae2-122">企业单一登录工具创建的关联应用程序代表诸如 JD Edwards OneWorld 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="33ae2-122">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as JD Edwards OneWorld.</span></span> <span data-ttu-id="33ae2-123">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="33ae2-123">Microsoft BizTalk Adapter for JD Edwards OneWorld uses the credentials of an application user.</span></span> <span data-ttu-id="33ae2-124">这些凭据是从服务器系统的 SSO 凭据数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="33ae2-124">These credentials are retrieved from the SSO Credentials database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="33ae2-125">凭据是启动 BizTalk Server 项目的应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="33ae2-125">The credentials are those of the application user who launched the BizTalk Server project.</span></span>  
  
     <span data-ttu-id="33ae2-126">有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。</span><span class="sxs-lookup"><span data-stu-id="33ae2-126">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
4.  <span data-ttu-id="33ae2-127">展开**博士 Edwards OneWorld 系统**节点然后输入博士 Edwards OneWorld 服务器连接的所有必要的信息。</span><span class="sxs-lookup"><span data-stu-id="33ae2-127">Expand the **JD Edwards OneWorld system** node and enter all required information for connection to the JD Edwards OneWorld server.</span></span>  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     <span data-ttu-id="33ae2-128">设置连接参数后，您可以浏览 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="33ae2-128">After you set the connection parameters, you can browse a JD Edwards OneWorld system.</span></span> <span data-ttu-id="33ae2-129">有关详细信息，请参阅[导入到 BizTalk 服务器项目博士 Edwards OneWorld 架构](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="33ae2-129">For more information, see [Importing JD Edwards OneWorld Schemas into BizTalk Server Projects](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).</span></span>  
  
5.  <span data-ttu-id="33ae2-130">输入一个值，在表示的调用，例如 200、 数**最大并发调用**如有必要。</span><span class="sxs-lookup"><span data-stu-id="33ae2-130">Enter a value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="33ae2-131">`Max Concurrent Calls`参数可以优化你的配置。</span><span class="sxs-lookup"><span data-stu-id="33ae2-131">The `Max Concurrent Calls` parameter lets you optimize your configuration.</span></span> <span data-ttu-id="33ae2-132">在吞吐量超过了后端处理能力的情况下，可以使用此参数激活消息重载保护。</span><span class="sxs-lookup"><span data-stu-id="33ae2-132">You use this parameter in instances where the throughput exceeds back-end processing capabilities, to activate message-overload protection.</span></span> <span data-ttu-id="33ae2-133">默认值为 -1，表示调用不受限制。</span><span class="sxs-lookup"><span data-stu-id="33ae2-133">The default is -1, which means that the calls are unlimited.</span></span>  
  
     <span data-ttu-id="33ae2-134">在 BizTalk Server 将消息提交到传输适配器后，首先会从该适配器收到一个批。</span><span class="sxs-lookup"><span data-stu-id="33ae2-134">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter.</span></span> <span data-ttu-id="33ae2-135">它调用批上的 `TransmitMessage` 以传输每个消息。</span><span class="sxs-lookup"><span data-stu-id="33ae2-135">It invokes `TransmitMessage` on the batch to transmit each message.</span></span> <span data-ttu-id="33ae2-136">完成上述操作后，BizTalk Server 对批调用 `Done`，然后适配器开始将消息传输到后端。</span><span class="sxs-lookup"><span data-stu-id="33ae2-136">When done, BizTalk Server invokes `Done` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="33ae2-137">如果在调用 `Done` 前，BizTalk Server 获得了多个批，这可能就永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="33ae2-137">If BizTalk Server obtains multiple batches before invoking `Done`, it might never occur.</span></span> <span data-ttu-id="33ae2-138">通过设置批中的最大消息数量，可以控制传输到后端的消息。</span><span class="sxs-lookup"><span data-stu-id="33ae2-138">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span>  
  
     <span data-ttu-id="33ae2-139">更改此参数后，所做更改会在一分钟内生效；BizTalk Server 必须检索 SQL 数据库中保存的对适配器配置的更改。</span><span class="sxs-lookup"><span data-stu-id="33ae2-139">Changing this parameter takes effect within one minute; BizTalk Server must retrieve the changes to the adapter configuration saved in the SQL database.</span></span>  
  
6.  <span data-ttu-id="33ae2-140">选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。</span><span class="sxs-lookup"><span data-stu-id="33ae2-140">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="33ae2-141">例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。</span><span class="sxs-lookup"><span data-stu-id="33ae2-141">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33ae2-142">browsingagent.exe 在退出当前浏览会话之前不会进行刷新。</span><span class="sxs-lookup"><span data-stu-id="33ae2-142">The browsingagent.exe does not refresh until you exit the current browsing session.</span></span> <span data-ttu-id="33ae2-143">例如，你必须退出**生成的添加项**浏览会话并重新输入更新 browsingagent.exe。</span><span class="sxs-lookup"><span data-stu-id="33ae2-143">For example, you must exit the **Add generated item** browsing session and reenter to update the browsingagent.exe.</span></span>  
  
7.  <span data-ttu-id="33ae2-144">提供所有所需的信息后，单击**应用**，然后单击**确定**接受连接信息。</span><span class="sxs-lookup"><span data-stu-id="33ae2-144">After providing all required information, click **Apply**, and then click **OK** to accept the connection information.</span></span>  
  
     <span data-ttu-id="33ae2-145">您必须为用于 JD Edwards OneWorld 的 BizTalk 适配器设置连接参数才能访问 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="33ae2-145">You must set connection parameters for BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld.</span></span>  
  
### <a name="adapter-required-properties"></a><span data-ttu-id="33ae2-146">适配器所需的属性</span><span class="sxs-lookup"><span data-stu-id="33ae2-146">Adapter Required Properties</span></span>  
 <span data-ttu-id="33ae2-147">如果没有在控制面板中设置全局环境变量，则可以在此部分中执行这项工作。</span><span class="sxs-lookup"><span data-stu-id="33ae2-147">If you did not set global environment variables in Control Panel, you can do so in this section.</span></span>  
  
|<span data-ttu-id="33ae2-148">参数</span><span class="sxs-lookup"><span data-stu-id="33ae2-148">Parameter</span></span>|<span data-ttu-id="33ae2-149">Description</span><span class="sxs-lookup"><span data-stu-id="33ae2-149">Description</span></span>|  
|---------------|-----------------|  
|`Host`|<span data-ttu-id="33ae2-150">键入主机服务器计算机名称的名称 (例如， `actsvr1`); 或计算机的 IP 地址 (例如， `123.456.0.789`)。</span><span class="sxs-lookup"><span data-stu-id="33ae2-150">Type the name of the host server computer name (for example, `actsvr1`); or the IP address of the computer (for example, `123.456.0.789`).</span></span>|  
|<span data-ttu-id="33ae2-151">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="33ae2-151">JAVA_HOME</span></span>|<span data-ttu-id="33ae2-152">键入 JDK 安装的完整路径。</span><span class="sxs-lookup"><span data-stu-id="33ae2-152">Type the complete path of your JDK installation.</span></span>|  
|<span data-ttu-id="33ae2-153">JDE Edwards 环境</span><span class="sxs-lookup"><span data-stu-id="33ae2-153">JDE Edwards Environment</span></span>|<span data-ttu-id="33ae2-154">例如，键入博士 Edwards OneWorld 环境的名称`DV7333`。</span><span class="sxs-lookup"><span data-stu-id="33ae2-154">Type the name of an environment in JD Edwards OneWorld, for example, `DV7333`.</span></span><br /><br /> <span data-ttu-id="33ae2-155">DV7333 是开发环境的公用名，PY7333 是原型环境的公用名，PD7333 是生产环境的公用名。</span><span class="sxs-lookup"><span data-stu-id="33ae2-155">DV7333 is a common name for the development environment, PY7333 is common for the prototype environment, and PD7333 is common for the production environment.</span></span>|  
|<span data-ttu-id="33ae2-156">JDEdwards JAR 文件</span><span class="sxs-lookup"><span data-stu-id="33ae2-156">JDEdwards JAR Files</span></span>|<span data-ttu-id="33ae2-157">输入每个 JAR 文件的完整路径和文件名称：</span><span class="sxs-lookup"><span data-stu-id="33ae2-157">Enter the complete path and file name for each JAR file:</span></span><br /><br /> <span data-ttu-id="33ae2-158">-Connector.jar</span><span class="sxs-lookup"><span data-stu-id="33ae2-158">-   Connector.jar</span></span><br /><span data-ttu-id="33ae2-159">-Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="33ae2-159">-   Kernel.jar</span></span><br /><span data-ttu-id="33ae2-160">-JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="33ae2-160">-   JDEJAccess.jar</span></span><br /><span data-ttu-id="33ae2-161">-JDEActionalInterop.jar</span><span class="sxs-lookup"><span data-stu-id="33ae2-161">-   JDEActionalInterop.jar</span></span><br /><br /> <span data-ttu-id="33ae2-162">每个 jar 文件必须用分号 (;) 分隔，中间不留空格。</span><span class="sxs-lookup"><span data-stu-id="33ae2-162">Each jar file must be separated with a semi-colon (;) and no space.</span></span> <span data-ttu-id="33ae2-163">例如：</span><span class="sxs-lookup"><span data-stu-id="33ae2-163">For example:</span></span><br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|<span data-ttu-id="33ae2-164">密码</span><span class="sxs-lookup"><span data-stu-id="33ae2-164">Password</span></span>|<span data-ttu-id="33ae2-165">键入指定用户的密码。</span><span class="sxs-lookup"><span data-stu-id="33ae2-165">Type the password of the specified user.</span></span>|  
|<span data-ttu-id="33ae2-166">端口</span><span class="sxs-lookup"><span data-stu-id="33ae2-166">Port</span></span>|<span data-ttu-id="33ae2-167">键入将交换数据的端口号 (例如， `6009`)。</span><span class="sxs-lookup"><span data-stu-id="33ae2-167">Type the port number that will exchange data (for example, `6009`).</span></span>|  
|<span data-ttu-id="33ae2-168">用户名</span><span class="sxs-lookup"><span data-stu-id="33ae2-168">User Name</span></span>|<span data-ttu-id="33ae2-169">键入将用于登录 JD Edwards OneWorld 系统的 JD Edwards OneWorld 用户名。</span><span class="sxs-lookup"><span data-stu-id="33ae2-169">Type a JD Edwards OneWorld user name that will be used to log on to the JD Edwards OneWorld system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33ae2-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33ae2-170">See Also</span></span>  
 [<span data-ttu-id="33ae2-171">创建博士 Edwards OneWorld 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="33ae2-171">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)