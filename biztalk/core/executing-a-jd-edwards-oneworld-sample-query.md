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
ms.openlocfilehash: 35d05dfe719a9b199d7422f99ef80e888126f01f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="ae6b0-102">执行 JD Edwards OneWorld 示例查询</span><span class="sxs-lookup"><span data-stu-id="ae6b0-102">Executing a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="ae6b0-103">可以使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 JD Edwards OneWorld (JDEOW) 系统。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="ae6b0-104">此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 配合使用的一组八个业务线 (LOB) 适配器之一。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
 <span data-ttu-id="ae6b0-105">这是 JD Edwards OneWorld 实验室工作的第二部分。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="ae6b0-106">第一部分（实验室 1）中，你在没有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 协助或其他 Microsoft 技术的情况下，手动访问 JD Edwards OneWorld 系统上的数据。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="ae6b0-107">在本部分（实验室 2）中，你将创建一个 BizTalk 业务流程作为 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="ae6b0-108">你将在此业务流程中配置端口，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ae6b0-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="ae6b0-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="ae6b0-110">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae6b0-110">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   <span data-ttu-id="ae6b0-111">Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae6b0-111">Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]</span></span>  
  
-   <span data-ttu-id="ae6b0-112">JD Edwards OneWorld 客户端软件</span><span class="sxs-lookup"><span data-stu-id="ae6b0-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="ae6b0-113">与另一台服务器上的 JD Edwards OneWorld 系统的网络连接</span><span class="sxs-lookup"><span data-stu-id="ae6b0-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="ae6b0-114">Microsoft BizTalk Adapters for Enterprise Applications</span><span class="sxs-lookup"><span data-stu-id="ae6b0-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae6b0-115">有关安装和配置 Microsoft BizTalk 适配器为企业应用程序的信息，请参阅[超链接"http://go.microsoft.com/fwlink/?LinkId=196039"\t"_blank"http://go.microsoft.com/fwlink/?LinkId=196039](http://go.microsoft.com/fwlink/?LinkId=196039)。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-115">For information about installing and configuring Microsoft BizTalk Adapters for Enterprise Applications, see [HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=196039" \t "_blank" http://go.microsoft.com/fwlink/?LinkId=196039](http://go.microsoft.com/fwlink/?LinkId=196039).</span></span> <span data-ttu-id="ae6b0-116">本文档包含 JD Edwards、PeopleSoft、JD Edwards OneWorld、TIBCO 和 Siebel LOB 适配器的重要配置信息。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-116">This document includes key configuration information for the JD Edwards, PeopleSoft, JD Edwards OneWorld, TIBCO, and Siebel LOB adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="ae6b0-117">实验室 2 - 执行 JD Edwards OneWorld 示例查询</span><span class="sxs-lookup"><span data-stu-id="ae6b0-117">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="ae6b0-118">在本实验中，将执行**获取**针对博士 Edwards OneWorld 系统操作。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-118">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-119">具体将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-119">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ae6b0-120">验证博士 Edwards OneWorld 先决条件</span><span class="sxs-lookup"><span data-stu-id="ae6b0-120">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="ae6b0-121">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中设置 JD Edwards OneWorld 发送端口</span><span class="sxs-lookup"><span data-stu-id="ae6b0-121">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="ae6b0-122">创建一个 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="ae6b0-122">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="ae6b0-123">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="ae6b0-123">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="ae6b0-124">测试应用程序并查看 XML 输出</span><span class="sxs-lookup"><span data-stu-id="ae6b0-124">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="ae6b0-125">你将使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中访问 JD Edwards OneWorld 系统上的数据。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-125">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ae6b0-126">此适配器允许由业务流程执行的请求和响应来处理 JD Edwards OneWorld 对象。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-126">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="ae6b0-127">许多方法可用于架构对象。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-127">Many methods are available for a schema object.</span></span> <span data-ttu-id="ae6b0-128">此实验室将演示如何使用**地址簿图： MBF**方法。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-128">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="ae6b0-129">在运行服务请求之前，必须为特定的 JD Edwards OneWorld 对象创建服务请求和响应架构。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-129">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="ae6b0-130">通过直接询问 JD Edwards OneWorld 中支持的元数据对象，添加生成的项/添加适配器向导可以创建这些架构。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-130">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="ae6b0-131">此实验室说明创建架构所需的步骤**地址簿图： MBF**方法并处理查询。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-131">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="procedures-for-lab-2--executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="ae6b0-132">实验室 2 的过程 - 执行 JD Edwards OneWorld 示例查询</span><span class="sxs-lookup"><span data-stu-id="ae6b0-132">Procedures for Lab 2- Executing a JD Edwards OneWorld Sample Query</span></span>  
  
### <a name="verifying-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="ae6b0-133">验证 JD Edwards OneWorld 先决条件</span><span class="sxs-lookup"><span data-stu-id="ae6b0-133">Verifying the JD Edwards OneWorld Prerequisites</span></span>  
 <span data-ttu-id="ae6b0-134">在开始创建 BizTalk 项目以便使用 JD Edwards OneWorld 适配器之前，你需要确保访问 JD Edwards OneWorld 系统所需的文件和适配器设置正确。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-134">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-135">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，JD Edwards OneWorld 适配器通过 Java 接口与 JD Edwards OneWorld 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-135">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>  
  
 <span data-ttu-id="ae6b0-136">四个文件所需的适当的接口访问使用博士 Edwards OneWorld 适配器博士 Edwards OneWorld 系统： Connector.jar、 Kernel.jar、 BTSLIBinterop.jar 和 JDEJAccess.jar。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-136">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
-   <span data-ttu-id="ae6b0-137">Connector.jar 和 Kernel.jar 文件随附了 JD Edwards OneWorld 系统，可以从 JD Edwards OneWorld 管理员获取。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-137">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="ae6b0-138">这些文件在 C:\JDEOWJars 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-138">These files are located in the C:\JDEOWJars folder.</span></span>  
  
-   <span data-ttu-id="ae6b0-139">遵循适配器安装指南中附带的这些说明，BTSLIBinterop.jar 文件可由 JD Edwards OneWorld 系统生成。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-139">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="ae6b0-140">此文件在 C:\JDEOWJars 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-140">This file is located in the C:\JDEOWJars folder.</span></span>  
  
-   <span data-ttu-id="ae6b0-141">JDEJAccess.jar 文件是 JDEOW 适配器的一部分，包含在该适配器的安装中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-141">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="ae6b0-142">默认情况下，它位于 C:\Program Files\Microsoft BizTalk 适配器对于企业 Applications\J.D。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-142">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="ae6b0-143">Edwards OneWorld® \Classes 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-143">Edwards OneWorld®\Classes folder.</span></span>  
  
##### <a name="to-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="ae6b0-144">验证 JD Edwards OneWorld 先决条件的步骤</span><span class="sxs-lookup"><span data-stu-id="ae6b0-144">To verify the JD Edwards OneWorld prerequisites</span></span>  
  
1.  <span data-ttu-id="ae6b0-145">请确保 Connector.jar、Kernel.jar 和 BTSLIBinterop.jar 文件在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的 C:\JDEOWJars 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-145">Ensure that the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
2.  <span data-ttu-id="ae6b0-146">请确保 JDEJAccess.jar 文件上存在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]企业 Applications\J.D 的 C:\Program Files\Microsoft BizTalk 适配器中的计算机。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-146">Ensure that the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="ae6b0-147">Edwards OneWorld® \Classes 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-147">Edwards OneWorld®\Classes folder.</span></span>  
  
