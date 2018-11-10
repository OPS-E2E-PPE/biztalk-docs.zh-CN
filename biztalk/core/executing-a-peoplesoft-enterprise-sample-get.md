---
title: 执行 PeopleSoft Enterprise 示例获取 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb54f14c-3fce-44d6-91bb-cb1ca38a20da
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e4601264b8dc407d1cc1bed323b4d3504bc91d
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753245"
---
# <a name="execute-a-peoplesoft-enterprise-sample-get"></a><span data-ttu-id="7f756-102">执行 PeopleSoft Enterprise 示例获取</span><span class="sxs-lookup"><span data-stu-id="7f756-102">Execute a PeopleSoft Enterprise Sample Get</span></span>
<span data-ttu-id="7f756-103">使用 PeopleSoft 适配器可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="7f756-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="7f756-104">此适配器随[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f756-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="7f756-105">这是 PeopleSoft 实验室工作的第二部分。</span><span class="sxs-lookup"><span data-stu-id="7f756-105">This is the second part of the PeopleSoft lab work.</span></span> <span data-ttu-id="7f756-106">在第一部分（实验室 1）中，您在未使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 协助或其他 Microsoft 技术的情况下，手动访问并修改了 PeopleSoft 系统上的数据。</span><span class="sxs-lookup"><span data-stu-id="7f756-106">In the first part (Lab 1), you manually accessed and modified data on the PeopleSoft system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="7f756-107">在本部分（实验室 2）中，你将创建一个 BizTalk 业务流程作为 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="7f756-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="7f756-108">您需要针对此业务流程配置端口，以便使用 PeopleSoft 适配器获取 PeopleSoft 系统中的数据。</span><span class="sxs-lookup"><span data-stu-id="7f756-108">You will configure ports on this orchestration to use the PeopleSoft adapter to get data from a PeopleSoft system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7f756-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="7f756-109">Prerequisites</span></span>  
  
- <span data-ttu-id="7f756-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f756-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
- <span data-ttu-id="7f756-111">Microsoft BizTalk Adapters for Enterprise Applications</span><span class="sxs-lookup"><span data-stu-id="7f756-111">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
- <span data-ttu-id="7f756-112">Microsoft Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7f756-112">Microsoft Visual Studio</span></span>  
  
- <span data-ttu-id="7f756-113">Sun Systems Java Development Kit (JDK) 版本 1.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7f756-113">Sun Systems Java Development Kit (JDK) version 1.4 or higher</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f756-114">请参阅[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)用于 JD Edwards、 PeopleSoft 和 TIBCO 适配器的重要配置信息。</span><span class="sxs-lookup"><span data-stu-id="7f756-114">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-peoplesoft-sample-get"></a><span data-ttu-id="7f756-115">实验室 2 - 执行 PeopleSoft Get 示例</span><span class="sxs-lookup"><span data-stu-id="7f756-115">Lab 2 - Executing a PeopleSoft Sample Get</span></span>  
 <span data-ttu-id="7f756-116">在此实验室中，您将针对 PeopleSoft 系统执行 **Get** 操作。</span><span class="sxs-lookup"><span data-stu-id="7f756-116">In this lab, you will execute a **Get** operation against the PeopleSoft system.</span></span> <span data-ttu-id="7f756-117">具体将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="7f756-117">Specifically you will perform the following tasks:</span></span>  
  
- <span data-ttu-id="7f756-118">验证 PeopleSoft 必备组件</span><span class="sxs-lookup"><span data-stu-id="7f756-118">Verify the PeopleSoft prerequisites</span></span>  
  
- <span data-ttu-id="7f756-119">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中设置一个 PeopleSoft 发送端口</span><span class="sxs-lookup"><span data-stu-id="7f756-119">Set up a PeopleSoft send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="7f756-120">创建一个 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="7f756-120">Create a BizTalk orchestration project</span></span>  
  
- <span data-ttu-id="7f756-121">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="7f756-121">Build and deploy the project</span></span>  
  
- <span data-ttu-id="7f756-122">测试应用程序并查看 XML 输出</span><span class="sxs-lookup"><span data-stu-id="7f756-122">Test the application and view the XML output</span></span>  
  
