---
title: "执行博士 Edwards OneWorld 示例查询 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e15310442d12c0b2604eb0d22b071ff6c57212
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="723a8-102">执行博士 Edwards OneWorld 示例查询</span><span class="sxs-lookup"><span data-stu-id="723a8-102">Execute a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="723a8-103">可以使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 JD Edwards OneWorld (JDEOW) 系统。</span><span class="sxs-lookup"><span data-stu-id="723a8-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="723a8-104">此适配器是附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="723a8-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="723a8-105">这是 JD Edwards OneWorld 实验室工作的第二部分。</span><span class="sxs-lookup"><span data-stu-id="723a8-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="723a8-106">第一部分（实验室 1）中，你在没有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 协助或其他 Microsoft 技术的情况下，手动访问 JD Edwards OneWorld 系统上的数据。</span><span class="sxs-lookup"><span data-stu-id="723a8-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="723a8-107">在本部分（实验室 2）中，你将创建一个 BizTalk 业务流程作为 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="723a8-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="723a8-108">你将在此业务流程中配置端口，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。</span><span class="sxs-lookup"><span data-stu-id="723a8-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="723a8-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="723a8-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="723a8-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="723a8-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
-   <span data-ttu-id="723a8-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="723a8-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="723a8-112">JD Edwards OneWorld 客户端软件</span><span class="sxs-lookup"><span data-stu-id="723a8-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="723a8-113">与另一台服务器上的 JD Edwards OneWorld 系统的网络连接</span><span class="sxs-lookup"><span data-stu-id="723a8-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="723a8-114">Microsoft BizTalk Adapters for Enterprise Applications</span><span class="sxs-lookup"><span data-stu-id="723a8-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="723a8-115">请参阅[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)博士 Edwards、 PeopleSoft 和 TIBCO 适配器的密钥配置信息。</span><span class="sxs-lookup"><span data-stu-id="723a8-115">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="723a8-116">实验室 2 - 执行 JD Edwards OneWorld 示例查询</span><span class="sxs-lookup"><span data-stu-id="723a8-116">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="723a8-117">在本实验中，将执行**获取**针对博士 Edwards OneWorld 系统操作。</span><span class="sxs-lookup"><span data-stu-id="723a8-117">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-118">具体将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="723a8-118">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="723a8-119">验证博士 Edwards OneWorld 先决条件</span><span class="sxs-lookup"><span data-stu-id="723a8-119">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="723a8-120">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中设置 JD Edwards OneWorld 发送端口</span><span class="sxs-lookup"><span data-stu-id="723a8-120">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="723a8-121">创建一个 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="723a8-121">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="723a8-122">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="723a8-122">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="723a8-123">测试应用程序并查看 XML 输出</span><span class="sxs-lookup"><span data-stu-id="723a8-123">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="723a8-124">你将使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中访问 JD Edwards OneWorld 系统上的数据。</span><span class="sxs-lookup"><span data-stu-id="723a8-124">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="723a8-125">此适配器允许由业务流程执行的请求和响应来处理 JD Edwards OneWorld 对象。</span><span class="sxs-lookup"><span data-stu-id="723a8-125">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="723a8-126">许多方法可用于架构对象。</span><span class="sxs-lookup"><span data-stu-id="723a8-126">Many methods are available for a schema object.</span></span> <span data-ttu-id="723a8-127">此实验室将演示如何使用**地址簿图： MBF**方法。</span><span class="sxs-lookup"><span data-stu-id="723a8-127">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="723a8-128">在运行服务请求之前，必须为特定的 JD Edwards OneWorld 对象创建服务请求和响应架构。</span><span class="sxs-lookup"><span data-stu-id="723a8-128">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="723a8-129">通过直接询问 JD Edwards OneWorld 中支持的元数据对象，添加生成的项/添加适配器向导可以创建这些架构。</span><span class="sxs-lookup"><span data-stu-id="723a8-129">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="723a8-130">此实验室说明创建架构所需的步骤**地址簿图： MBF**方法并处理查询。</span><span class="sxs-lookup"><span data-stu-id="723a8-130">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="723a8-131">步骤 1： 验证博士 Edwards OneWorld 先决条件</span><span class="sxs-lookup"><span data-stu-id="723a8-131">Step 1: Verify the JD Edwards OneWorld prerequisites</span></span>  
 <span data-ttu-id="723a8-132">在开始创建 BizTalk 项目以便使用 JD Edwards OneWorld 适配器之前，你需要确保访问 JD Edwards OneWorld 系统所需的文件和适配器设置正确。</span><span class="sxs-lookup"><span data-stu-id="723a8-132">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-133">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，JD Edwards OneWorld 适配器通过 Java 接口与 JD Edwards OneWorld 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="723a8-133">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>    