3.  <span data-ttu-id="ae6b0-148">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-148">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
### <a name="configuring-biztalk-send-ports"></a><span data-ttu-id="ae6b0-149">配置 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="ae6b0-149">Configuring BizTalk Send Ports</span></span>  
 <span data-ttu-id="ae6b0-150">现在，你将验证是否安装了 JD Edwards OneWorld 适配器并创建 JD Edwards OneWorld 发送端口。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-150">Now you will verify that the JD Edwards OneWorld adapter is installed and create the JD Edwards OneWorld send port.</span></span>  
  
##### <a name="to-verify-that-the-jd-edwards-oneworld-adapter-is-installed-in-includepragueincludesprague-mdmd"></a><span data-ttu-id="ae6b0-151">验证 JD Edwards OneWorld 适配器是否安装在 [!INCLUDE[prague](../includes/prague-md.md)] 中的步骤</span><span class="sxs-lookup"><span data-stu-id="ae6b0-151">To verify that the JD Edwards OneWorld adapter is installed in [!INCLUDE[prague](../includes/prague-md.md)]</span></span>  
  
1.  <span data-ttu-id="ae6b0-152">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-152">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-153">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-153">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
     <span data-ttu-id="ae6b0-154">确保**JDE_OneWorld**安装适配器和列表。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-154">Ensure that the **JDE_OneWorld** adapter is installed and on the list.</span></span> <span data-ttu-id="ae6b0-155">如果没有安装 JD Edwards OneWorld 适配器，请安装企业应用程序的 BizTalk 适配器（请参阅前面的“先决条件”部分）。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-155">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="ae6b0-156">安装适配器后，右键单击**适配器**，然后单击**新建-适配器**安装博士 Edwards OneWorld 适配器。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-156">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="ae6b0-157">你必须重新启动主机实例才能使此操作生效。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-157">You will have to restart the host instance for this to take effect.</span></span>  
  
