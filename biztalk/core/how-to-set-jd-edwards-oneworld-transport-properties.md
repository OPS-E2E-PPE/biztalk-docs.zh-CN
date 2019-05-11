---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2dbfa33f316dc48d696bdcb7f16b6506e918a9c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383927"
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a><span data-ttu-id="97141-101">如何设置 JD Edwards OneWorld 传输属性</span><span class="sxs-lookup"><span data-stu-id="97141-101">How to Set JD Edwards OneWorld Transport Properties</span></span>

## <a name="overview"></a><span data-ttu-id="97141-102">概述</span><span class="sxs-lookup"><span data-stu-id="97141-102">Overview</span></span>
<span data-ttu-id="97141-103">JD Edwards OneWorld 传输属性系统定义用于设计和运行时登录。</span><span class="sxs-lookup"><span data-stu-id="97141-103">The JD Edwards OneWorld Transport Property System Definition is used for design and run-time logon.</span></span> <span data-ttu-id="97141-104">设置这些凭据以在设计时浏览 JD Edwards OneWorld 业务函数，并在运行时进行调用。</span><span class="sxs-lookup"><span data-stu-id="97141-104">You set these credentials to browse JD Edwards OneWorld business functions at design time and make calls at run time.</span></span>  
  
 <span data-ttu-id="97141-105">在与 JD Edwards OneWorld 建立连接，则将参数传递给连接对象 （用户、 密码、 环境）。</span><span class="sxs-lookup"><span data-stu-id="97141-105">When a connection is made to JD Edwards OneWorld, parameters are passed to the connection object (User, Password, Environment).</span></span> <span data-ttu-id="97141-106">它会返回 JD Edwards OneWorld 应用程序业务函数的实例。</span><span class="sxs-lookup"><span data-stu-id="97141-106">It returns an instance of the JD Edwards OneWorld aApplication business function.</span></span> <span data-ttu-id="97141-107">通过企业/应用程序服务器和定义的服务在其侦听的 TCP/IP 端口的名称来进一步定义这些凭据。</span><span class="sxs-lookup"><span data-stu-id="97141-107">The credentials are further defined by the name of the enterprise/application server, and the defined TCP/IP port on which the service listens.</span></span>  
  
 <span data-ttu-id="97141-108">从名为 jdeinterop.ini 的文件中读取企业服务器名称和端口。</span><span class="sxs-lookup"><span data-stu-id="97141-108">The enterprise server name and port are read from a file that is named jdeinterop.ini.</span></span> <span data-ttu-id="97141-109">这些值必须是系统定义设置中的相同。</span><span class="sxs-lookup"><span data-stu-id="97141-109">These values must be the same as those that are in the System Definition settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97141-110">所有项目都均区分大小写。</span><span class="sxs-lookup"><span data-stu-id="97141-110">All entries are case sensitive.</span></span>  
  
## <a name="set-the-transport-properties"></a><span data-ttu-id="97141-111">设置传输属性</span><span class="sxs-lookup"><span data-stu-id="97141-111">Set the transport properties</span></span>  
 <span data-ttu-id="97141-112">在中**传输属性**对话框中，你设置特定于服务器系统和你尝试访问的对象的连接和凭据参数。</span><span class="sxs-lookup"><span data-stu-id="97141-112">In the **Transport Properties** dialog box, you set the connection and credential parameters that are specific to the server system and the objects you are trying to access.</span></span>  
  
