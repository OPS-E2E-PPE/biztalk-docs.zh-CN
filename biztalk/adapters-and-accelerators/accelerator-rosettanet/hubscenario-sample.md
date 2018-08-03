---
title: HubScenario 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b3274108d6a8cac25e58958a6bdea530027f36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970198"
---
# <a name="hubscenario-sample"></a><span data-ttu-id="92ea5-102">HubScenario 示例</span><span class="sxs-lookup"><span data-stu-id="92ea5-102">HubScenario Sample</span></span>
<span data-ttu-id="92ea5-103">HubScenario 示例演示在网络集线器方案中如何管理消息传输。</span><span class="sxs-lookup"><span data-stu-id="92ea5-103">The HubScenario sample demonstrates how to manage message transmission in a hub scenario.</span></span> <span data-ttu-id="92ea5-104">该示例将发送到中间网络集线器的消息转换为发送到最终接收人的消息。</span><span class="sxs-lookup"><span data-stu-id="92ea5-104">It transforms a message sent to an intermediary hub into a message to be sent to the final recipient.</span></span>  
  
 <span data-ttu-id="92ea5-105">HubScenario 从服务内容中提取最终接收人的邓氏 (DUNS) 编码。</span><span class="sxs-lookup"><span data-stu-id="92ea5-105">HubScenario extracts the DUNS number of the final recipient from the service content.</span></span> <span data-ttu-id="92ea5-106">它管理签名证书、加密证书和目标 URL，</span><span class="sxs-lookup"><span data-stu-id="92ea5-106">It manages signing and encryption certificates, and the destination URL.</span></span> <span data-ttu-id="92ea5-107">并为最终接收人生成一条新消息。</span><span class="sxs-lookup"><span data-stu-id="92ea5-107">It generates a new message for the final recipient.</span></span>  
  
 <span data-ttu-id="92ea5-108">此示例处理 3A4 请求与响应消息以及 0C1 请求消息。</span><span class="sxs-lookup"><span data-stu-id="92ea5-108">This sample handles 3A4 request and response messages, and 0C1 request messages.</span></span> <span data-ttu-id="92ea5-109">当你使用 HubScenario 创建用于个人目的的应用程序时，必须为每个消息合作伙伴接口流程 (PIP) 都生成例程。</span><span class="sxs-lookup"><span data-stu-id="92ea5-109">When you use HubScenario to create an application for your purposes, you will have to generate routines for each message Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="92ea5-110">HubScenario 示例包含 HubHelper.cs 项目和 HubScenario.odx 项目。</span><span class="sxs-lookup"><span data-stu-id="92ea5-110">The HubScenario sample includes HubHelper.cs and HubScenario.odx projects.</span></span>  
  
 <span data-ttu-id="92ea5-111">HubScenario 示例还包含一个绑定文件，可以用于导入接收端口 (MessagesToLOB_Receive_Port) 和接收位置 (MessagesToLOB_Receive_Location) 之间的绑定，以用于 HubScenario.odx 业务流程。</span><span class="sxs-lookup"><span data-stu-id="92ea5-111">The HubScenario sample also includes a binding file that you can use to import bindings for a receive port (MessagesToLOB_Receive_Port) and receive location (MessagesToLOB_Receive_Location) for use with the HubScenario.odx orchestration.</span></span> <span data-ttu-id="92ea5-112">此绑定文件 (HubScenarioBinding.xml) 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet \SDK\HubScenario。</span><span class="sxs-lookup"><span data-stu-id="92ea5-112">This binding file (HubScenarioBinding.xml) is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\HubScenario.</span></span> <span data-ttu-id="92ea5-113">使用 BTSTask 命令可以导入绑定。</span><span class="sxs-lookup"><span data-stu-id="92ea5-113">Use the BTSTask command to import the bindings.</span></span> <span data-ttu-id="92ea5-114">有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。</span><span class="sxs-lookup"><span data-stu-id="92ea5-114">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="92ea5-115">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="92ea5-115">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="92ea5-116">在 Visual Studio 中打开\<驱动器\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj。</span><span class="sxs-lookup"><span data-stu-id="92ea5-116">In Visual Studio, open \<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj.</span></span> <span data-ttu-id="92ea5-117">在解决方案资源管理器中，右键单击 HubScenario 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="92ea5-117">In Solution Explorer, right-click the HubScenario project, and then click Properties.</span></span> <span data-ttu-id="92ea5-118">在 HubScenario 项目的属性页中，在签名选项卡上选择**为程序集签名**复选框，然后选择**HubScenario.snk**中**选择强名称密钥文件**并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="92ea5-118">In the Properties page for the HubScenario project, in the Signing tab select **Sign the assembly** checkbox, and select **HubScenario.snk** in **Choose a strong name key file** and click **Ok**.</span></span>  
  