##### <a name="to-create-the-jd-edwards-oneworld-send-port"></a><span data-ttu-id="ae6b0-158">创建 JD Edwards OneWorld 发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="ae6b0-158">To create the JD Edwards OneWorld send port</span></span>  
  
1.  <span data-ttu-id="ae6b0-159">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-159">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-160">右键单击**发送端口**，单击**新建**，然后单击**静态请求-响应发送端口**。为这些字段中输入以下值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-160">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="ae6b0-161">**名称：**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-161">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="ae6b0-162">**类型：**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-162">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="ae6b0-163">**发送处理程序：**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-163">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="ae6b0-164">**发送管道：**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-164">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="ae6b0-165">**接收管道：**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-165">**Receive pipeline:**  `XMLReceive`</span></span>  
  
3.  <span data-ttu-id="ae6b0-166">单击“配置” ，然后输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-166">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="ae6b0-167">**主机：** \<输入你 JDEOW 的主机名 ></span><span class="sxs-lookup"><span data-stu-id="ae6b0-167">**Host:** \<enter your JDEOW host name></span></span>  
  
    2.  <span data-ttu-id="ae6b0-168">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-168">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="ae6b0-169">**JDEdwards 环境：** \<进入 JDEOW 环境 ></span><span class="sxs-lookup"><span data-stu-id="ae6b0-169">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
    4.  <span data-ttu-id="ae6b0-170">**JDEdwards JAR 文件：** \<输入的 JAR 文件的完整路径 ></span><span class="sxs-lookup"><span data-stu-id="ae6b0-170">**JDEdwards JAR files:** \<enter full path of JAR files></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="ae6b0-171">**密码：**使用下拉列表，然后输入你博士 Edwards OneWorld 密码。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-171">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="ae6b0-172">**端口：**  `6009`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-172">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="ae6b0-173">**用户名：** \<输入博士 Edwards 用户名 ></span><span class="sxs-lookup"><span data-stu-id="ae6b0-173">**User Name:** \<enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
4.  <span data-ttu-id="ae6b0-174">单击**确定**两次以关闭**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-174">Click **OK** twice to close the **Send Port Properties** dialog box.</span></span>  
  
### <a name="creating-a-biztalk-orchestration-project"></a><span data-ttu-id="ae6b0-175">创建 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="ae6b0-175">Creating a BizTalk Orchestration Project</span></span>  
 <span data-ttu-id="ae6b0-176">现在，你将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中创建 BizTalk 项目，并配置该项目中的业务流程，以处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 JD Edwards OneWorld 系统之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-176">Now you will create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-177">你将添加发送端口和接收端口，生成项目，然后部署项目。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-177">You will add send and receive ports, build the project, and then deploy the project.</span></span>  
  