1. <span data-ttu-id="723a8-134">四个文件所需的适当的接口访问使用博士 Edwards OneWorld 适配器博士 Edwards OneWorld 系统： Connector.jar、 Kernel.jar、 BTSLIBinterop.jar 和 JDEJAccess.jar。</span><span class="sxs-lookup"><span data-stu-id="723a8-134">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
    -   <span data-ttu-id="723a8-135">Connector.jar 和 Kernel.jar 文件随附了 JD Edwards OneWorld 系统，可以从 JD Edwards OneWorld 管理员获取。</span><span class="sxs-lookup"><span data-stu-id="723a8-135">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="723a8-136">这些文件在 C:\JDEOWJars 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="723a8-136">These files are located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="723a8-137">遵循适配器安装指南中附带的这些说明，BTSLIBinterop.jar 文件可由 JD Edwards OneWorld 系统生成。</span><span class="sxs-lookup"><span data-stu-id="723a8-137">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="723a8-138">此文件在 C:\JDEOWJars 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="723a8-138">This file is located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="723a8-139">JDEJAccess.jar 文件是 JDEOW 适配器的一部分，包含在该适配器的安装中。</span><span class="sxs-lookup"><span data-stu-id="723a8-139">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="723a8-140">默认情况下，它位于 C:\Program Files\Microsoft BizTalk 适配器对于企业 Applications\J.D。</span><span class="sxs-lookup"><span data-stu-id="723a8-140">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="723a8-141">Edwards OneWorld® \Classes 文件夹。</span><span class="sxs-lookup"><span data-stu-id="723a8-141">Edwards OneWorld®\Classes folder.</span></span>  
  
2. <span data-ttu-id="723a8-142">确认 Connector.jar，Kernel.jar，并且 BTSLIBinterop.jar 文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]C:\JDEOWJars 文件夹中的计算机。</span><span class="sxs-lookup"><span data-stu-id="723a8-142">Confirm the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
3. <span data-ttu-id="723a8-143">确认 JDEJAccess.jar 文件上是否存在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]企业 Applications\J.D 的 C:\Program Files\Microsoft BizTalk 适配器中的计算机。</span><span class="sxs-lookup"><span data-stu-id="723a8-143">Confirm the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="723a8-144">Edwards OneWorld\Classes 文件夹。</span><span class="sxs-lookup"><span data-stu-id="723a8-144">Edwards OneWorld\Classes folder.</span></span>  
  
## <a name="step-2-configure-biztalk-send-ports"></a><span data-ttu-id="723a8-145">步骤 2： 配置 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="723a8-145">Step 2: Configure BizTalk send ports</span></span>  
<span data-ttu-id="723a8-146">接下来，验证博士 Edwards OneWorld 适配器已安装，并且创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="723a8-146">Next, verify that the JD Edwards OneWorld adapter is installed, and create the send port.</span></span>  

1.  <span data-ttu-id="723a8-147">打开**BizTalk Server 管理**，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="723a8-147">Open **BizTalk Server Administration**, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
    <span data-ttu-id="723a8-148">确认**JDE_OneWorld**列出适配器。</span><span class="sxs-lookup"><span data-stu-id="723a8-148">Confirm the **JDE_OneWorld** adapter is listed.</span></span> <span data-ttu-id="723a8-149">如果没有安装 JD Edwards OneWorld 适配器，请安装企业应用程序的 BizTalk 适配器（请参阅前面的“先决条件”部分）。</span><span class="sxs-lookup"><span data-stu-id="723a8-149">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="723a8-150">安装适配器后，右键单击**适配器**，然后单击**新建-适配器**安装博士 Edwards OneWorld 适配器。</span><span class="sxs-lookup"><span data-stu-id="723a8-150">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="723a8-151">重新启动主机实例，这才会生效。</span><span class="sxs-lookup"><span data-stu-id="723a8-151">Restart the host instance for this to take effect.</span></span>  
  
2. <span data-ttu-id="723a8-152">展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="723a8-152">Expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="723a8-153">右键单击**发送端口**，单击**新建**，然后单击**静态请求-响应发送端口**。为这些字段中输入以下值：</span><span class="sxs-lookup"><span data-stu-id="723a8-153">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="723a8-154">**名称：**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="723a8-154">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="723a8-155">**类型：**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="723a8-155">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="723a8-156">**发送处理程序：**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="723a8-156">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="723a8-157">**发送管道：**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="723a8-157">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="723a8-158">**接收管道：**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="723a8-158">**Receive pipeline:**  `XMLReceive`</span></span>  
  