1.  <span data-ttu-id="97141-113">提供凭据。</span><span class="sxs-lookup"><span data-stu-id="97141-113">Provide credentials.</span></span>  
  
     <span data-ttu-id="97141-114">您可以访问 JD Edwards OneWorld 系统使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="97141-114">You can access the JD Edwards OneWorld system using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="97141-115">登录凭据 （密码、 用户名）：如果使用此方法，请转到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="97141-115">Logon credentials (Password, User name): If you use this method, go to step 5.</span></span>  
  
    -   <span data-ttu-id="97141-116">单一登录。</span><span class="sxs-lookup"><span data-stu-id="97141-116">Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="97141-117">若要使用单一登录 (SSO)，选择**是**中**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="97141-117">To use Single Sign-On (SSO), select **Yes** in the **Use SSO**.</span></span>  
  
     <span data-ttu-id="97141-118">有关如何设置 SSO 的详细信息，请参阅[适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span><span class="sxs-lookup"><span data-stu-id="97141-118">For more information about how to set up SSO, see [Security in the adapter](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span></span>  
  
3.  <span data-ttu-id="97141-119">在列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="97141-119">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="97141-120">关联应用程序，由企业单一登录工具创建代表 JD Edwards OneWorld 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="97141-120">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as JD Edwards OneWorld.</span></span> <span data-ttu-id="97141-121">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="97141-121">Microsoft BizTalk Adapter for JD Edwards OneWorld uses the credentials of an application user.</span></span> <span data-ttu-id="97141-122">从指定的关联应用程序的服务器系统的 SSO 凭据数据库检索这些凭据。</span><span class="sxs-lookup"><span data-stu-id="97141-122">These credentials are retrieved from the SSO Credentials database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="97141-123">凭据是启动 BizTalk Server 项目的应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="97141-123">The credentials are those of the application user who launched the BizTalk Server project.</span></span>  
  
     <span data-ttu-id="97141-124">有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。</span><span class="sxs-lookup"><span data-stu-id="97141-124">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
4.  <span data-ttu-id="97141-125">展开**JD Edwards OneWorld 系统**节点并输入所需的所有信息以连接到 JD Edwards OneWorld 服务器。</span><span class="sxs-lookup"><span data-stu-id="97141-125">Expand the **JD Edwards OneWorld system** node and enter all required information for connection to the JD Edwards OneWorld server.</span></span>  
  
     <span data-ttu-id="97141-126">![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")</span><span class="sxs-lookup"><span data-stu-id="97141-126">![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")</span></span>  
  
     <span data-ttu-id="97141-127">设置连接参数后，您可以浏览 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="97141-127">After you set the connection parameters, you can browse a JD Edwards OneWorld system.</span></span> <span data-ttu-id="97141-128">有关详细信息，请参阅[导入到 BizTalk Server 项目 JD Edwards OneWorld 架构](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="97141-128">For more information, see [Importing JD Edwards OneWorld Schemas into BizTalk Server Projects](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).</span></span>  
  
5.  <span data-ttu-id="97141-129">输入一个值，表示在调用，例如 200 数**最大并发调用**如有必要。</span><span class="sxs-lookup"><span data-stu-id="97141-129">Enter a value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="97141-130">`Max Concurrent Calls`参数可以优化您的配置。</span><span class="sxs-lookup"><span data-stu-id="97141-130">The `Max Concurrent Calls` parameter lets you optimize your configuration.</span></span> <span data-ttu-id="97141-131">在吞吐量超过了后端处理能力，以激活消息重载保护中使用此参数。</span><span class="sxs-lookup"><span data-stu-id="97141-131">You use this parameter in instances where the throughput exceeds back-end processing capabilities, to activate message-overload protection.</span></span> <span data-ttu-id="97141-132">默认值为-1，表示不限制调用。</span><span class="sxs-lookup"><span data-stu-id="97141-132">The default is -1, which means that the calls are unlimited.</span></span>  
  
     <span data-ttu-id="97141-133">当 BizTalk Server 将消息提交到传输适配器时，它首先从适配器接收一批。</span><span class="sxs-lookup"><span data-stu-id="97141-133">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter.</span></span> <span data-ttu-id="97141-134">它将调用`TransmitMessage`对批，将每个消息传送。</span><span class="sxs-lookup"><span data-stu-id="97141-134">It invokes `TransmitMessage` on the batch to transmit each message.</span></span> <span data-ttu-id="97141-135">完成后，BizTalk Server 调用`Done`批处理，然后适配器开始将消息传输到后端上。</span><span class="sxs-lookup"><span data-stu-id="97141-135">When done, BizTalk Server invokes `Done` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="97141-136">如果 BizTalk Server 调用之前获取多个批次`Done`，可能永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="97141-136">If BizTalk Server obtains multiple batches before invoking `Done`, it might never occur.</span></span> <span data-ttu-id="97141-137">通过在批处理中设置的最大消息数，可以控制到后端的消息。</span><span class="sxs-lookup"><span data-stu-id="97141-137">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span>  
  
     <span data-ttu-id="97141-138">更改此参数在一分钟; 内将生效BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。</span><span class="sxs-lookup"><span data-stu-id="97141-138">Changing this parameter takes effect within one minute; BizTalk Server must retrieve the changes to the adapter configuration saved in the SQL database.</span></span>  
  
6.  <span data-ttu-id="97141-139">选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="97141-139">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="97141-140">例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。</span><span class="sxs-lookup"><span data-stu-id="97141-140">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97141-141">退出当前浏览会话之前不刷新 browsingagent.exe。</span><span class="sxs-lookup"><span data-stu-id="97141-141">The browsingagent.exe does not refresh until you exit the current browsing session.</span></span> <span data-ttu-id="97141-142">例如，你必须退出**生成的添加项**浏览会话并重新进入以便更新 browsingagent.exe。</span><span class="sxs-lookup"><span data-stu-id="97141-142">For example, you must exit the **Add generated item** browsing session and reenter to update the browsingagent.exe.</span></span>  
  
7.  <span data-ttu-id="97141-143">提供所需的所有信息后，单击**Apply**，然后单击**确定**接受连接信息。</span><span class="sxs-lookup"><span data-stu-id="97141-143">After providing all required information, click **Apply**, and then click **OK** to accept the connection information.</span></span>  
  
     <span data-ttu-id="97141-144">必须设置用于 JD Edwards OneWorld 访问 JD Edwards OneWorld 的 BizTalk 适配器的连接参数。</span><span class="sxs-lookup"><span data-stu-id="97141-144">You must set connection parameters for BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld.</span></span>  
  
## <a name="adapter-required-properties"></a><span data-ttu-id="97141-145">所需的适配器属性</span><span class="sxs-lookup"><span data-stu-id="97141-145">Adapter required properties</span></span>  
 <span data-ttu-id="97141-146">如果你未在控制面板中设置全局环境变量，就可以做到在本部分中。</span><span class="sxs-lookup"><span data-stu-id="97141-146">If you did not set global environment variables in Control Panel, you can do so in this section.</span></span>  
  
|<span data-ttu-id="97141-147">参数</span><span class="sxs-lookup"><span data-stu-id="97141-147">Parameter</span></span>|<span data-ttu-id="97141-148">Description</span><span class="sxs-lookup"><span data-stu-id="97141-148">Description</span></span>|  
|---------------|-----------------|  
|`Host`|<span data-ttu-id="97141-149">键入主机服务器计算机名称的名称 (例如， `actsvr1`); 或的计算机的 IP 地址 (例如， `123.456.0.789`)。</span><span class="sxs-lookup"><span data-stu-id="97141-149">Type the name of the host server computer name (for example, `actsvr1`); or the IP address of the computer (for example, `123.456.0.789`).</span></span>|  
|<span data-ttu-id="97141-150">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="97141-150">JAVA_HOME</span></span>|<span data-ttu-id="97141-151">键入 JDK 安装的完整路径。</span><span class="sxs-lookup"><span data-stu-id="97141-151">Type the complete path of your JDK installation.</span></span>|  
|<span data-ttu-id="97141-152">JDE Edwards 环境</span><span class="sxs-lookup"><span data-stu-id="97141-152">JDE Edwards Environment</span></span>|<span data-ttu-id="97141-153">例如，JD Edwards OneWorld 中键入环境名称`DV7333`。</span><span class="sxs-lookup"><span data-stu-id="97141-153">Type the name of an environment in JD Edwards OneWorld, for example, `DV7333`.</span></span><br /><br /> <span data-ttu-id="97141-154">DV7333 是开发环境的公用名，PY7333 是原型环境和 PD7333 是生产环境。</span><span class="sxs-lookup"><span data-stu-id="97141-154">DV7333 is a common name for the development environment, PY7333 is common for the prototype environment, and PD7333 is common for the production environment.</span></span>|  
|<span data-ttu-id="97141-155">JDEdwards JAR 文件</span><span class="sxs-lookup"><span data-stu-id="97141-155">JDEdwards JAR Files</span></span>|<span data-ttu-id="97141-156">输入每个 JAR 文件的完整路径和文件名称：</span><span class="sxs-lookup"><span data-stu-id="97141-156">Enter the complete path and file name for each JAR file:</span></span><br /><br /> <span data-ttu-id="97141-157">-   Connector.jar</span><span class="sxs-lookup"><span data-stu-id="97141-157">-   Connector.jar</span></span><br /><span data-ttu-id="97141-158">-   Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="97141-158">-   Kernel.jar</span></span><br /><span data-ttu-id="97141-159">-   JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="97141-159">-   JDEJAccess.jar</span></span><br /><span data-ttu-id="97141-160">-   JDEActionalInterop.jar</span><span class="sxs-lookup"><span data-stu-id="97141-160">-   JDEActionalInterop.jar</span></span><br /><br /> <span data-ttu-id="97141-161">必须用分号 （;） 和没有空格分隔每个 jar 文件。</span><span class="sxs-lookup"><span data-stu-id="97141-161">Each jar file must be separated with a semi-colon (;) and no space.</span></span> <span data-ttu-id="97141-162">例如：</span><span class="sxs-lookup"><span data-stu-id="97141-162">For example:</span></span><br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|<span data-ttu-id="97141-163">Password</span><span class="sxs-lookup"><span data-stu-id="97141-163">Password</span></span>|<span data-ttu-id="97141-164">键入指定用户的密码。</span><span class="sxs-lookup"><span data-stu-id="97141-164">Type the password of the specified user.</span></span>|  
|<span data-ttu-id="97141-165">Port</span><span class="sxs-lookup"><span data-stu-id="97141-165">Port</span></span>|<span data-ttu-id="97141-166">键入将要交换数据的端口号 (例如， `6009`)。</span><span class="sxs-lookup"><span data-stu-id="97141-166">Type the port number that will exchange data (for example, `6009`).</span></span>|  
|<span data-ttu-id="97141-167">用户名</span><span class="sxs-lookup"><span data-stu-id="97141-167">User Name</span></span>|<span data-ttu-id="97141-168">键入将用于登录到 JD Edwards OneWorld 系统的 JD Edwards OneWorld 用户名。</span><span class="sxs-lookup"><span data-stu-id="97141-168">Type a JD Edwards OneWorld user name that will be used to log on to the JD Edwards OneWorld system.</span></span>|  
  
