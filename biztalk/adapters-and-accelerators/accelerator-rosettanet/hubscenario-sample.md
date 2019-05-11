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
ms.openlocfilehash: bcd7f7d08e1451bfe50d2558b8f7c6b24d897957
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283604"
---
# <a name="hubscenario-sample"></a><span data-ttu-id="84b01-102">HubScenario 示例</span><span class="sxs-lookup"><span data-stu-id="84b01-102">HubScenario Sample</span></span>
<span data-ttu-id="84b01-103">HubScenario 示例演示如何管理集线器方案中的消息传输。</span><span class="sxs-lookup"><span data-stu-id="84b01-103">The HubScenario sample demonstrates how to manage message transmission in a hub scenario.</span></span> <span data-ttu-id="84b01-104">它会将转换为消息要发送到最终接收人发送到中间网络集线器的消息。</span><span class="sxs-lookup"><span data-stu-id="84b01-104">It transforms a message sent to an intermediary hub into a message to be sent to the final recipient.</span></span>  
  
 <span data-ttu-id="84b01-105">HubScenario 从服务内容中提取最终接收人的邓氏数。</span><span class="sxs-lookup"><span data-stu-id="84b01-105">HubScenario extracts the DUNS number of the final recipient from the service content.</span></span> <span data-ttu-id="84b01-106">它管理签名和加密证书和目标 URL。</span><span class="sxs-lookup"><span data-stu-id="84b01-106">It manages signing and encryption certificates, and the destination URL.</span></span> <span data-ttu-id="84b01-107">为最终接收人生成一封新邮件。</span><span class="sxs-lookup"><span data-stu-id="84b01-107">It generates a new message for the final recipient.</span></span>  
  
 <span data-ttu-id="84b01-108">此示例处理 3A4 请求和响应消息和 0 C 1 个请求消息。</span><span class="sxs-lookup"><span data-stu-id="84b01-108">This sample handles 3A4 request and response messages, and 0C1 request messages.</span></span> <span data-ttu-id="84b01-109">当你使用 HubScenario 创建您的要求的应用程序时，必须生成为每个消息合作伙伴接口流程 (PIP) 的例程。</span><span class="sxs-lookup"><span data-stu-id="84b01-109">When you use HubScenario to create an application for your purposes, you will have to generate routines for each message Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="84b01-110">HubScenario 示例包含 hubhelper.cs 项目和 HubScenario.odx 项目。</span><span class="sxs-lookup"><span data-stu-id="84b01-110">The HubScenario sample includes HubHelper.cs and HubScenario.odx projects.</span></span>  
  
 <span data-ttu-id="84b01-111">HubScenario 示例还包括可用于导入绑定接收端口 (MessagesToLOB_Receive_Port) 和接收位置 (MessagesToLOB_Receive_Location) 的绑定文件，以用于 HubScenario.odx 业务流程。</span><span class="sxs-lookup"><span data-stu-id="84b01-111">The HubScenario sample also includes a binding file that you can use to import bindings for a receive port (MessagesToLOB_Receive_Port) and receive location (MessagesToLOB_Receive_Location) for use with the HubScenario.odx orchestration.</span></span> <span data-ttu-id="84b01-112">此绑定文件 (HubScenarioBinding.xml) 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet \SDK\HubScenario。</span><span class="sxs-lookup"><span data-stu-id="84b01-112">This binding file (HubScenarioBinding.xml) is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\HubScenario.</span></span> <span data-ttu-id="84b01-113">使用 BTSTask 命令导入绑定。</span><span class="sxs-lookup"><span data-stu-id="84b01-113">Use the BTSTask command to import the bindings.</span></span> <span data-ttu-id="84b01-114">有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。</span><span class="sxs-lookup"><span data-stu-id="84b01-114">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="84b01-115">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="84b01-115">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="84b01-116">在 Visual Studio 中打开\<驱动器\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj。</span><span class="sxs-lookup"><span data-stu-id="84b01-116">In Visual Studio, open \<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj.</span></span> <span data-ttu-id="84b01-117">在解决方案资源管理器，右键单击 HubScenario 项目，然后单击属性。</span><span class="sxs-lookup"><span data-stu-id="84b01-117">In Solution Explorer, right-click the HubScenario project, and then click Properties.</span></span> <span data-ttu-id="84b01-118">在 HubScenario 项目的属性页中，在签名选项卡上选择**为程序集签名**复选框，然后选择**HubScenario.snk**中**选择强名称密钥文件**并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="84b01-118">In the Properties page for the HubScenario project, in the Signing tab select **Sign the assembly** checkbox, and select **HubScenario.snk** in **Choose a strong name key file** and click **Ok**.</span></span>  
  