##### <a name="to-create-the-biztalk-orchestration-project-in-visual-studio"></a><span data-ttu-id="ae6b0-178">在 Visual Studio 中创建 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="ae6b0-178">To create the BizTalk orchestration project in Visual Studio</span></span>  
  
1.  <span data-ttu-id="ae6b0-179">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在 C:\LABS 文件夹中创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-179">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="ae6b0-180">在“文件”  菜单上，单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-180">On the **File** menu, click **New**.</span></span> <span data-ttu-id="ae6b0-181">此时将显示“新建项目”  对话框。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-181">The **New Project** dialog box appears.</span></span> <span data-ttu-id="ae6b0-182">在“发送端口属性”  选择“空的 BizTalk Server 项目”。 </span><span class="sxs-lookup"><span data-stu-id="ae6b0-182">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="ae6b0-183">输入`JDE_OW_Test`作为唯一项目名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-183">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-184">在解决方案资源管理器中，右键单击该项目，单击“添加” ，然后单击“添加生成的项” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-184">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="ae6b0-185">在类别窗格中，选择**添加适配器元数据**，在模板窗格中，选择**添加适配器元数据**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-185">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="ae6b0-186">在添加适配器向导中，选择**博士 Edwards OneWorld**适配器，选择**JDE_OneWorldPort**发送在前面的过程中，创建的端口，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="ae6b0-186">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  <span data-ttu-id="ae6b0-187">上**选择服务添加到导入**页上，打开**博士 Edwards OneWorld**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-187">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="ae6b0-188">JDEOW 系统使用 BrowsingAgent 程序通过适配器进行连接。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-188">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="ae6b0-189">BrowsingAgent 返回以下服务。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-189">The BrowsingAgent returns the following services.</span></span>  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  <span data-ttu-id="ae6b0-190">展开**CALLBSFN**和向下滚动到**N0100041-地址簿图： MBF**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-190">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="ae6b0-191">选择 N0100041，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-191">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="ae6b0-192">在解决方案资源管理器中，会有一个新的 BizTalk 业务流程，包含两个新的相关架构文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-192">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="ae6b0-193">这些文件由添加适配器向导创建。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-193">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="ae6b0-194">双击“BizTalk Orchestration.odx”文件以打开业务流程。 </span><span class="sxs-lookup"><span data-stu-id="ae6b0-194">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 <span data-ttu-id="ae6b0-195">此业务流程接受已为 JD Edwards OneWorld 系统设置格式的 XML 文件作为文件适配器中的输入。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-195">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-196">此业务流程使用 JD Edwards OneWorld 适配器将 XML 文件发送到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-196">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-197">JD Edwards OneWorld 处理查询并生成包含结果的输出 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-197">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="ae6b0-198">此 XML 文件通过 JD Edwards OneWorld 适配器返回到业务流程，并且文件适配器将 XML 文件写入磁盘上的输出位置。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-198">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="ae6b0-199">要完成业务流程，你需要创建并配置用于接收和发送 XML 文件的端口。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-199">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="ae6b0-200">首先，配置文件适配器所用的接收端口，以便从磁盘将包含查询的 XML 输入到业务流程。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-200">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
##### <a name="to-configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="ae6b0-201">配置接收端口以接受 XML 输入文件的步骤</span><span class="sxs-lookup"><span data-stu-id="ae6b0-201">To configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="ae6b0-202">双击“BizTalk Orchestration.odx”文件以打开业务流程。 </span><span class="sxs-lookup"><span data-stu-id="ae6b0-202">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="ae6b0-203">在 BizTalk Orchestration.odx 文件中，右键单击左的端口图面，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-203">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="ae6b0-204">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-204">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="ae6b0-205">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-205">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="ae6b0-206">上**端口属性**页上，输入`JDE_File_In`为**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-206">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ae6b0-207">在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-207">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="ae6b0-208">**端口类型名称**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-208">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="ae6b0-209">**通信模式**： **单向**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-209">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="ae6b0-210">**访问限制**： **内部 - 仅限于此项目**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-210">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="ae6b0-211">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="ae6b0-211">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="ae6b0-212">**端口通信方向**： **始终在此端口上接收消息**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-212">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="ae6b0-213">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-213">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="ae6b0-214">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-214">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="ae6b0-215">接下来，创建一个发送/接收端口，将包含查询的初始 XML 输入文件发送到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-215">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-216">此端口还接收 XML 输出文件，该文件包含来自对 JD Edwards OneWorld 系统调用的查询结果。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-216">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
##### <a name="to-configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="ae6b0-217">配置发送/接收端口以连接 JD Edwards OneWorld 的步骤</span><span class="sxs-lookup"><span data-stu-id="ae6b0-217">To configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="ae6b0-218">在 BizTalk Orchestration.odx 文件中，右键单击右侧端口图面，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-218">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="ae6b0-219">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-219">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="ae6b0-220">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-220">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-221">在“选择端口类型”  页上，选择“使用现有端口类型” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-221">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="ae6b0-222">下**可用端口类型**，选择**JD_OW_Test.N0100041**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-222">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  <span data-ttu-id="ae6b0-223">选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-223">Select the following property values:</span></span>  
  
     <span data-ttu-id="ae6b0-224">**端口的通信的方向**:**我将发送请求并接收响应**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-224">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="ae6b0-225">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-225">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="ae6b0-226">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-226">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="ae6b0-227">在端口图面上，你将看到端口和可用的方法。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-227">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="ae6b0-228">最后，配置文件适配器要使用的发送端口，从而将包含查询结果的 XML 输出到磁盘。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-228">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