## <a name="procedures-for-lab-2--executing-a-peoplesoft-sample-get"></a><span data-ttu-id="7f756-123">实验室 2 的过程 - 执行 PeopleSoft Get 示例</span><span class="sxs-lookup"><span data-stu-id="7f756-123">Procedures for Lab 2- Executing a PeopleSoft Sample Get</span></span>  
 <span data-ttu-id="7f756-124">必须使用以下两个文件，才能对 PeopleSoft 系统的接口进行正确访问：PSJOA.JAR 和 GET_CI_INFO.PC。</span><span class="sxs-lookup"><span data-stu-id="7f756-124">Two files are necessary for proper interface access to a PeopleSoft system: PSJOA.JAR and GET_CI_INFO.PC.</span></span> <span data-ttu-id="7f756-125">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，PeopleSoft 适配器通过使用 PeopleSoft Java 接口与 PeopleSoft 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="7f756-125">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the PeopleSoft adapter communicates with the PeopleSoft system by using the PeopleSoft Java interface.</span></span> <span data-ttu-id="7f756-126">此接口由 PSJOA.JAR 文件提供。</span><span class="sxs-lookup"><span data-stu-id="7f756-126">This interface is supplied by the PSJOA.JAR file.</span></span> <span data-ttu-id="7f756-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上存放的此文件的副本通常来自正在访问的 PeopleSoft 服务器系统的管理员。</span><span class="sxs-lookup"><span data-stu-id="7f756-127">A copy of this file placed onto the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] typically comes from the administrator of the PeopleSoft server system that is being accessed.</span></span> <span data-ttu-id="7f756-128">在此实验室中，PSJOA.JAR 的副本位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 C:\PSJars\Ver841\ 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7f756-128">In this lab, a copy of PSJOA.JAR exists in the C:\PSJars\Ver841\ folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7f756-129">PeopleSoft 适配器配置属性中指定了此文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7f756-129">The location of this file is specified in the PeopleSoft adapter configuration properties.</span></span>  
  
 <span data-ttu-id="7f756-130">PeopleSoft 系统本身必须安装自定义组件接口 (CI)。</span><span class="sxs-lookup"><span data-stu-id="7f756-130">On the PeopleSoft system itself, a custom component interface (CI) must be installed.</span></span> <span data-ttu-id="7f756-131">这将允许适配器在适配器配置过程中浏览 PeopleSoft 对象。</span><span class="sxs-lookup"><span data-stu-id="7f756-131">This allows the adapter to browse PeopleSoft objects during adapter configuration.</span></span> <span data-ttu-id="7f756-132">将（从“添加生成的项”步骤）调用自定义组件接口，以获取可访问的 PeopleSoft 对象的列表。</span><span class="sxs-lookup"><span data-stu-id="7f756-132">The custom component interface is called (from within the Add Generated Items step) to get a list of accessible PeopleSoft objects.</span></span> <span data-ttu-id="7f756-133">这些对象确定可用于客户端系统的公开的 PeopleSoft 功能。</span><span class="sxs-lookup"><span data-stu-id="7f756-133">These objects determine exposed PeopleSoft functionality available to the client system.</span></span>  
  
 <span data-ttu-id="7f756-134">特别是在初始安装过程中，PeopleSoft 系统上必须安装自定义组件 GET_CI_INFO。</span><span class="sxs-lookup"><span data-stu-id="7f756-134">Specifically the custom component, GET_CI_INFO, must be installed on the PeopleSoft system once during initial setup.</span></span> <span data-ttu-id="7f756-135">可对此文件进行修改，以限制 GET_CI_INFO 公开的内容（默认情况下，公开 PeopleSoft 系统中的所有组件接口）。</span><span class="sxs-lookup"><span data-stu-id="7f756-135">This file can be modified to limit what the GET_CI_INFO exposes (by default it exposes all component interfaces within the PeopleSoft system).</span></span> <span data-ttu-id="7f756-136">此文件源位于以下默认位置的 GET_CI_INFO.PC 文本文件中：</span><span class="sxs-lookup"><span data-stu-id="7f756-136">Its source is found in the GET_CI_INFO.PC text file at the following default location:</span></span>  
  
 <span data-ttu-id="7f756-137">**C:\Program Files\Microsoft BizTalk Adapters 为 Enterprise Applications\PeopleSoft Enterprise(r) \Config 的**</span><span class="sxs-lookup"><span data-stu-id="7f756-137">**C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config**</span></span>  
  
 <span data-ttu-id="7f756-138">中提供了常规说明如何将 GET_CI_INFO 组件接口安装到 PeopleSoft[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="7f756-138">General instructions about installing the GET_CI_INFO component interface into PeopleSoft are provided in [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md).</span></span> <span data-ttu-id="7f756-139">这些说明面向经验丰富的 PeopleSoft 管理员。</span><span class="sxs-lookup"><span data-stu-id="7f756-139">These instructions are for an experienced PeopleSoft administrator.</span></span>  
  
## <a name="step-1-confirm-the-peoplesoft-rerequisites"></a><span data-ttu-id="7f756-140">步骤 1： 确认 PeopleSoft rerequisites</span><span class="sxs-lookup"><span data-stu-id="7f756-140">Step 1: Confirm the PeopleSoft rerequisites</span></span>  
 <span data-ttu-id="7f756-141">开始创建与 PeopleSoft 适配器配合使用的 BizTalk 项目之前，需要确保为访问 PeopleSoft 正确安装了所有必备组件。</span><span class="sxs-lookup"><span data-stu-id="7f756-141">Before you start creating a BizTalk project for use with the PeopleSoft adapter, you need to be sure that everything is set up correctly to access PeopleSoft.</span></span>  
  
1. <span data-ttu-id="7f756-142">确认 PSJOA。JAR 文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机的 C:\psjars\ver841 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7f756-142">Confirm that the PSJOA.JAR file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\psjars\ver841 folder.</span></span> <span data-ttu-id="7f756-143">（此文件可能位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的其他位置。</span><span class="sxs-lookup"><span data-stu-id="7f756-143">(This file can exist at a different location on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7f756-144">在以下给定的配置中，假设该文件位于此位置。）</span><span class="sxs-lookup"><span data-stu-id="7f756-144">In the configuration given below, it is assumed the file is at this location.)</span></span>  
  
2. <span data-ttu-id="7f756-145">确认 get_ci_info.pc 文件位于 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r) \Config 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7f756-145">Confirm that the get_ci_info.pc file exists in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config folder.</span></span>  
  
3. <span data-ttu-id="7f756-146">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="7f756-146">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span> <span data-ttu-id="7f756-147">确保安装了 PeopleSoft 适配器，且该适配器位于列表中。</span><span class="sxs-lookup"><span data-stu-id="7f756-147">Ensure that the PeopleSoft adapter is installed and on the list.</span></span>  
  
    <span data-ttu-id="7f756-148">如果未安装 PeopleSoft 适配器，请安装企业应用程序的 BizTalk 适配器（请参阅前面的“必备组件”部分）。</span><span class="sxs-lookup"><span data-stu-id="7f756-148">If the PeopleSoft adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="7f756-149">安装适配器之后，右键单击“适配器”  ，然后单击“新建 - 适配器”  以安装 PeopleSoft 适配器。</span><span class="sxs-lookup"><span data-stu-id="7f756-149">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the PeopleSoft adapter.</span></span> <span data-ttu-id="7f756-150">重新启动主机实例这才会生效。</span><span class="sxs-lookup"><span data-stu-id="7f756-150">Restart the host instance for this to take effect.</span></span>  
  
## <a name="step-2-create-a-send-port-for-peoplesoft"></a><span data-ttu-id="7f756-151">步骤 2： 创建 peoplesoft 发送端口</span><span class="sxs-lookup"><span data-stu-id="7f756-151">Step 2: Create a Send Port for PeopleSoft</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7f756-152">需要具有发送端口以便用于与 PeopleSoft 系统通信。</span><span class="sxs-lookup"><span data-stu-id="7f756-152">needs to have a send port to use for communicating with the PeopleSoft system.</span></span> <span data-ttu-id="7f756-153">此发送端口将最终绑定到业务流程的逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="7f756-153">This send port will eventually be bound to the orchestration's logical ports.</span></span>  
  
1. <span data-ttu-id="7f756-154">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk.EnterpriseApplication。**</span><span class="sxs-lookup"><span data-stu-id="7f756-154">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk.EnterpriseApplication.**</span></span>  
  
2. <span data-ttu-id="7f756-155">右键单击“发送端口” ，单击“新建” ，然后选择“静态要求响应发送端口” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-155">Right-click **Send Ports**, click **New**, and then select **Static Solicit-Response Send Port**.</span></span> <span data-ttu-id="7f756-156">在“发送端口属性”  对话框中，输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-156">In the **Send Port Properties** dialog box, enter the following values for the properties:</span></span>  
  
   1.  <span data-ttu-id="7f756-157">**名称：**  `PeopleSoftSamplePort`</span><span class="sxs-lookup"><span data-stu-id="7f756-157">**Name:**  `PeopleSoftSamplePort`</span></span>  
  
   2.  <span data-ttu-id="7f756-158">**类型：**  `PeopleSoft`</span><span class="sxs-lookup"><span data-stu-id="7f756-158">**Type:**  `PeopleSoft`</span></span>  
  
   3.  <span data-ttu-id="7f756-159">**发送处理程序：**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="7f756-159">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
   4.  <span data-ttu-id="7f756-160">**发送管道：**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="7f756-160">**Send pipeline:**  `XMLTransmit`</span></span>  
  
   5.  <span data-ttu-id="7f756-161">**接收管道：**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="7f756-161">**Receive pipeline:**  `XMLReceive`</span></span>  
  