4.  <span data-ttu-id="723a8-159">单击“配置” ，然后输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-159">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="723a8-160">**主机：** \<输入你 JDEOW 的主机名\></span><span class="sxs-lookup"><span data-stu-id="723a8-160">**Host:** \<enter your JDEOW host name\></span></span>  
  
    2.  <span data-ttu-id="723a8-161">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="723a8-161">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="723a8-162">**JDEdwards 环境：** \<进入 JDEOW 环境\></span><span class="sxs-lookup"><span data-stu-id="723a8-162">**JDEdwards Environment:** \<enter your JDEOW environment\></span></span>  
  
    4.  <span data-ttu-id="723a8-163">**JDEdwards JAR 文件：** \<输入的 JAR 文件的完整路径\></span><span class="sxs-lookup"><span data-stu-id="723a8-163">**JDEdwards JAR files:** \<enter full path of JAR files\></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="723a8-164">**密码：**使用下拉列表，然后输入你博士 Edwards OneWorld 密码。</span><span class="sxs-lookup"><span data-stu-id="723a8-164">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="723a8-165">**端口：**  `6009`</span><span class="sxs-lookup"><span data-stu-id="723a8-165">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="723a8-166">**用户名：** \<输入博士 Edwards 用户名\></span><span class="sxs-lookup"><span data-stu-id="723a8-166">**User Name:** \<enter your JD Edwards User Name\></span></span>  
  
     <span data-ttu-id="723a8-167">![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")</span><span class="sxs-lookup"><span data-stu-id="723a8-167">![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")</span></span>  
  
5.  <span data-ttu-id="723a8-168">选择**确定**关闭**发送端口属性**。</span><span class="sxs-lookup"><span data-stu-id="723a8-168">Select **OK** to close the **Send Port Properties**.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="723a8-169">步骤 3： 创建 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="723a8-169">Step 3: Create a BizTalk Orchestration Project</span></span>  
<span data-ttu-id="723a8-170">接下来，创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，和项目中，以处理之间的通信配置业务流程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和博士 Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="723a8-170">Next, create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-171">你将添加发送端口和接收端口，生成项目，然后部署项目。</span><span class="sxs-lookup"><span data-stu-id="723a8-171">You will add send and receive ports, build the project, and then deploy the project.</span></span>  

  
1.  <span data-ttu-id="723a8-172">打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，并在 C:\LABS 文件夹中创建一个新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="723a8-172">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="723a8-173">在“文件”  菜单上，单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-173">On the **File** menu, click **New**.</span></span> <span data-ttu-id="723a8-174">此时将显示“新建项目”  对话框。</span><span class="sxs-lookup"><span data-stu-id="723a8-174">The **New Project** dialog box appears.</span></span> <span data-ttu-id="723a8-175">在“发送端口属性”  选择“空的 BizTalk Server 项目”。 </span><span class="sxs-lookup"><span data-stu-id="723a8-175">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="723a8-176">输入`JDE_OW_Test`作为唯一项目名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="723a8-176">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="723a8-177">在解决方案资源管理器中，右键单击该项目，单击“添加” ，然后单击“添加生成的项” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-177">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="723a8-178">在类别窗格中，选择**添加适配器元数据**，在模板窗格中，选择**添加适配器元数据**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="723a8-178">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="723a8-179">在添加适配器向导中，选择**博士 Edwards OneWorld**适配器，选择**JDE_OneWorldPort**发送在前面的过程中，创建的端口，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="723a8-179">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     <span data-ttu-id="723a8-180">![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")</span><span class="sxs-lookup"><span data-stu-id="723a8-180">![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")</span></span>  
  
4.  <span data-ttu-id="723a8-181">上**选择服务添加到导入**页上，打开**博士 Edwards OneWorld**。</span><span class="sxs-lookup"><span data-stu-id="723a8-181">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="723a8-182">JDEOW 系统使用 BrowsingAgent 程序通过适配器进行连接。</span><span class="sxs-lookup"><span data-stu-id="723a8-182">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="723a8-183">BrowsingAgent 返回以下服务。</span><span class="sxs-lookup"><span data-stu-id="723a8-183">The BrowsingAgent returns the following services.</span></span>  
  
     <span data-ttu-id="723a8-184">![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")</span><span class="sxs-lookup"><span data-stu-id="723a8-184">![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")</span></span>  
  