##### <a name="to-configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="ae6b0-229">配置发送端口将 XML 文件输出到磁盘的步骤</span><span class="sxs-lookup"><span data-stu-id="ae6b0-229">To configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="ae6b0-230">在 BizTalk Orchestration.odx 文件中，右键单击左的端口图面，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-230">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="ae6b0-231">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-231">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="ae6b0-232">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-232">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-233">上**端口属性**页上，输入`JDE_FileOut`为**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-233">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="ae6b0-234">在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-234">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="ae6b0-235">**端口类型名称**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-235">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="ae6b0-236">**通信模式**： **单向**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-236">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="ae6b0-237">**访问限制**： **内部 - 仅限于此项目**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-237">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="ae6b0-238">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="ae6b0-238">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="ae6b0-239">**端口通信方向**： **始终在此端口上发送消息**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-239">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="ae6b0-240">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-240">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="ae6b0-241">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-241">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="ae6b0-242">端口图面上显示的是 JD Edwards OneWorld 服务的新端口和可用方法。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-242">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="ae6b0-243">随后，你将指定 JD Edwards OneWorld 适配器，以发送和接收来自 JD Edwards OneWorld 系统的文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-243">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="ae6b0-244">**JDE_File_In**和**JDE_File_Out**你刚刚创建需要的端口相关联的消息类型。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-244">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
##### <a name="to-assign-message-types-to-the-ports"></a><span data-ttu-id="ae6b0-245">为端口分配消息类型</span><span class="sxs-lookup"><span data-stu-id="ae6b0-245">To assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="ae6b0-246">在左的端口面上**JDE_File_In**端口，请单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-246">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="ae6b0-247">在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBF**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-247">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-248">在左的端口面上**JDE_File_Out**端口，请单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-248">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="ae6b0-249">在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBFResponse**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-249">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="ae6b0-250">插入两个**发送**形状和第二个**接收**用于链接到的端口到业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-250">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
##### <a name="to-add-send-and-receive-shapes"></a><span data-ttu-id="ae6b0-251">添加“发送”和“接收”形状</span><span class="sxs-lookup"><span data-stu-id="ae6b0-251">To add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="ae6b0-252">将工具箱中的“接收”  组件拖放到业务流程的起点（绿色圆圈）下。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-252">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="ae6b0-253">单击**接收**形状，然后在属性窗口中，输入`Get_File`为**名称**，并设置**激活**到`true`。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-253">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="ae6b0-254">执行此操作后，此接收端口上收到传入文档时将激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-254">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="ae6b0-255">拖动**发送**组件从工具箱拖放正下方**GetFileReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-255">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="ae6b0-256">单击新建**发送**形状，然后在属性窗口中，输入`SendToJDEOW`为**名称**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-256">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="ae6b0-257">拖动**接收**组件从工具箱拖放正下方**SendToJDEOWSend**形状。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-257">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="ae6b0-258">单击**接收**形状，然后在属性窗口中，输入`JDEOW_Resp`为**名称**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-258">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="ae6b0-259">拖动**发送**组件从工具箱拖放正下方**JDEOW_RespReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-259">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="ae6b0-260">单击新建**发送**形状，然后在属性窗口中，输入`FileToDisk`为**名称**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-260">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  <span data-ttu-id="ae6b0-261">连接**JDE_FileIn**端口到**GetFileReceive**组件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-261">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="ae6b0-262">连接**JDE_FileOut**端口到**FileToDiskReceive**组件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-262">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="ae6b0-263">转到**业务流程视图**展开**消息**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-263">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="ae6b0-264">更改的标识符**Message_1**到`MsgToJDEOW`，和**Message_2**到`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-264">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="ae6b0-265">突出显示**SendToJDEOWSend**组件，并且已设置其**消息**属性**MsgToJDEOW**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-265">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="ae6b0-266">突出显示**JDEOW_RespReceive**组件，并且已设置其**消息**属性**JDEOW_Resp**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-266">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="ae6b0-267">连接**SendToJDEOW**到**请求**部分**JDE_OW_Port**端口。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-267">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="ae6b0-268">连接**JDEOW_Resp**到**响应**部分**JDE_OW_Port**端口。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-268">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
### <a name="building-and-deploying-the-project"></a><span data-ttu-id="ae6b0-269">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="ae6b0-269">Building and Deploying the Project</span></span>  
 <span data-ttu-id="ae6b0-270">现在，BizTalk 项目已完成，你可以生成项目并将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-270">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
##### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="ae6b0-271">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="ae6b0-271">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="ae6b0-272">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-272">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="ae6b0-273">要生成项目，你需要强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-273">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="ae6b0-274">在命令提示符下，输入以下内容以创建强名称密钥文件：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-274">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="ae6b0-275">**sn-k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-275">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="ae6b0-276">在解决方案资源管理器，右键单击**JD_OW_Test**项目，，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-276">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="ae6b0-277">单击“签名”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-277">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="ae6b0-278">选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-278">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="ae6b0-279">浏览以选择密钥文件“labs.snk” ，然后单击“打开” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-279">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="ae6b0-280">单击项目设计器中的“部署”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-280">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="ae6b0-281">设置**应用程序名称**到`JDE_OW_Test`。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-281">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="ae6b0-282">在解决方案资源管理器，右键单击**JDE_OW_Test**项目，，然后单击**生成。**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-282">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. <span data-ttu-id="ae6b0-283">生成成功完成后，右键单击**XX_JD Edwards OneWorldQuery**项目，，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-283">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="ae6b0-284">在输出窗口中将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-284">In the output window the following output will be displayed:</span></span>  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
### <a name="testing-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="ae6b0-285">测试应用程序并查看 XML 输出</span><span class="sxs-lookup"><span data-stu-id="ae6b0-285">Testing the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="ae6b0-286">现在，你将测试你所创建和部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-286">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="ae6b0-287">你将创建用于启动业务流程进程的 XML 文件，然后将文件夹配置为接收和发送应用程序中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-287">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="ae6b0-288">配置应用程序之后，将运行该应用程序并查看业务流程返回的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-288">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
##### <a name="to-generate-the-xml-file-for-the-query"></a><span data-ttu-id="ae6b0-289">生成 XML 文件以便查询</span><span class="sxs-lookup"><span data-stu-id="ae6b0-289">To generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="ae6b0-290">在解决方案资源管理器中，双击**N0100041Service_N0100041.xsd**打开文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-290">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="ae6b0-291">右键单击**N0100041Service_N0100041.xsd** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-291">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="ae6b0-292">为“输出实例文件名”输入示例 XML 的  以下路径和文件名：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-292">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="ae6b0-293">单击“确定” **。**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-293">Click **OK.**</span></span> <span data-ttu-id="ae6b0-294">在属性窗口中，选择**\<架构 >**并设置**根引用：**到`AddressBookMasterMBF`。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-294">In the Properties window, select **\<Schema>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="ae6b0-295">这将导致生成的 XML，仅包含**查询**xml。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-295">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  <span data-ttu-id="ae6b0-296">右键单击**N0100041Service_N0100041.xsd** ，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-296">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="ae6b0-297">这将生成**Sample.xml**文件。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-297">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="ae6b0-298">此文件将放入接收位置，作为适配器启动业务流程进程的输入。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-298">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
##### <a name="to-configure-and-start-the-biztalk-application"></a><span data-ttu-id="ae6b0-299">配置和启动 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ae6b0-299">To configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="ae6b0-300">配置用于接收传入文件和发送传出文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-300">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="ae6b0-301">转到**C:\LABS\JDE_OW_Test**并创建两个新的子文件夹名为`FileIn`和`FileOut`。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-301">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="ae6b0-302">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-302">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ae6b0-303">右键单击**JDE_OW_Test**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-303">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  <span data-ttu-id="ae6b0-304">选择“Orchestration_1”  ，然后单击“主机”  下拉框。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-304">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="ae6b0-305">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-305">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="ae6b0-306">下**接收端口**，单击**\<无 >**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-306">Under **Receive Ports**, click **\<None>**.</span></span> <span data-ttu-id="ae6b0-307">在下拉列表中，选择“新建接收端口” 。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-307">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="ae6b0-308">有关**名称**，类型`JDE_FileIn_Port`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-308">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="ae6b0-309">将出现一个消息框，表明你需要指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-309">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="ae6b0-310">单击“确定”，然后单击“新建”。  </span><span class="sxs-lookup"><span data-stu-id="ae6b0-310">Click **OK**, and then click **New**.</span></span>  
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  <span data-ttu-id="ae6b0-311">键入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-311">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="ae6b0-312">**名称**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-312">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="ae6b0-313">**类型**： **文件**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-313">**Type**: **File**</span></span>  
  
     <span data-ttu-id="ae6b0-314">**接收处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-314">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="ae6b0-315">**接收管道**： **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-315">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  <span data-ttu-id="ae6b0-316">单击**配置**，类型`C:\LABS\JDE_OW_Test\FileIn`为**接收文件夹**，然后单击**确定**三次。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-316">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. <span data-ttu-id="ae6b0-317">单击**\<无 >**为**JDE_OW_Port**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-317">Click **\<None>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="ae6b0-318">选择**新建发送端口**，然后选择或键入属性的以下值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-318">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="ae6b0-319">**名称**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-319">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="ae6b0-320">**类型**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-320">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="ae6b0-321">**发送处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-321">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="ae6b0-322">**管道**：“XMLTransmit”  和“XMLReceive” </span><span class="sxs-lookup"><span data-stu-id="ae6b0-322">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="ae6b0-323">单击“配置” ，然后输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-323">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="ae6b0-324">**主机：** \<输入你 JDEOW 的主机名 ></span><span class="sxs-lookup"><span data-stu-id="ae6b0-324">**Host:** \<enter your JDEOW host name></span></span>  
  
     <span data-ttu-id="ae6b0-325">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-325">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="ae6b0-326">**JDEdwards 环境：** \<进入 JDEOW 环境 ></span><span class="sxs-lookup"><span data-stu-id="ae6b0-326">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
     <span data-ttu-id="ae6b0-327">**JDEdwards JAR 文件：**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="ae6b0-327">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="ae6b0-328">**密码：**使用下拉列表，然后输入你博士 Edwards OneWorld 密码。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-328">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="ae6b0-329">**端口：**  `6009`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-329">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="ae6b0-330">**用户名：**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="ae6b0-330">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. <span data-ttu-id="ae6b0-331">单击“确定”  两次以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-331">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="ae6b0-332">在配置 Applicationwindow 中，单击**\<无 >**为**JDE_FileOut**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-332">In the Configure Applicationwindow, click **\<None>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="ae6b0-333">选择“新建发送端口”  ，然后键入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-333">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="ae6b0-334">**名称**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="ae6b0-334">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="ae6b0-335">**类型**： **文件**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-335">**Type**: **File**</span></span>  
  
     <span data-ttu-id="ae6b0-336">**发送处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-336">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="ae6b0-337">**发送管道**： **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-337">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="ae6b0-338">单击**配置**和类型`C:\Labs\JDE_OW_Test\FileOut`为**目标文件夹。**</span><span class="sxs-lookup"><span data-stu-id="ae6b0-338">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="ae6b0-339">。为“文件名”保留“”，因为这会为每个消息生成唯一的文件。  ，  because this results in a unique file ， each message.</span><span class="sxs-lookup"><span data-stu-id="ae6b0-339">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. <span data-ttu-id="ae6b0-340">单击“确定”三次  以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-340">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="ae6b0-341">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**JDE_OW_Test**应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-341">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