3. <span data-ttu-id="7f756-162">单击“配置” ，然后输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-162">Click **Configure**, and then enter the following property values:</span></span>  
  
   1. <span data-ttu-id="7f756-163">**应用程序服务器路径**： **//Servername:9000**</span><span class="sxs-lookup"><span data-stu-id="7f756-163">**Application server path**: **//Servername:9000**</span></span>  
  
       <span data-ttu-id="7f756-164">Servername 是您的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="7f756-164">Servername is your application server.</span></span> <span data-ttu-id="7f756-165">这是特定服务器名称或 IP 地址以及此 PeopleSoft 系统的端口号。</span><span class="sxs-lookup"><span data-stu-id="7f756-165">This is the specific server name or IP address and port number for this PeopleSoft system.</span></span>  
  
   2. <span data-ttu-id="7f756-166">**JAVA_HOME**： **C:\J2SDK1.4.2_08**</span><span class="sxs-lookup"><span data-stu-id="7f756-166">**JAVA_HOME**: **C:\J2SDK1.4.2_08**</span></span>  
  
       <span data-ttu-id="7f756-167">此路径特定于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 Java SDK 安装。</span><span class="sxs-lookup"><span data-stu-id="7f756-167">This path is specific to the Java SDK installation on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   3. <span data-ttu-id="7f756-168">**密码**:\<输入您的 PeopleSoft 密码\></span><span class="sxs-lookup"><span data-stu-id="7f756-168">**Password**: \<enter your PeopleSoft password\></span></span>  
  
   4. <span data-ttu-id="7f756-169">**PeopleSoft 8.x JAR 文件**： **C:\PSJARS\VER841\PSJOA.JAR**</span><span class="sxs-lookup"><span data-stu-id="7f756-169">**PeopleSoft 8.x JAR files**: **C:\PSJARS\VER841\PSJOA.JAR**</span></span>  
  
   5. <span data-ttu-id="7f756-170">**用户名：** \<输入你的 PeopleSoft 用户\></span><span class="sxs-lookup"><span data-stu-id="7f756-170">**User name:** \<enter your PeopleSoft UserID\></span></span>  
  
      <span data-ttu-id="7f756-171">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span><span class="sxs-lookup"><span data-stu-id="7f756-171">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span></span>  
  
4. <span data-ttu-id="7f756-172">单击“确定”  两次以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="7f756-172">Click **OK** twice to close the dialog boxes.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="7f756-173">步骤 3： 创建 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="7f756-173">Step 3: Create a BizTalk Orchestration Project</span></span>  
 <span data-ttu-id="7f756-174">现在，您将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中创建 BizTalk 项目，并配置该项目中的业务流程，以处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 PeopleSoft 系统之间的通信。</span><span class="sxs-lookup"><span data-stu-id="7f756-174">Now you will create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the PeopleSoft system.</span></span> <span data-ttu-id="7f756-175">你将添加发送端口和接收端口，生成项目，然后部署项目。</span><span class="sxs-lookup"><span data-stu-id="7f756-175">You will add send and receive ports, build the project, and then deploy the project.</span></span>  
  
1. <span data-ttu-id="7f756-176">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ，在 C:\LABS 文件夹中创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7f756-176">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="7f756-177">在“文件”  菜单上，单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-177">On the **File** menu, click **New**.</span></span> <span data-ttu-id="7f756-178">此时将显示“新建项目”  对话框。</span><span class="sxs-lookup"><span data-stu-id="7f756-178">The **New Project** dialog box appears.</span></span> <span data-ttu-id="7f756-179">在“发送端口属性”  选择“空的 BizTalk Server 项目”。 </span><span class="sxs-lookup"><span data-stu-id="7f756-179">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="7f756-180">输入`PS_Test`作为唯一项目名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7f756-180">Enter `PS_Test` as the unique project name, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="7f756-181">在解决方案资源管理器中，右键单击该项目，单击“添加” ，然后单击“添加生成的项” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-181">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="7f756-182">在“类别”  窗格中选择“添加适配器元数据”  ，在“模板”  侧选择“添加适配器元数据”  ，然后单击“添加” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-182">Select **Add Adapter Metadata** in the **Categories** pane, select **Add Adapter Metadata** on the **Templates** side, and then click **Add**.</span></span>  
  
3. <span data-ttu-id="7f756-183">在添加适配器向导中，选择“PeopleSoft Enterprise”适配器  ，选择在前面的过程中创建的“PeopleSoftSamplePort”  发送端口，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-183">In the Add Adapter Wizard, select the **PeopleSoft Enterprise** adapter, select the **PeopleSoftSamplePort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
    <span data-ttu-id="7f756-184">![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")</span><span class="sxs-lookup"><span data-stu-id="7f756-184">![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")</span></span>  
  