2. <span data-ttu-id="84b01-119">在解决方案资源管理器，右键单击 HubHelper 项目，然后单击属性。</span><span class="sxs-lookup"><span data-stu-id="84b01-119">In Solution Explorer, right-click the HubHelper project, and then click Properties.</span></span> <span data-ttu-id="84b01-120">在 HubHelper 项目属性页中，在签名选项卡中选中签名程序集复选框。</span><span class="sxs-lookup"><span data-stu-id="84b01-120">In the Properties page for the HubHelper project, in the Signing tab check Sign the assembly checkbox.</span></span> <span data-ttu-id="84b01-121">在选择强名称密钥文件字段中，选择新的类型**HubHelper.snk**作为密钥文件名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="84b01-121">In Choose a strong name key file field, select new type **HubHelper.snk** as Key file name and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="84b01-122">如果你没有在 HubScenario 和 HubHelper 项目中手动输入程序集密钥文件，将不会部署程序集。</span><span class="sxs-lookup"><span data-stu-id="84b01-122">If you do not manually enter the assembly key file in the HubScenario and HubHelper projects, the assemblies will not deploy.</span></span>  
  
3. <span data-ttu-id="84b01-123">在命令提示符处，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario 文件夹。</span><span class="sxs-lookup"><span data-stu-id="84b01-123">At a command prompt, move to *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario folder.</span></span> <span data-ttu-id="84b01-124">运行文件 Setup.bat （或在 64 位计算机上运行 Setupx64.bat）。</span><span class="sxs-lookup"><span data-stu-id="84b01-124">Run the file Setup.bat (or on a 64-bit computer, run Setupx64.bat).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="84b01-125">演示</span><span class="sxs-lookup"><span data-stu-id="84b01-125">Demonstrates</span></span>  
 <span data-ttu-id="84b01-126">HubScenario.ods 业务流程演示如何执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="84b01-126">The HubScenario.ods orchestration demonstrates how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="84b01-127">从业务线应用程序接收的消息。</span><span class="sxs-lookup"><span data-stu-id="84b01-127">Receives the message from the line-of-business application.</span></span>  
  
2. <span data-ttu-id="84b01-128">删除`CDATA`服务内容，返回 XML 字符串中的元素。</span><span class="sxs-lookup"><span data-stu-id="84b01-128">Removes the `CDATA` element from the service content, returning the XML string.</span></span>  
  
3. <span data-ttu-id="84b01-129">检索最后一条消息的目标参与方名称、 PIPCode、 PIPInstanceID 和 PIPVersion。</span><span class="sxs-lookup"><span data-stu-id="84b01-129">Retrieves the destination party name, PIPCode, PIPInstanceID, and PIPVersion for the final message.</span></span>  
  
4. <span data-ttu-id="84b01-130">检索最终接收人的邓氏数。</span><span class="sxs-lookup"><span data-stu-id="84b01-130">Retrieves the DUNS number for the final recipient.</span></span>  
  
5. <span data-ttu-id="84b01-131">确定消息的类别，并添加包含对服务内容到相应的架构的引用的 DOCTYPE 元素。</span><span class="sxs-lookup"><span data-stu-id="84b01-131">Determines the category of the message, and adds the DOCTYPE element that contains a reference to the appropriate schema to the service content.</span></span>  
  
6. <span data-ttu-id="84b01-132">构造新的目标参与方名称、 邓氏、 PIP 代码信息和服务内容的消息。</span><span class="sxs-lookup"><span data-stu-id="84b01-132">Constructs a message with the new destination party name, DUNS number, PIP code information, and service content.</span></span>  
  
7. <span data-ttu-id="84b01-133">提交消息以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84b01-133">Submits the message for processing by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="84b01-134">这是调用`SubmitRNIF.SubmitMessage`。</span><span class="sxs-lookup"><span data-stu-id="84b01-134">This is a call to `SubmitRNIF.SubmitMessage`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b01-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="84b01-135">See Also</span></span>  
 <span data-ttu-id="84b01-136">[示例基于中心的方案](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84b01-136">[Sample Hub-Based Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span></span>  
 [<span data-ttu-id="84b01-137">业务流程示例</span><span class="sxs-lookup"><span data-stu-id="84b01-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)