##### <a name="to-test-the-orchestration"></a><span data-ttu-id="ae6b0-342">测试业务流程</span><span class="sxs-lookup"><span data-stu-id="ae6b0-342">To test the orchestration</span></span>  
  
1.  <span data-ttu-id="ae6b0-343">在**C:\Labs\JDE_OW_Test**目录**Sample.xml**文件将显示为：</span><span class="sxs-lookup"><span data-stu-id="ae6b0-343">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  <span data-ttu-id="ae6b0-344">编辑**Sample.xml**文件，以删除以外的所有内容**cActionCode**和**mnAddressBookNumber**元素。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-344">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  <span data-ttu-id="ae6b0-345">有关**cActionCode**元素插入的字母`i`。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-345">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="ae6b0-346">有关**mnAddressBookNumber**插入数`500`。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-346">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="ae6b0-347">保存更改并将文件复制到**C:\Labs\JDE_OW_Test\FileIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-347">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="ae6b0-348">这是启动业务流程进程的接收位置。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-348">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="ae6b0-349">在几秒钟，XML 文件应出现在**C:\Labs\JDE_OW_Test\FileOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-349">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="ae6b0-350">此文件应包含地址为 500 的所有记录。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-350">This should contain the all the records where the address is 500.</span></span>  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     <span data-ttu-id="ae6b0-351">此返回的记录数据应与匹配实验室 1 中为博士 Edwards OneWorld 系统的查询返回的数据。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-351">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="ae6b0-352">通过比较实验室 1 中获得的记录，你可以验证**获取**方法正常运行。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-352">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ae6b0-353">摘要</span><span class="sxs-lookup"><span data-stu-id="ae6b0-353">Summary</span></span>  
 <span data-ttu-id="ae6b0-354">在本实验室中，你首先验证了访问 JD Edwards OneWorld 系统所需的先决条件是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-354">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-355">然后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建了包含业务流程的新 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-355">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="ae6b0-356">你将配置 BizTalk 业务流程，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-356">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-357">为配置业务流程，你创建了发送端口、接收端口和发送/接收端口。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-357">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="ae6b0-358">将这些端口绑定到 JD Edwards OneWorld 适配器，并将消息分配给相应的端口。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-358">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="ae6b0-359">完成 BizTalk 项目后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 来生成和部署该项目。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-359">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="ae6b0-360">随后，配置了新应用程序，运行该应用程序，并从 JD Edwards OneWorld 系统中获取数据。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-360">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ae6b0-361">要验证应用程序是否正常运行，你将其输出 XML 文件与实验室 1 中从 JD Edwards OneWorld 系统接收到的文件进行了比较。</span><span class="sxs-lookup"><span data-stu-id="ae6b0-361">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>