5.  <span data-ttu-id="723a8-185">展开**CALLBSFN**和向下滚动到**N0100041-地址簿图： MBF**。</span><span class="sxs-lookup"><span data-stu-id="723a8-185">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="723a8-186">选择 N0100041，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="723a8-186">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="723a8-187">在解决方案资源管理器中，会有一个新的 BizTalk 业务流程，包含两个新的相关架构文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-187">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="723a8-188">这些文件由添加适配器向导创建。</span><span class="sxs-lookup"><span data-stu-id="723a8-188">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="723a8-189">双击“BizTalk Orchestration.odx”文件以打开业务流程。 </span><span class="sxs-lookup"><span data-stu-id="723a8-189">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     <span data-ttu-id="723a8-190">![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")</span><span class="sxs-lookup"><span data-stu-id="723a8-190">![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")</span></span>  
  
 <span data-ttu-id="723a8-191">此业务流程接受已为 JD Edwards OneWorld 系统设置格式的 XML 文件作为文件适配器中的输入。</span><span class="sxs-lookup"><span data-stu-id="723a8-191">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-192">此业务流程使用 JD Edwards OneWorld 适配器将 XML 文件发送到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="723a8-192">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-193">JD Edwards OneWorld 处理查询并生成包含结果的输出 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-193">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="723a8-194">此 XML 文件通过 JD Edwards OneWorld 适配器返回到业务流程，并且文件适配器将 XML 文件写入磁盘上的输出位置。</span><span class="sxs-lookup"><span data-stu-id="723a8-194">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="723a8-195">要完成业务流程，你需要创建并配置用于接收和发送 XML 文件的端口。</span><span class="sxs-lookup"><span data-stu-id="723a8-195">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="723a8-196">首先，配置文件适配器所用的接收端口，以便从磁盘将包含查询的 XML 输入到业务流程。</span><span class="sxs-lookup"><span data-stu-id="723a8-196">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="723a8-197">配置要接受输入的 XML 文件的接收端口</span><span class="sxs-lookup"><span data-stu-id="723a8-197">Configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="723a8-198">双击“BizTalk Orchestration.odx”文件以打开业务流程。 </span><span class="sxs-lookup"><span data-stu-id="723a8-198">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="723a8-199">在 BizTalk Orchestration.odx 文件中，右键单击左的端口图面，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="723a8-199">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="723a8-200">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="723a8-200">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="723a8-201">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-201">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="723a8-202">上**端口属性**页上，输入`JDE_File_In`为**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="723a8-202">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="723a8-203">在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-203">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="723a8-204">**端口类型名称**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="723a8-204">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="723a8-205">**通信模式**： **单向**</span><span class="sxs-lookup"><span data-stu-id="723a8-205">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="723a8-206">**访问限制**： **内部 - 仅限于此项目**</span><span class="sxs-lookup"><span data-stu-id="723a8-206">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="723a8-207">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="723a8-207">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="723a8-208">**端口通信方向**： **始终在此端口上接收消息**</span><span class="sxs-lookup"><span data-stu-id="723a8-208">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="723a8-209">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="723a8-209">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="723a8-210">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-210">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="723a8-211">接下来，创建一个发送/接收端口，将包含查询的初始 XML 输入文件发送到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="723a8-211">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-212">此端口还接收 XML 输出文件，该文件包含来自对 JD Edwards OneWorld 系统调用的查询结果。</span><span class="sxs-lookup"><span data-stu-id="723a8-212">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="723a8-213">使用博士 Edwards OneWorld 配置到接口发送/接收端口</span><span class="sxs-lookup"><span data-stu-id="723a8-213">Configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="723a8-214">在 BizTalk Orchestration.odx 文件中，右键单击右侧端口图面，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="723a8-214">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="723a8-215">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="723a8-215">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="723a8-216">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-216">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="723a8-217">在“选择端口类型”  页上，选择“使用现有端口类型” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-217">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="723a8-218">下**可用端口类型**，选择**JD_OW_Test.N0100041**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="723a8-218">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     <span data-ttu-id="723a8-219">![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")</span><span class="sxs-lookup"><span data-stu-id="723a8-219">![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")</span></span>  
  
3.  <span data-ttu-id="723a8-220">选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-220">Select the following property values:</span></span>  
  
     <span data-ttu-id="723a8-221">**端口的通信的方向**:**我将发送请求并接收响应**</span><span class="sxs-lookup"><span data-stu-id="723a8-221">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="723a8-222">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="723a8-222">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="723a8-223">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-223">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="723a8-224">在端口图面上，你将看到端口和可用的方法。</span><span class="sxs-lookup"><span data-stu-id="723a8-224">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="723a8-225">最后，配置文件适配器要使用的发送端口，从而将包含查询结果的 XML 输出到磁盘。</span><span class="sxs-lookup"><span data-stu-id="723a8-225">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="723a8-226">配置要输出到磁盘的 XML 文件的发送端口</span><span class="sxs-lookup"><span data-stu-id="723a8-226">Configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="723a8-227">在 BizTalk Orchestration.odx 文件中，右键单击左的端口图面，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="723a8-227">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="723a8-228">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="723a8-228">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="723a8-229">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-229">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="723a8-230">上**端口属性**页上，输入`JDE_FileOut`为**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="723a8-230">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="723a8-231">在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-231">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="723a8-232">**端口类型名称**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="723a8-232">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="723a8-233">**通信模式**： **单向**</span><span class="sxs-lookup"><span data-stu-id="723a8-233">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="723a8-234">**访问限制**： **内部 - 仅限于此项目**</span><span class="sxs-lookup"><span data-stu-id="723a8-234">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="723a8-235">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="723a8-235">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="723a8-236">**端口通信方向**： **始终在此端口上发送消息**</span><span class="sxs-lookup"><span data-stu-id="723a8-236">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="723a8-237">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="723a8-237">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="723a8-238">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-238">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="723a8-239">端口图面上显示的是 JD Edwards OneWorld 服务的新端口和可用方法。</span><span class="sxs-lookup"><span data-stu-id="723a8-239">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="723a8-240">随后，你将指定 JD Edwards OneWorld 适配器，以发送和接收来自 JD Edwards OneWorld 系统的文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-240">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="723a8-241">**JDE_File_In**和**JDE_File_Out**你刚刚创建需要的端口相关联的消息类型。</span><span class="sxs-lookup"><span data-stu-id="723a8-241">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
#### <a name="assign-message-types-to-the-ports"></a><span data-ttu-id="723a8-242">将消息类型分配到的端口</span><span class="sxs-lookup"><span data-stu-id="723a8-242">Assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="723a8-243">在左的端口面上**JDE_File_In**端口，请单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="723a8-243">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="723a8-244">在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBF**。</span><span class="sxs-lookup"><span data-stu-id="723a8-244">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="723a8-245">在左的端口面上**JDE_File_Out**端口，请单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="723a8-245">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="723a8-246">在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBFResponse**。</span><span class="sxs-lookup"><span data-stu-id="723a8-246">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="723a8-247">插入两个**发送**形状和第二个**接收**用于链接到的端口到业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="723a8-247">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="723a8-248">添加发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="723a8-248">Add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="723a8-249">将工具箱中的“接收”  组件拖放到业务流程的起点（绿色圆圈）下。</span><span class="sxs-lookup"><span data-stu-id="723a8-249">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="723a8-250">单击**接收**形状，然后在属性窗口中，输入`Get_File`为**名称**，并设置**激活**到`true`。</span><span class="sxs-lookup"><span data-stu-id="723a8-250">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="723a8-251">执行此操作后，此接收端口上收到传入文档时将激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="723a8-251">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="723a8-252">拖动**发送**组件从工具箱拖放正下方**GetFileReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="723a8-252">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="723a8-253">单击新建**发送**形状，然后在属性窗口中，输入`SendToJDEOW`为**名称**。</span><span class="sxs-lookup"><span data-stu-id="723a8-253">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="723a8-254">拖动**接收**组件从工具箱拖放正下方**SendToJDEOWSend**形状。</span><span class="sxs-lookup"><span data-stu-id="723a8-254">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="723a8-255">单击**接收**形状，然后在属性窗口中，输入`JDEOW_Resp`为**名称**。</span><span class="sxs-lookup"><span data-stu-id="723a8-255">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="723a8-256">拖动**发送**组件从工具箱拖放正下方**JDEOW_RespReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="723a8-256">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="723a8-257">单击新建**发送**形状，然后在属性窗口中，输入`FileToDisk`为**名称**。</span><span class="sxs-lookup"><span data-stu-id="723a8-257">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     <span data-ttu-id="723a8-258">![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")</span><span class="sxs-lookup"><span data-stu-id="723a8-258">![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")</span></span>  
  
5.  <span data-ttu-id="723a8-259">连接**JDE_FileIn**端口到**GetFileReceive**组件。</span><span class="sxs-lookup"><span data-stu-id="723a8-259">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="723a8-260">连接**JDE_FileOut**端口到**FileToDiskReceive**组件。</span><span class="sxs-lookup"><span data-stu-id="723a8-260">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="723a8-261">转到**业务流程视图**展开**消息**。</span><span class="sxs-lookup"><span data-stu-id="723a8-261">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="723a8-262">更改的标识符**Message_1**到`MsgToJDEOW`，和**Message_2**到`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="723a8-262">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="723a8-263">突出显示**SendToJDEOWSend**组件，并且已设置其**消息**属性**MsgToJDEOW**。</span><span class="sxs-lookup"><span data-stu-id="723a8-263">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="723a8-264">突出显示**JDEOW_RespReceive**组件，并且已设置其**消息**属性**JDEOW_Resp**。</span><span class="sxs-lookup"><span data-stu-id="723a8-264">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="723a8-265">连接**SendToJDEOW**到**请求**部分**JDE_OW_Port**端口。</span><span class="sxs-lookup"><span data-stu-id="723a8-265">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="723a8-266">连接**JDEOW_Resp**到**响应**部分**JDE_OW_Port**端口。</span><span class="sxs-lookup"><span data-stu-id="723a8-266">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     <span data-ttu-id="723a8-267">![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")</span><span class="sxs-lookup"><span data-stu-id="723a8-267">![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")</span></span>  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="723a8-268">步骤 4： 生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="723a8-268">Step 4: Build and deploy the project</span></span>  
 <span data-ttu-id="723a8-269">现在，BizTalk 项目已完成，你可以生成项目并将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中。</span><span class="sxs-lookup"><span data-stu-id="723a8-269">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="723a8-270">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="723a8-270">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="723a8-271">要生成项目，你需要强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-271">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="723a8-272">在命令提示符下，输入以下内容以创建强名称密钥文件：</span><span class="sxs-lookup"><span data-stu-id="723a8-272">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="723a8-273">**sn-k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="723a8-273">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="723a8-274">在解决方案资源管理器，右键单击**JD_OW_Test**项目，，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="723a8-274">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="723a8-275">单击“签名”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="723a8-275">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="723a8-276">选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-276">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="723a8-277">浏览以选择密钥文件“labs.snk” ，然后单击“打开” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-277">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="723a8-278">单击项目设计器中的“部署”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="723a8-278">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="723a8-279">设置**应用程序名称**到`JDE_OW_Test`。</span><span class="sxs-lookup"><span data-stu-id="723a8-279">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="723a8-280">在解决方案资源管理器，右键单击**JDE_OW_Test**项目，，然后单击**生成。**</span><span class="sxs-lookup"><span data-stu-id="723a8-280">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     <span data-ttu-id="723a8-281">![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")</span><span class="sxs-lookup"><span data-stu-id="723a8-281">![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")</span></span>  
  
10. <span data-ttu-id="723a8-282">生成成功完成后，右键单击**XX_JD Edwards OneWorldQuery**项目，，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="723a8-282">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="723a8-283">在输出窗口中将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="723a8-283">In the output window the following output will be displayed:</span></span>  
  
     <span data-ttu-id="723a8-284">![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")</span><span class="sxs-lookup"><span data-stu-id="723a8-284">![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")</span></span>  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="723a8-285">步骤 5： 测试应用程序和查看 XML 输出</span><span class="sxs-lookup"><span data-stu-id="723a8-285">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="723a8-286">现在，你将测试你所创建和部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="723a8-286">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="723a8-287">你将创建用于启动业务流程进程的 XML 文件，然后将文件夹配置为接收和发送应用程序中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-287">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="723a8-288">配置应用程序之后，将运行该应用程序并查看业务流程返回的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-288">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="723a8-289">生成查询的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="723a8-289">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="723a8-290">在解决方案资源管理器中，双击**N0100041Service_N0100041.xsd**打开文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-290">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="723a8-291">右键单击**N0100041Service_N0100041.xsd** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="723a8-291">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="723a8-292">为“输出实例文件名”输入示例 XML 的  以下路径和文件名：</span><span class="sxs-lookup"><span data-stu-id="723a8-292">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="723a8-293">单击“确定” **。**</span><span class="sxs-lookup"><span data-stu-id="723a8-293">Click **OK.**</span></span> <span data-ttu-id="723a8-294">在属性窗口中，选择**\<架构\>**并设置**根引用：**到`AddressBookMasterMBF`。</span><span class="sxs-lookup"><span data-stu-id="723a8-294">In the Properties window, select **\<Schema\>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="723a8-295">这将导致生成的 XML，仅包含**查询**xml。</span><span class="sxs-lookup"><span data-stu-id="723a8-295">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     <span data-ttu-id="723a8-296">![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")</span><span class="sxs-lookup"><span data-stu-id="723a8-296">![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")</span></span>  
  
4.  <span data-ttu-id="723a8-297">右键单击**N0100041Service_N0100041.xsd** ，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="723a8-297">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="723a8-298">这将生成**Sample.xml**文件。</span><span class="sxs-lookup"><span data-stu-id="723a8-298">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="723a8-299">此文件将放入接收位置，作为适配器启动业务流程进程的输入。</span><span class="sxs-lookup"><span data-stu-id="723a8-299">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="723a8-300">配置和启动 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="723a8-300">Configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="723a8-301">配置用于接收传入文件和发送传出文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="723a8-301">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="723a8-302">转到**C:\LABS\JDE_OW_Test**并创建两个新的子文件夹名为`FileIn`和`FileOut`。</span><span class="sxs-lookup"><span data-stu-id="723a8-302">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="723a8-303">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="723a8-303">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="723a8-304">右键单击**JDE_OW_Test**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="723a8-304">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="723a8-305">![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")</span><span class="sxs-lookup"><span data-stu-id="723a8-305">![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")</span></span>  
  
4.  <span data-ttu-id="723a8-306">选择“Orchestration_1”  ，然后单击“主机”  下拉框。</span><span class="sxs-lookup"><span data-stu-id="723a8-306">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="723a8-307">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-307">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="723a8-308">下**接收端口**，单击**\<无\>**。</span><span class="sxs-lookup"><span data-stu-id="723a8-308">Under **Receive Ports**, click **\<None\>**.</span></span> <span data-ttu-id="723a8-309">在下拉列表中，选择“新建接收端口” 。</span><span class="sxs-lookup"><span data-stu-id="723a8-309">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="723a8-310">有关**名称**，类型`JDE_FileIn_Port`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="723a8-310">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="723a8-311">将出现一个消息框，表明你需要指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="723a8-311">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="723a8-312">单击“确定”，然后单击“新建”。  </span><span class="sxs-lookup"><span data-stu-id="723a8-312">Click **OK**, and then click **New**.</span></span>  
  
     <span data-ttu-id="723a8-313">![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")</span><span class="sxs-lookup"><span data-stu-id="723a8-313">![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")</span></span>  
  
7.  <span data-ttu-id="723a8-314">键入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-314">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="723a8-315">**名称**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="723a8-315">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="723a8-316">**类型**： **文件**</span><span class="sxs-lookup"><span data-stu-id="723a8-316">**Type**: **File**</span></span>  
  
     <span data-ttu-id="723a8-317">**接收处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="723a8-317">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="723a8-318">**接收管道**： **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="723a8-318">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     <span data-ttu-id="723a8-319">![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")</span><span class="sxs-lookup"><span data-stu-id="723a8-319">![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")</span></span>  
  
8.  <span data-ttu-id="723a8-320">单击**配置**，类型`C:\LABS\JDE_OW_Test\FileIn`为**接收文件夹**，然后单击**确定**三次。</span><span class="sxs-lookup"><span data-stu-id="723a8-320">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     <span data-ttu-id="723a8-321">![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")</span><span class="sxs-lookup"><span data-stu-id="723a8-321">![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")</span></span>  
  
9. <span data-ttu-id="723a8-322">单击**\<无\>**为**JDE_OW_Port**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="723a8-322">Click **\<None\>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="723a8-323">选择**新建发送端口**，然后选择或键入属性的以下值：</span><span class="sxs-lookup"><span data-stu-id="723a8-323">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="723a8-324">**名称**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="723a8-324">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="723a8-325">**类型**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="723a8-325">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="723a8-326">**发送处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="723a8-326">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="723a8-327">**管道**：“XMLTransmit”  和“XMLReceive” </span><span class="sxs-lookup"><span data-stu-id="723a8-327">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="723a8-328">单击“配置” ，然后输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-328">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="723a8-329">**主机：** \<输入你 JDEOW 的主机名\></span><span class="sxs-lookup"><span data-stu-id="723a8-329">**Host:** \<enter your JDEOW host name\></span></span>  
  
     <span data-ttu-id="723a8-330">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="723a8-330">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="723a8-331">**JDEdwards 环境：** \<进入 JDEOW 环境\></span><span class="sxs-lookup"><span data-stu-id="723a8-331">**JDEdwards Environment:** \<enter your JDEOW environment\></span></span>  
  
     <span data-ttu-id="723a8-332">**JDEdwards JAR 文件：**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="723a8-332">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="723a8-333">**密码：**使用下拉列表，然后输入你博士 Edwards OneWorld 密码。</span><span class="sxs-lookup"><span data-stu-id="723a8-333">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="723a8-334">**端口：**  `6009`</span><span class="sxs-lookup"><span data-stu-id="723a8-334">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="723a8-335">**用户名：**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="723a8-335">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     <span data-ttu-id="723a8-336">![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")</span><span class="sxs-lookup"><span data-stu-id="723a8-336">![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")</span></span>  
  
12. <span data-ttu-id="723a8-337">单击“确定”  两次以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="723a8-337">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="723a8-338">在配置 Applicationwindow 中，单击**\<无\>**为**JDE_FileOut**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="723a8-338">In the Configure Applicationwindow, click **\<None\>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="723a8-339">选择“新建发送端口”  ，然后键入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="723a8-339">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="723a8-340">**名称**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="723a8-340">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="723a8-341">**类型**： **文件**</span><span class="sxs-lookup"><span data-stu-id="723a8-341">**Type**: **File**</span></span>  
  
     <span data-ttu-id="723a8-342">**发送处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="723a8-342">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="723a8-343">**发送管道**： **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="723a8-343">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="723a8-344">单击**配置**和类型`C:\Labs\JDE_OW_Test\FileOut`为**目标文件夹。**</span><span class="sxs-lookup"><span data-stu-id="723a8-344">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="723a8-345">。为“文件名”保留“”，因为这会为每个消息生成唯一的文件。  ，  because this results in a unique file ， each message.</span><span class="sxs-lookup"><span data-stu-id="723a8-345">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     <span data-ttu-id="723a8-346">![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")</span><span class="sxs-lookup"><span data-stu-id="723a8-346">![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")</span></span>  
  
16. <span data-ttu-id="723a8-347">单击“确定”三次  以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="723a8-347">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="723a8-348">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**JDE_OW_Test**应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="723a8-348">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="723a8-349">测试业务流程</span><span class="sxs-lookup"><span data-stu-id="723a8-349">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="723a8-350">在**C:\Labs\JDE_OW_Test**目录**Sample.xml**文件将显示为：</span><span class="sxs-lookup"><span data-stu-id="723a8-350">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     <span data-ttu-id="723a8-351">![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")</span><span class="sxs-lookup"><span data-stu-id="723a8-351">![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")</span></span>  
  
2.  <span data-ttu-id="723a8-352">编辑**Sample.xml**文件，以删除以外的所有内容**cActionCode**和**mnAddressBookNumber**元素。</span><span class="sxs-lookup"><span data-stu-id="723a8-352">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     <span data-ttu-id="723a8-353">![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")</span><span class="sxs-lookup"><span data-stu-id="723a8-353">![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")</span></span>  
  
3.  <span data-ttu-id="723a8-354">有关**cActionCode**元素插入的字母`i`。</span><span class="sxs-lookup"><span data-stu-id="723a8-354">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="723a8-355">有关**mnAddressBookNumber**插入数`500`。</span><span class="sxs-lookup"><span data-stu-id="723a8-355">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="723a8-356">保存更改并将文件复制到**C:\Labs\JDE_OW_Test\FileIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="723a8-356">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="723a8-357">这是启动业务流程进程的接收位置。</span><span class="sxs-lookup"><span data-stu-id="723a8-357">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="723a8-358">在几秒钟，XML 文件应出现在**C:\Labs\JDE_OW_Test\FileOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="723a8-358">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="723a8-359">此文件应包含地址为 500 的所有记录。</span><span class="sxs-lookup"><span data-stu-id="723a8-359">This should contain the all the records where the address is 500.</span></span>  
  
     <span data-ttu-id="723a8-360">![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")</span><span class="sxs-lookup"><span data-stu-id="723a8-360">![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")</span></span>  
  
     <span data-ttu-id="723a8-361">此返回的记录数据应与匹配实验室 1 中为博士 Edwards OneWorld 系统的查询返回的数据。</span><span class="sxs-lookup"><span data-stu-id="723a8-361">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="723a8-362">通过比较实验室 1 中获得的记录，你可以验证**获取**方法正常运行。</span><span class="sxs-lookup"><span data-stu-id="723a8-362">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="723a8-363">摘要</span><span class="sxs-lookup"><span data-stu-id="723a8-363">Summary</span></span>  
 <span data-ttu-id="723a8-364">在本实验室中，你首先验证了访问 JD Edwards OneWorld 系统所需的先决条件是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="723a8-364">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-365">然后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建了包含业务流程的新 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="723a8-365">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="723a8-366">你将配置 BizTalk 业务流程，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。</span><span class="sxs-lookup"><span data-stu-id="723a8-366">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-367">为配置业务流程，你创建了发送端口、接收端口和发送/接收端口。</span><span class="sxs-lookup"><span data-stu-id="723a8-367">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="723a8-368">将这些端口绑定到 JD Edwards OneWorld 适配器，并将消息分配给相应的端口。</span><span class="sxs-lookup"><span data-stu-id="723a8-368">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="723a8-369">完成 BizTalk 项目后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 来生成和部署该项目。</span><span class="sxs-lookup"><span data-stu-id="723a8-369">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="723a8-370">随后，配置了新应用程序，运行该应用程序，并从 JD Edwards OneWorld 系统中获取数据。</span><span class="sxs-lookup"><span data-stu-id="723a8-370">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="723a8-371">要验证应用程序是否正常运行，你将其输出 XML 文件与实验室 1 中从 JD Edwards OneWorld 系统接收到的文件进行了比较。</span><span class="sxs-lookup"><span data-stu-id="723a8-371">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>