4. <span data-ttu-id="7f756-185">在“选择要导入的服务”页上，  展开“PeopleSoft” ，然后展开“CI” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-185">On the **Select Services to Import** page, expand **PeopleSoft**, and then expand **CI**.</span></span>  
  
    <span data-ttu-id="7f756-186">适配器使用浏览代理对 PeopleSoft 系统进行询问。</span><span class="sxs-lookup"><span data-stu-id="7f756-186">The PeopleSoft system is interrogated by the adapter using the Browsing Agent.</span></span> <span data-ttu-id="7f756-187">展开“CI” 时，BrowsingAgent.exe 进程启动（进程运行时，您可以在任务管理器中查看），并返回下图中显示的服务。</span><span class="sxs-lookup"><span data-stu-id="7f756-187">When you expand **CI**, the BrowsingAgent.exe process starts (you can view it as running in Task Manager) and returns the services shown in the following figure.</span></span>  
  
    <span data-ttu-id="7f756-188">![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")</span><span class="sxs-lookup"><span data-stu-id="7f756-188">![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7f756-189">从您的 PeopleSoft 系统获得和显示的 PeopleSoft 服务可能与此处显示的服务稍有不同。</span><span class="sxs-lookup"><span data-stu-id="7f756-189">The PeopleSoft services obtained and displayed from your PeopleSoft system may be slightly different than the services displayed here.</span></span>  
  
5. <span data-ttu-id="7f756-190">向下滚动，选择“LOCATION” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-190">Scroll down, select **LOCATION**, and then click **Finish**.</span></span>  
  
    <span data-ttu-id="7f756-191">![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")</span><span class="sxs-lookup"><span data-stu-id="7f756-191">![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")</span></span>  
  
6. <span data-ttu-id="7f756-192">在解决方案资源管理器中，出现一个新的 BizTalk 业务流程和两个新的相关架构文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-192">In Solution Explorer, there is a new BizTalk orchestration and two new associated schema files.</span></span> <span data-ttu-id="7f756-193">这些文件由添加适配器向导创建。</span><span class="sxs-lookup"><span data-stu-id="7f756-193">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="7f756-194">双击“BizTalk Orchestration.odx”文件以打开业务流程。 </span><span class="sxs-lookup"><span data-stu-id="7f756-194">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
    <span data-ttu-id="7f756-195">![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")</span><span class="sxs-lookup"><span data-stu-id="7f756-195">![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")</span></span>  
  
   <span data-ttu-id="7f756-196">此业务流程接受已为 PeopleSoft **Get** 方法设置格式的 XML 文件作为输入，并将该 XML 文件发送到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="7f756-196">This orchestration accepts as input an XML file formatted for the PeopleSoft **Get** method and sends the XML file to the PeopleSoft system.</span></span> <span data-ttu-id="7f756-197">**Get** 方法从 PeopleSoft 系统检索位置信息并将其返回到 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="7f756-197">The **Get** method retrieves location information from the PeopleSoft system and returns it to the BizTalk orchestration.</span></span> <span data-ttu-id="7f756-198">业务流程使用端口帮助与适配器和 PeopleSoft 系统进行此类通信。</span><span class="sxs-lookup"><span data-stu-id="7f756-198">The orchestration uses ports to facilitate this communication with the adapter and the PeopleSoft system.</span></span> <span data-ttu-id="7f756-199">您将在此处配置的端口用于接收和发送 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-199">The ports you will configure here are for receiving and sending XML files.</span></span> <span data-ttu-id="7f756-200">传出 XML 文件告知 PeopleSoft 系统这是 **Get** 操作。</span><span class="sxs-lookup"><span data-stu-id="7f756-200">The outgoing XML file tells the PeopleSoft system that this is a **Get** operation.</span></span> <span data-ttu-id="7f756-201">传入 XML 文件将位置信息返回到业务流程。</span><span class="sxs-lookup"><span data-stu-id="7f756-201">The incoming XML file returns the location information to the orchestration.</span></span>  
  
   <span data-ttu-id="7f756-202">要完成业务流程，你需要创建并配置用于接收和发送 XML 文件的端口。</span><span class="sxs-lookup"><span data-stu-id="7f756-202">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="7f756-203">首先，设置一个新的接收端口，以便接受包含 **Get** 方法的初始 XML 输入文件以启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="7f756-203">First, set up a new receive port to accept the initial XML input file that contains the **Get** method to start the orchestration.</span></span>  
  
#### <a name="configure-a-receive-port"></a><span data-ttu-id="7f756-204">配置接收端口</span><span class="sxs-lookup"><span data-stu-id="7f756-204">Configure a receive port</span></span>  
  
1. <span data-ttu-id="7f756-205">在上一步中打开的 BizTalk Orchestration.odx 文件中，右键单击左侧的端口图面，然后单击“新建配置的端口” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-205">Within the BizTalk Orchestration.odx file that you opened in the previous step, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="7f756-206">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="7f756-206">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="7f756-207">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-207">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2. <span data-ttu-id="7f756-208">上**端口属性**页上，输入`FileIn`有关**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7f756-208">On the **Port Properties** page, enter `FileIn` for **Name**, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="7f756-209">在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-209">In the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
    <span data-ttu-id="7f756-210">**端口类型名称**: `FileInPort`</span><span class="sxs-lookup"><span data-stu-id="7f756-210">**Port Type Name**: `FileInPort`</span></span>  
  
    <span data-ttu-id="7f756-211">**通信模式**： **单向**</span><span class="sxs-lookup"><span data-stu-id="7f756-211">**Communication Pattern**: **One Way**</span></span>  
  
    <span data-ttu-id="7f756-212">**访问限制**： **内部 - 仅限于此项目**</span><span class="sxs-lookup"><span data-stu-id="7f756-212">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4. <span data-ttu-id="7f756-213">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="7f756-213">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
    <span data-ttu-id="7f756-214">**端口通信方向**： **始终在此端口上接收消息**</span><span class="sxs-lookup"><span data-stu-id="7f756-214">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
    <span data-ttu-id="7f756-215">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="7f756-215">**Port binding**: **Specify later**</span></span>  
  
5. <span data-ttu-id="7f756-216">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-216">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="7f756-217">您将使用文件适配器接受此文件作为来自磁盘的输入。</span><span class="sxs-lookup"><span data-stu-id="7f756-217">You will use the File adapter to accept this file as input from disk.</span></span>  
  
   <span data-ttu-id="7f756-218">接下来，创建一个发送端口，以接受包含位置结果（从调用 PeopleSoft **Get** 方法获得）的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-218">Next, create a send port to accept the XML file containing the location results from the call to the PeopleSoft **Get** method.</span></span> <span data-ttu-id="7f756-219">业务流程使用文件适配器通过此发送端口将该 XML 文件写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="7f756-219">The orchestration uses the File adapter to write that XML file to disk through this send port.</span></span>  
  
#### <a name="configure-a-send-port"></a><span data-ttu-id="7f756-220">配置发送端口</span><span class="sxs-lookup"><span data-stu-id="7f756-220">Configure a send port</span></span>  
  
1. <span data-ttu-id="7f756-221">在 BizTalk Orchestration.odx 文件中，右键单击右侧的端口图面，然后单击“新建配置的端口” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-221">Within the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="7f756-222">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="7f756-222">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="7f756-223">在“欢迎使用端口配置向导”页上，单击“下一步”。  </span><span class="sxs-lookup"><span data-stu-id="7f756-223">On the **Welcome to the Port Configuration Wizard** page click **Next**.</span></span>  
  
2. <span data-ttu-id="7f756-224">上**端口属性**页上，输入`FileOut`有关**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7f756-224">On the **Port Properties** page, enter `FileOut` for **Name**, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="7f756-225">在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-225">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
    <span data-ttu-id="7f756-226">**端口类型名称**: `FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="7f756-226">**Port Type Name**: `FileOutPort`</span></span>  
  
    <span data-ttu-id="7f756-227">**通信模式**： **单向**</span><span class="sxs-lookup"><span data-stu-id="7f756-227">**Communication Pattern**: **One Way**</span></span>  
  
    <span data-ttu-id="7f756-228">**访问限制**： **内部 - 仅限于此项目**</span><span class="sxs-lookup"><span data-stu-id="7f756-228">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4. <span data-ttu-id="7f756-229">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="7f756-229">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
    <span data-ttu-id="7f756-230">**端口通信方向**： **始终在此端口上发送消息**</span><span class="sxs-lookup"><span data-stu-id="7f756-230">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
    <span data-ttu-id="7f756-231">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="7f756-231">**Port binding**: **Specify later**</span></span>  
  
5. <span data-ttu-id="7f756-232">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-232">Click **Next**, and then click **Finish**.</span></span>  
  
   <span data-ttu-id="7f756-233">最后，创建一个发送/接收端口，以将包含 **Get** 方法的初始 XML 输入文件发送到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="7f756-233">Finally, create a send/receive port to send the initial XML input file containing the **Get** method to the PeopleSoft system.</span></span> <span data-ttu-id="7f756-234">此端口还将接收 XML 文件，该文件包含从 PeopleSoft 系统上调用 **Get** 方法获得的位置信息。</span><span class="sxs-lookup"><span data-stu-id="7f756-234">This port will also receive an XML file containing the location information that results from the **Get** method call on the PeopleSoft system.</span></span>  
  
#### <a name="configure-a-sendreceive-port"></a><span data-ttu-id="7f756-235">配置发送/接收端口</span><span class="sxs-lookup"><span data-stu-id="7f756-235">Configure a send/receive port</span></span>  
  
1. <span data-ttu-id="7f756-236">在 BizTalk Orchestration.odx 文件中，右键单击右侧的端口图面，然后单击“新建配置的端口” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-236">Within the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="7f756-237">这将启动端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="7f756-237">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="7f756-238">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-238">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2. <span data-ttu-id="7f756-239">上**端口属性**页上，输入`PeopleSoft_Port`有关**名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7f756-239">On the **Port Properties** page, enter `PeopleSoft_Port` for **Name**, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="7f756-240">在“选择端口类型”  页上，选择“使用现有端口类型” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-240">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="7f756-241">为“可用端口类型” 选择“PS_Test.LOCATION” ，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-241">For **Available Port Types**, select **PS_Test.LOCATION**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="7f756-242">![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")</span><span class="sxs-lookup"><span data-stu-id="7f756-242">![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")</span></span>  
  
4. <span data-ttu-id="7f756-243">单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：  </span><span class="sxs-lookup"><span data-stu-id="7f756-243">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
    <span data-ttu-id="7f756-244">**端口通信方向**： **我将始终发送请求并接收响应**</span><span class="sxs-lookup"><span data-stu-id="7f756-244">**Port direction of communication**: **I'll always be sending a request and receiving a response**</span></span>  
  
    <span data-ttu-id="7f756-245">**端口绑定**： **以后指定**</span><span class="sxs-lookup"><span data-stu-id="7f756-245">**Port binding**: **Specify later**</span></span>  
  
5. <span data-ttu-id="7f756-246">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-246">Click **Next**, and then click **Finish**.</span></span>  
  
   <span data-ttu-id="7f756-247">端口图面上显示的是 PeopleSoft 定位服务的新端口和可用方法。</span><span class="sxs-lookup"><span data-stu-id="7f756-247">Displayed on the port surface are the new port and the available methods for the PeopleSoft Location service.</span></span> <span data-ttu-id="7f756-248">随后您将指定 PeopleSoft 适配器，以发送和接收来自 PeopleSoft 系统的文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-248">Later you will specify the PeopleSoft adapter to send and receive files from the PeopleSoft system.</span></span>  
  
   <span data-ttu-id="7f756-249">现在，将两个“发送”  形状和两个“接收”  形状插入业务流程，以链接到您刚才创建的端口。</span><span class="sxs-lookup"><span data-stu-id="7f756-249">Now insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports you just created.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="7f756-250">添加发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="7f756-250">Add Send and Receive shapes</span></span>  
  
1. <span data-ttu-id="7f756-251">将工具箱中的“接收”  组件拖放到业务流程的起点（绿色圆圈）下。</span><span class="sxs-lookup"><span data-stu-id="7f756-251">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="7f756-252">单击**接收**形状，然后在属性窗口中输入`FromDisk`有关**名称**，并设置**激活**到`true`。</span><span class="sxs-lookup"><span data-stu-id="7f756-252">Click the **Receive** shape, and in the Properties window, enter `FromDisk` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="7f756-253">执行此操作后，此接收端口上收到传入文档时将激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="7f756-253">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2. <span data-ttu-id="7f756-254">拖动**发送**组件从工具箱拖放立即**FromDiskReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="7f756-254">Drag a **Send** component from the Toolbox and drop it immediately below the **FromDiskReceive** shape.</span></span> <span data-ttu-id="7f756-255">单击新建**发送**形状，然后在属性窗口中输入`ToPS`有关**名称**。</span><span class="sxs-lookup"><span data-stu-id="7f756-255">Click the new **Send** shape, and in the Properties window, enter `ToPS` for the **Name**.</span></span>  
  
3. <span data-ttu-id="7f756-256">拖动**接收**组件从工具箱拖放立即**to_ps**<strong>发送</strong>形状。</span><span class="sxs-lookup"><span data-stu-id="7f756-256">Drag a **Receive** component from the Toolbox and drop it immediately below the **To_PS**<strong>Send</strong> shape.</span></span> <span data-ttu-id="7f756-257">单击**接收**形状，然后在属性窗口中输入`FromPS`有关**名称**。</span><span class="sxs-lookup"><span data-stu-id="7f756-257">Click the **Receive** shape, and in the Properties window, enter `FromPS` for the **Name**.</span></span>  
  
4. <span data-ttu-id="7f756-258">拖动**发送**组件从工具箱拖放立即**From_PSReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="7f756-258">Drag a **Send** component from the Toolbox and drop it immediately below the **From_PSReceive** shape.</span></span> <span data-ttu-id="7f756-259">单击新建**发送**形状，然后在属性窗口中输入`ToDisk`有关**名称**。</span><span class="sxs-lookup"><span data-stu-id="7f756-259">Click the new **Send** shape, and in the Properties window, enter `ToDisk` for the **Name**.</span></span>  
  
   <span data-ttu-id="7f756-260">您需要先定义要处理的消息类型，然后才能将这些形状连接到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="7f756-260">Before you can connect these shapes to logical ports, you need to define the message types to be processed.</span></span> <span data-ttu-id="7f756-261">适配器需要传入（**Request** 方法）消息和传出（**Response** 方法）消息。</span><span class="sxs-lookup"><span data-stu-id="7f756-261">The adapter needs both an incoming (**Request** method) message and an outgoing (**Response** method) message.</span></span> <span data-ttu-id="7f756-262">每种方法的消息不同。</span><span class="sxs-lookup"><span data-stu-id="7f756-262">The messages for each of the methods are different.</span></span>  
  
   <span data-ttu-id="7f756-263">在此业务流程中，您仅使用 **Get-Request** 和 **Get-Response** 消息。</span><span class="sxs-lookup"><span data-stu-id="7f756-263">In this orchestration, you are only using the **Get-Request** and **Get-Response** messages.</span></span> <span data-ttu-id="7f756-264">如果业务流程正在更新数据（假设使用 **UpdateEx** 方法），则需要其他请求/响应消息。</span><span class="sxs-lookup"><span data-stu-id="7f756-264">If the orchestration were updating the data, say by using the **UpdateEx** method, it would require different Request/Response messages.</span></span>  
  
#### <a name="define-and-assign-messages-to-ports"></a><span data-ttu-id="7f756-265">定义并将消息分配到端口</span><span class="sxs-lookup"><span data-stu-id="7f756-265">Define and assign messages to ports</span></span>  
  
1.  <span data-ttu-id="7f756-266">在左侧的端口图面上，  单击 **“FileIn”** 端口上的“请求”。</span><span class="sxs-lookup"><span data-stu-id="7f756-266">On the left port surface, click **Request** on the **FileIn** port.</span></span> <span data-ttu-id="7f756-267">在“属性”窗口中，依次展开“消息类型” 和“多部分消息” ，然后单击“PS_Test.Get” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-267">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **PS_Test.Get**.</span></span>  
  
2.  <span data-ttu-id="7f756-268">在左侧的端口图面上，单击“FileOut”端口上的“请求”。  </span><span class="sxs-lookup"><span data-stu-id="7f756-268">On the left port surface, click **Request** on the **FileOut** port.</span></span> <span data-ttu-id="7f756-269">在“属性”窗口中，依次展开“消息类型” 和“多部分消息” ，然后单击“PS_Test.GetResponse” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-269">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **PS_Test.GetResponse**.</span></span>  
  
     <span data-ttu-id="7f756-270">![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")</span><span class="sxs-lookup"><span data-stu-id="7f756-270">![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")</span></span>  
  
3.  <span data-ttu-id="7f756-271">选择“FileIn”  端口，并将其传出发送箭头拖到“FromDisk”形状上的传入反向接收箭头。 </span><span class="sxs-lookup"><span data-stu-id="7f756-271">Select the **FileIn** port and drag its outgoing send arrow to the incoming converse receive arrow on the **FromDisk** shape.</span></span>  
  
4.  <span data-ttu-id="7f756-272">选择“FileOut”  端口，并将其传入反向接收箭头拖到“ToDisk”形状上的传出发送箭头。 </span><span class="sxs-lookup"><span data-stu-id="7f756-272">Select the **FileOut** port and drag its incoming converse receive arrow to the outgoing send arrow on the **ToDisk** shape.</span></span>  
  
5.  <span data-ttu-id="7f756-273">将现有的一般消息名称重命名为更具描述性的名称，以遵循正确的应用程序设计原则。</span><span class="sxs-lookup"><span data-stu-id="7f756-273">Rename existing generic message names to more descriptive names to adhere to good application design principles.</span></span> <span data-ttu-id="7f756-274">在解决方案资源管理器中，单击“业务流程视图”选项卡  。在“消息”下 ，将“Message_1”的标识符更改为“PS_Msg”。  </span><span class="sxs-lookup"><span data-stu-id="7f756-274">In Solution Explorer, click the **Orchestration View** tab. Under **Messages**, change the identifier for **Message_1** to **PS_Msg**.</span></span> <span data-ttu-id="7f756-275">将 **“Message_2”** 的标识符更改为 **“PS_Resp”**。</span><span class="sxs-lookup"><span data-stu-id="7f756-275">Change the identifier for **Message_2** to **PS_Resp**.</span></span>  
  
     <span data-ttu-id="7f756-276">![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")</span><span class="sxs-lookup"><span data-stu-id="7f756-276">![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")</span></span>  
  
     <span data-ttu-id="7f756-277">![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")</span><span class="sxs-lookup"><span data-stu-id="7f756-277">![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")</span></span>  
  
6.  <span data-ttu-id="7f756-278">突出显示“To_PS”  发送形状，并将其“消息”  属性设置为“PS_Msg” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-278">Highlight the **To_PS** send shape and set its **Message** property to **PS_Msg**.</span></span>  
  
7.  <span data-ttu-id="7f756-279">突出显示“From_PS”  接收形状，并将其“消息”  属性设置为“PS_Resp” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-279">Highlight the **From_PS** receive shape and set its **Message** property to **PS_Resp**.</span></span>  
  
8.  <span data-ttu-id="7f756-280">将 **“To_PS”** 发送形状连接到 **“PeopleSoft_Port”** 端口上“Get”方法的“请求”部分。  </span><span class="sxs-lookup"><span data-stu-id="7f756-280">Connect the **To_PS** send shape to the **Request** portion of the **Get** method on the **PeopleSoft_Port** port.</span></span>  
  
9. <span data-ttu-id="7f756-281">将 **“From_PS”** 发送形状连接到 **“PeopleSoft_Port”** 端口上“Get”方法的“响应”部分。  </span><span class="sxs-lookup"><span data-stu-id="7f756-281">Connect the **From_PS** send shape to the **Response** portion of the **Get** method on the **PeopleSoft_Port** port.</span></span>  
  
     <span data-ttu-id="7f756-282">![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")</span><span class="sxs-lookup"><span data-stu-id="7f756-282">![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")</span></span>  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="7f756-283">步骤 4： 生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="7f756-283">Step 4: Build and Deploy the Project</span></span>  
 <span data-ttu-id="7f756-284">现在，BizTalk 项目已完成，你可以生成项目并将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中。</span><span class="sxs-lookup"><span data-stu-id="7f756-284">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="7f756-285">在 Visual Studio 中，指向**Visual Studio Tools**，然后选择**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="7f756-285">In Visual Studio, point to **Visual Studio Tools**, and then select **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="7f756-286">要生成项目，您需要强名称密钥文件。在命令提示符下，输入以下内容以创建强名称密钥文件：</span><span class="sxs-lookup"><span data-stu-id="7f756-286">To build the project, you need a strong name key file.At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="7f756-287">**sn-k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="7f756-287">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="7f756-288">在“解决方案资源管理器”中，右键单击“PS_Test”  项目，然后单击“属性”  以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="7f756-288">In Solution Explorer, right-click the **PS_Test** project and then click **Properties** to launch the Project Designer for the project..</span></span>  
  
4.  <span data-ttu-id="7f756-289">单击“签名”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="7f756-289">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="7f756-290">选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-290">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="7f756-291">浏览以选择密钥文件“labs.snk” ，然后单击“打开” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-291">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="7f756-292">单击项目设计器中的“部署”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="7f756-292">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="7f756-293">设置**应用程序名称**到`PS_Test`。</span><span class="sxs-lookup"><span data-stu-id="7f756-293">Set the **Application Name** to `PS_Test`.</span></span>  
  
9. <span data-ttu-id="7f756-294">在解决方案资源管理器中，右键单击“”  项目，然后单击“生成” </span><span class="sxs-lookup"><span data-stu-id="7f756-294">In Solution Explorer, right-click the **PS_Test** project, and then click **Build.**</span></span>  
  
10. <span data-ttu-id="7f756-295">成功生成该项目后，右键单击“PS_Test”  项目，然后单击“部署” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-295">After the build completes successfully, right-click the **PS_Test** project, and then click **Deploy**.</span></span>  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="7f756-296">步骤 5： 测试应用程序和查看 XML 输出</span><span class="sxs-lookup"><span data-stu-id="7f756-296">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="7f756-297">现在，你将测试你所创建和部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f756-297">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="7f756-298">你将创建用于启动业务流程进程的 XML 文件，然后将文件夹配置为接收和发送应用程序中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-298">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="7f756-299">配置应用程序之后，将运行该应用程序并查看业务流程返回的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-299">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="7f756-300">生成查询的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="7f756-300">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="7f756-301">在解决方案资源管理器中，双击“LOCATIONService_LOCATION_x5d.xsd”  以打开该文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-301">In Solution Explorer, double-click **LOCATIONService_LOCATION_x5d.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="7f756-302">右键单击“LOCATIONService_LOCATION_x5d.xsd”  ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-302">Right-click **LOCATIONService_LOCATION_x5d.xsd** and then click **Properties**.</span></span> <span data-ttu-id="7f756-303">为“输出实例文件名”输入示例 XML 的  以下路径和文件名：</span><span class="sxs-lookup"><span data-stu-id="7f756-303">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\PS_TEST\SAMPLEQUERY.XML`  
  
3.  <span data-ttu-id="7f756-304">单击“确定” **。**</span><span class="sxs-lookup"><span data-stu-id="7f756-304">Click **OK.**</span></span> <span data-ttu-id="7f756-305">在属性窗口中，选择**\<架构\>** 并设置**根引用： 获取**。</span><span class="sxs-lookup"><span data-stu-id="7f756-305">In the Properties window, select **\<Schema\>** and set **Root Reference: Get**.</span></span>  
  
4.  <span data-ttu-id="7f756-306">右键单击“LOCATIONService_LOCATION_x5d.xsd”  ，然后单击“生成实例” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-306">Right-click **LOCATIONService_LOCATION_x5d.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="7f756-307">这将生成 **SampleQuery.xml** 文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-307">This generates the **SampleQuery.xml** file.</span></span> <span data-ttu-id="7f756-308">此文件将放入接收位置，作为适配器启动业务流程进程的输入。</span><span class="sxs-lookup"><span data-stu-id="7f756-308">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
     <span data-ttu-id="7f756-309">![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")</span><span class="sxs-lookup"><span data-stu-id="7f756-309">![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="7f756-310">配置并启动 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="7f756-310">Configure and start the BizTalk application</span></span>  
  
1. <span data-ttu-id="7f756-311">配置用于接收传入文件和发送传出文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7f756-311">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="7f756-312">转到**C:\LABS\PS_TEST**并创建两个新的子文件夹名为`FileIn`和`FileOut`。</span><span class="sxs-lookup"><span data-stu-id="7f756-312">Go to **C:\LABS\PS_TEST** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2. <span data-ttu-id="7f756-313">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，展开**BizTalk 组**，展开**应用程序**，右键单击**PS_Test** ，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7f756-313">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand **BizTalk Group**, expand **Applications**, right-click **PS_Test** and then click **Configure**.</span></span>  
  
    <span data-ttu-id="7f756-314">![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")</span><span class="sxs-lookup"><span data-stu-id="7f756-314">![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")</span></span>  
  
3. <span data-ttu-id="7f756-315">选择“Orchestration_1”  ，然后单击“主机”  下拉框。</span><span class="sxs-lookup"><span data-stu-id="7f756-315">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="7f756-316">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-316">Select **BizTalkServerApplication**.</span></span>  
  
4. <span data-ttu-id="7f756-317">下**接收端口**，单击 **\<None\>**。</span><span class="sxs-lookup"><span data-stu-id="7f756-317">Under **Receive Ports**, click **\<None\>**.</span></span> <span data-ttu-id="7f756-318">在下拉列表中，选择“新建接收端口” 。</span><span class="sxs-lookup"><span data-stu-id="7f756-318">In the drop-down list, select **New Receive Port**.</span></span>  
  
5. <span data-ttu-id="7f756-319">有关**名称**，类型`FileInPort`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7f756-319">For **Name**, type `FileInPort`, and then click **OK**.</span></span> <span data-ttu-id="7f756-320">将出现一个消息框，表明你需要指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="7f756-320">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="7f756-321">单击“确定”，然后单击“新建”。  </span><span class="sxs-lookup"><span data-stu-id="7f756-321">Click **OK**, and then click **New**.</span></span>  
  
    <span data-ttu-id="7f756-322">![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")</span><span class="sxs-lookup"><span data-stu-id="7f756-322">![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")</span></span>  
  
6. <span data-ttu-id="7f756-323">键入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-323">Type or select the following values for the properties:</span></span>  
  
    <span data-ttu-id="7f756-324">**名称**：`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="7f756-324">**Name**: `FileInLoc`</span></span>  
  
    <span data-ttu-id="7f756-325">**类型**： **文件**</span><span class="sxs-lookup"><span data-stu-id="7f756-325">**Type**: **File**</span></span>  
  
    <span data-ttu-id="7f756-326">**接收处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="7f756-326">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
    <span data-ttu-id="7f756-327">**接收管道**： **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="7f756-327">**Receive Pipeline**: **XMLReceive**</span></span>  
  
    <span data-ttu-id="7f756-328">![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")</span><span class="sxs-lookup"><span data-stu-id="7f756-328">![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")</span></span>  
  
7. <span data-ttu-id="7f756-329">单击“配置”  ，为“接收文件夹”键入 `C:\LABS\PS_TEST\FILEIN` ， ，然后单击“添加生成的项”  </span><span class="sxs-lookup"><span data-stu-id="7f756-329">Click **Configure** and type `C:\LABS\PS_TEST\FILEIN` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
    <span data-ttu-id="7f756-330">![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")</span><span class="sxs-lookup"><span data-stu-id="7f756-330">![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")</span></span>  
  
8. <span data-ttu-id="7f756-331">单击**\<无\>** 有关**PeopleSoft_Port**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="7f756-331">Click **\<None\>** for **PeopleSoft_Port** in the drop-down list.</span></span>  
  
9. <span data-ttu-id="7f756-332">选择“新建发送端口”  ，然后选择或键入以下属性值。</span><span class="sxs-lookup"><span data-stu-id="7f756-332">Select **New Send Port** and then select or type the following values for the properties.</span></span>  
  
     <span data-ttu-id="7f756-333">**名称**：`PS_Test_Port`</span><span class="sxs-lookup"><span data-stu-id="7f756-333">**Name**: `PS_Test_Port`</span></span>  
  
     <span data-ttu-id="7f756-334">**类型**： **PeopleSoft**</span><span class="sxs-lookup"><span data-stu-id="7f756-334">**Type**: **PeopleSoft**</span></span>  
  
     <span data-ttu-id="7f756-335">**发送处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="7f756-335">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="7f756-336">**管道**：“XMLTransmit”  和“XMLReceive” </span><span class="sxs-lookup"><span data-stu-id="7f756-336">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
10. <span data-ttu-id="7f756-337">单击“配置” ，然后输入以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-337">Click **Configure**, and then enter the following property values:</span></span>  
  
    1. <span data-ttu-id="7f756-338">**应用程序服务器路径**： **//Servername:9000**</span><span class="sxs-lookup"><span data-stu-id="7f756-338">**Application server path**: **//Servername:9000**</span></span>  
  
        <span data-ttu-id="7f756-339">Servername 是您的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="7f756-339">Servername is your application server.</span></span> <span data-ttu-id="7f756-340">这是特定服务器名称或 IP 地址以及此 PeopleSoft 系统的端口号。</span><span class="sxs-lookup"><span data-stu-id="7f756-340">This is the specific server name or IP address and port number for this PeopleSoft system.</span></span>  
  
    2. <span data-ttu-id="7f756-341">**JAVA_HOME**： **C:\J2SDK1.4.2_08**</span><span class="sxs-lookup"><span data-stu-id="7f756-341">**JAVA_HOME**: **C:\J2SDK1.4.2_08**</span></span>  
  
        <span data-ttu-id="7f756-342">此路径特定于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的 Java SDK 安装。</span><span class="sxs-lookup"><span data-stu-id="7f756-342">This path is specific to the Java SDK installation on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    3. <span data-ttu-id="7f756-343">**密码**:\<输入您的 PeopleSoft 密码\></span><span class="sxs-lookup"><span data-stu-id="7f756-343">**Password**: \<enter your PeopleSoft password\></span></span>  
  
    4. <span data-ttu-id="7f756-344">**PeopleSoft 8.x JAR 文件**： **C:\PSJARS\VER841\PSJOA.JAR**</span><span class="sxs-lookup"><span data-stu-id="7f756-344">**PeopleSoft 8.x JAR files**: **C:\PSJARS\VER841\PSJOA.JAR**</span></span>  
  
       <span data-ttu-id="7f756-345">**用户名：** \<输入你的 PeopleSoft 用户\></span><span class="sxs-lookup"><span data-stu-id="7f756-345">**User name:** \<enter your PeopleSoft UserID\></span></span>  
  
11. <span data-ttu-id="7f756-346">单击“确定”  两次以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="7f756-346">Click **OK** twice to close the dialog boxes.</span></span>  
  
12. <span data-ttu-id="7f756-347">在配置 Applicationwindow 中，单击**\<无\>** 有关**FileOut**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="7f756-347">In the Configure Applicationwindow, click **\<None\>** for **FileOut** in the drop-down list.</span></span>  
  
13. <span data-ttu-id="7f756-348">选择“新建发送端口”  ，然后键入或选择以下属性值：</span><span class="sxs-lookup"><span data-stu-id="7f756-348">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="7f756-349">**名称**：`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="7f756-349">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="7f756-350">**类型**： **文件**</span><span class="sxs-lookup"><span data-stu-id="7f756-350">**Type**: **File**</span></span>  
  
     <span data-ttu-id="7f756-351">**发送处理程序**： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="7f756-351">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="7f756-352">**发送管道**： **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="7f756-352">**Send Pipeline**: **XMLTransmit**</span></span>  
  
14. <span data-ttu-id="7f756-353">单击“配置”  ，为“接收文件夹”键入`C:\Labs\PS_Test\FileOut` ， **C:\Labs\PS_Test\FileOut**</span><span class="sxs-lookup"><span data-stu-id="7f756-353">Click **Configure** and type`C:\Labs\PS_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="7f756-354">。为“文件名”保留“”，因为这会为每个消息生成唯一的文件。  ，  because this results in a unique file ， each message.</span><span class="sxs-lookup"><span data-stu-id="7f756-354">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
15. <span data-ttu-id="7f756-355">单击“确定”三次  以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="7f756-355">Click **OK** three times to close the dialog boxes.</span></span>  
  
16. <span data-ttu-id="7f756-356">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右击**PS_Test**应用程序，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7f756-356">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **PS_Test** application and then click **Start**.</span></span>  
  
     <span data-ttu-id="7f756-357">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span><span class="sxs-lookup"><span data-stu-id="7f756-357">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="7f756-358">测试业务流程</span><span class="sxs-lookup"><span data-stu-id="7f756-358">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="7f756-359">在 **“C:\Labs\PS_Test”** 目录中，将 **Samplequery.xml** 文件更改为以下内容：</span><span class="sxs-lookup"><span data-stu-id="7f756-359">In the **C:\Labs\PS_Test** directory, change the **Samplequery.xml** file to the following:</span></span>  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>AUS01</ns0:LOCATION>  
      <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="7f756-360">所有系统上都将使用 **SHARE** 数据值。</span><span class="sxs-lookup"><span data-stu-id="7f756-360">The **SHARE** data value will be used on all systems.</span></span> <span data-ttu-id="7f756-361">但您的系统上必须存在要用于此 XML 文件中的 **Location** 的值。</span><span class="sxs-lookup"><span data-stu-id="7f756-361">However the value you will use for **Location** in this XML file must exist on your system.</span></span> <span data-ttu-id="7f756-362">您会在实验室 1 中发现这一点。</span><span class="sxs-lookup"><span data-stu-id="7f756-362">You found this out in Lab 1.</span></span>  
  
2.  <span data-ttu-id="7f756-363">保存更改并将文件复制到 **C:\Labs\PS_Test\FileIn** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7f756-363">Save the changes and copy the file to the **C:\Labs\PS_Test\FileIn** folder.</span></span> <span data-ttu-id="7f756-364">这是用于启动业务流程进程的 FileIn 的接收位置。</span><span class="sxs-lookup"><span data-stu-id="7f756-364">This is the receive location for FileIn that starts the orchestration process.</span></span>  
  
3.  <span data-ttu-id="7f756-365">几秒钟之后， **C:\Labs\PS_Test\FileOut** 文件夹中应出现一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7f756-365">In a few seconds, an XML file should appear in the **C:\Labs\PS_Test\FileOut** folder.</span></span> <span data-ttu-id="7f756-366">此文件应包含的记录（记录了位置为 AUS01）中的数据。</span><span class="sxs-lookup"><span data-stu-id="7f756-366">This should contain the data from the record where the location is AUS01.</span></span>  
  
     <span data-ttu-id="7f756-367">![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")</span><span class="sxs-lookup"><span data-stu-id="7f756-367">![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")</span></span>  
  
     <span data-ttu-id="7f756-368">这些返回的记录数据应与在 PeopleSoft 练习 1 中针对 PeopleSoft 系统的查询所返回的结果相匹配。</span><span class="sxs-lookup"><span data-stu-id="7f756-368">This returned record data should match what was returned by the query against the PeopleSoft system in PeopleSoft Lab 1.</span></span> <span data-ttu-id="7f756-369">通过比较的值获取在实验室 1 中专门**地址 1**并**Address2**行，在此处显示**\<位置： 地址 1\>** 并**\<位置： ADDRESS2\>** 字段中，你可以验证**获取**方法正常工作。</span><span class="sxs-lookup"><span data-stu-id="7f756-369">By comparing the values you obtained in Lab 1, specifically the **Address1** and **Address2** lines, to what is shown here in the **\<LOCATION:ADDRESS1\>** and **\<LOCATION:ADDRESS2\>** fields, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7f756-370">总结</span><span class="sxs-lookup"><span data-stu-id="7f756-370">Summary</span></span>  
 <span data-ttu-id="7f756-371">在本实验室中，您首先验证了必备组件的设置对于访问 PeopleSoft 系统是否正确。</span><span class="sxs-lookup"><span data-stu-id="7f756-371">In this lab, you first verified that the prerequisites were set up correctly to access the PeopleSoft system.</span></span> <span data-ttu-id="7f756-372">然后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建了包含业务流程的新 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7f756-372">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="7f756-373">对 BizTalk 业务流程进行了配置，以使用 PeopleSoft 适配器获取来自 PeopleSoft 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="7f756-373">You configured the BizTalk orchestration to use the PeopleSoft adapter to get data from the PeopleSoft system.</span></span> <span data-ttu-id="7f756-374">为配置业务流程，你创建了发送端口、接收端口和发送/接收端口。</span><span class="sxs-lookup"><span data-stu-id="7f756-374">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="7f756-375">将这些端口绑定到 PeopleSoft 适配器，并将消息分配给相应的端口。</span><span class="sxs-lookup"><span data-stu-id="7f756-375">You bound these ports to the PeopleSoft adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="7f756-376">完成 BizTalk 项目后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 来生成和部署该项目。</span><span class="sxs-lookup"><span data-stu-id="7f756-376">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="7f756-377">随后，配置了新应用程序，并运行该应用程序，以获取来自 PeopleSoft 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="7f756-377">You then configured your new application and ran it to get data from the PeopleSoft system.</span></span> <span data-ttu-id="7f756-378">为了验证应用程序是否正常运行，您将其输出 XML 文件与在实验室 1 中从 PeopleSoft 系统接收到的文件进行了比较。</span><span class="sxs-lookup"><span data-stu-id="7f756-378">To verify that the application worked correctly, you compared its output XML file to the file that you received from the PeopleSoft system in Lab 1.</span></span>