2. <span data-ttu-id="92ea5-119">在解决方案资源管理器中，右键单击 HubHelper 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="92ea5-119">In Solution Explorer, right-click the HubHelper project, and then click Properties.</span></span> <span data-ttu-id="92ea5-120">在 HubHelper 项目的“属性”页中，在“签名”选项卡中选中“为程序集签名”复选框。</span><span class="sxs-lookup"><span data-stu-id="92ea5-120">In the Properties page for the HubHelper project, in the Signing tab check Sign the assembly checkbox.</span></span> <span data-ttu-id="92ea5-121">在选择强名称密钥文件字段中，选择新的类型**HubHelper.snk**作为密钥文件名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="92ea5-121">In Choose a strong name key file field, select new type **HubHelper.snk** as Key file name and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="92ea5-122">如果没有在 HubScenario 和 HubHelper 项目中手动输入程序集密钥文件，则这些程序集将不会进行部署。</span><span class="sxs-lookup"><span data-stu-id="92ea5-122">If you do not manually enter the assembly key file in the HubScenario and HubHelper projects, the assemblies will not deploy.</span></span>  
  
3. <span data-ttu-id="92ea5-123">在命令提示符处，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario 文件夹。</span><span class="sxs-lookup"><span data-stu-id="92ea5-123">At a command prompt, move to *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario folder.</span></span> <span data-ttu-id="92ea5-124">运行文件 Setup.bat（如果在 64 位计算机上，则运行 Setupx64.bat）。</span><span class="sxs-lookup"><span data-stu-id="92ea5-124">Run the file Setup.bat (or on a 64-bit computer, run Setupx64.bat).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="92ea5-125">演示</span><span class="sxs-lookup"><span data-stu-id="92ea5-125">Demonstrates</span></span>  
 <span data-ttu-id="92ea5-126">HubScenario.ods 业务流程演示如何执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="92ea5-126">The HubScenario.ods orchestration demonstrates how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="92ea5-127">从业务线应用程序接收消息。</span><span class="sxs-lookup"><span data-stu-id="92ea5-127">Receives the message from the line-of-business application.</span></span>  
  
2. <span data-ttu-id="92ea5-128">删除服务内容中的 `CDATA` 元素，返回 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="92ea5-128">Removes the `CDATA` element from the service content, returning the XML string.</span></span>  
  
3. <span data-ttu-id="92ea5-129">检索最终消息的目标参与方名称、PIPCode、PIPInstanceID 和 PIPVersion。</span><span class="sxs-lookup"><span data-stu-id="92ea5-129">Retrieves the destination party name, PIPCode, PIPInstanceID, and PIPVersion for the final message.</span></span>  
  
4. <span data-ttu-id="92ea5-130">检索最终接收人的邓氏 (DUNS) 编码。</span><span class="sxs-lookup"><span data-stu-id="92ea5-130">Retrieves the DUNS number for the final recipient.</span></span>  
  
5. <span data-ttu-id="92ea5-131">确定消息的类别，向服务内容添加包含对适当架构的引用的 DOCTYPE 元素。</span><span class="sxs-lookup"><span data-stu-id="92ea5-131">Determines the category of the message, and adds the DOCTYPE element that contains a reference to the appropriate schema to the service content.</span></span>  
  
6. <span data-ttu-id="92ea5-132">使用新的目标参与方名称、邓氏 (DUNS) 编码、PIP 代码信息和服务内容构造一条消息。</span><span class="sxs-lookup"><span data-stu-id="92ea5-132">Constructs a message with the new destination party name, DUNS number, PIP code information, and service content.</span></span>  
  
7. <span data-ttu-id="92ea5-133">提交消息以供 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 进行处理。</span><span class="sxs-lookup"><span data-stu-id="92ea5-133">Submits the message for processing by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="92ea5-134">这是对 `SubmitRNIF.SubmitMessage` 的一个调用。</span><span class="sxs-lookup"><span data-stu-id="92ea5-134">This is a call to `SubmitRNIF.SubmitMessage`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ea5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="92ea5-135">See Also</span></span>  
 <span data-ttu-id="92ea5-136">[示例基于中心的方案](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="92ea5-136">[Sample Hub-Based Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span></span>  
 [<span data-ttu-id="92ea5-137">业务流程示例</span><span class="sxs-lookup"><span data-stu-id="92ea5-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)