---
title: 使用业务规则的 3A4 专用响应方业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33d87952-def6-4202-b535-3d80171332eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6af8d06ddda2019982bd3ba83bf5d638208c2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285030"
---
# <a name="3a4-private-responder-orchestration-using-a-business-rule"></a><span data-ttu-id="9deba-102">使用业务规则的 3A4 专用响应方业务流程</span><span class="sxs-lookup"><span data-stu-id="9deba-102">3A4 Private Responder Orchestration Using a Business Rule</span></span>
<span data-ttu-id="9deba-103">PIP3A4PrivateResponder.odx 示例是演示如何实现合作伙伴接口流程 (PIP) 的专用流程业务流程的特定响应方专用流程合并了业务规则。</span><span class="sxs-lookup"><span data-stu-id="9deba-103">The PIP3A4PrivateResponder.odx sample is a private-process orchestration that demonstrates how to implement a Partner Interface Process (PIP)-specific responder private process incorporating a business rule.</span></span> <span data-ttu-id="9deba-104">有关此过程的详细信息，请参阅[专用业务流程中定义的业务规则](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="9deba-104">For more information about this process, see [Defining a Business Rule for a Private Process Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md).</span></span>  
  
 <span data-ttu-id="9deba-105">默认情况下，Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序将安装中的示例\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PipAutomation\3A4。</span><span class="sxs-lookup"><span data-stu-id="9deba-105">By default, the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Setup program installs the sample in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9deba-106">过程</span><span class="sxs-lookup"><span data-stu-id="9deba-106">Procedures</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="9deba-107">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="9deba-107">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="9deba-108">在命令提示符处，找到 *\<驱动器\>* : files\ Microsoft BizTalk Accelerator for RosettaNet\<版本\>\SDK\PIPAutomation\3A4 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9deba-108">At a command prompt, locate the *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for RosettaNet \<version\>\SDK\PIPAutomation\3A4 folder.</span></span>  
  
2.  <span data-ttu-id="9deba-109">运行文件 Setup.bat，以使用 Binding.xml 绑定文件来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9deba-109">Run the file Setup.bat, which uses the Binding.xml binding file to perform the following actions:</span></span>  
  
    -   <span data-ttu-id="9deba-110">编译 Helper 项目，并在全局程序集缓存中注册该程序集。</span><span class="sxs-lookup"><span data-stu-id="9deba-110">Compiles the Helper project and registers the assembly in the global assembly cache.</span></span>  
  
    -   <span data-ttu-id="9deba-111">编译 PIP3APrivateResponder 项目，并在全局程序集缓存中注册该程序集。</span><span class="sxs-lookup"><span data-stu-id="9deba-111">Compiles the PIP3APrivateResponder project and registers the assembly in the global assembly cache.</span></span>  
  
    -   <span data-ttu-id="9deba-112">创建 LOB_To_PrivateResponder 接收端口。</span><span class="sxs-lookup"><span data-stu-id="9deba-112">Creates the LOB_To_PrivateResponder receive port.</span></span>  
  
    -   <span data-ttu-id="9deba-113">创建 LOB_To_PrivateResponder 接收位置。</span><span class="sxs-lookup"><span data-stu-id="9deba-113">Creates the LOB_To_PrivateResponder receive location.</span></span>  
  
    -   <span data-ttu-id="9deba-114">创建并启动 PrivateResponder_To_LOB 发送端口。</span><span class="sxs-lookup"><span data-stu-id="9deba-114">Creates and starts the PrivateResponder_To_LOB send port.</span></span>  
  
    -   <span data-ttu-id="9deba-115">编译并部署 PIP3A4PrivateResponderProcess 业务流程。</span><span class="sxs-lookup"><span data-stu-id="9deba-115">Compiles and deploys the PIP3A4PrivateResponderProcess orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9deba-116">必须完成 PIP3A4PrivateResponderProcess 业务流程使用 BizTalk 浏览器的端口绑定配置。</span><span class="sxs-lookup"><span data-stu-id="9deba-116">You must complete the port binding configuration of the PIP3A4PrivateResponderProcess orchestration using BizTalk Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9deba-117">若要撤消 setup.bat 所做的更改，请手动取消登记 PIP3A4PrivateResponder.odx 业务流程、 取消部署 Helper 和 PIP3A4PrivateResponder 程序集，并取消部署，然后删除 samplebtarnpolicy 规则策略。</span><span class="sxs-lookup"><span data-stu-id="9deba-117">To undo changes made by setup.bat, manually unenlist the PIP3A4PrivateResponder.odx orchestration, undeploy the Helper and PIP3A4PrivateResponder assemblies, and undeploy and then delete the samplebtarnpolicy rules policy.</span></span> <span data-ttu-id="9deba-118">不能使用中的 Cleanup.bat *\<驱动器\>* : files\ Microsoft BizTalk Accelerator for RosettaNet\<版本\>\SDK\PIPAutomation\3A4 文件夹，若要撤消更改setup.bat 所做的。</span><span class="sxs-lookup"><span data-stu-id="9deba-118">You cannot use Cleanup.bat in the *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for RosettaNet \<version\>\SDK\PIPAutomation\3A4 folder to undo changes made by setup.bat.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9deba-119">演示</span><span class="sxs-lookup"><span data-stu-id="9deba-119">Demonstrates</span></span>  
 <span data-ttu-id="9deba-120">此示例订阅 3A4 请求操作和信号消息。</span><span class="sxs-lookup"><span data-stu-id="9deba-120">This sample subscribes 3A4 request action and signal messages.</span></span> <span data-ttu-id="9deba-121">它适用于这两个 3A4 同步和异步进程。</span><span class="sxs-lookup"><span data-stu-id="9deba-121">It works in both 3A4 synchronous and asynchronous processes.</span></span> <span data-ttu-id="9deba-122">所有其他 PIP 消息仍通过通用路由[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]专用流程。</span><span class="sxs-lookup"><span data-stu-id="9deba-122">All other PIP messages still route through the generic [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] private process.</span></span> <span data-ttu-id="9deba-123">此示例调用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务规则引擎，并将传递给规则引擎将传入 3A4 请求消息。</span><span class="sxs-lookup"><span data-stu-id="9deba-123">This sample invokes the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Business Rule Engine, and passes to the Rule Engine the incoming 3A4 request message.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="9deba-124">提供了一个名为中的 samplebtarnpolicy.xml 的示例业务规则策略\<*驱动器*\>: files\ Microsoft BizTalk Accelerator for RosettaNet\<版本\>\SDK\PipAutomation\3A4。</span><span class="sxs-lookup"><span data-stu-id="9deba-124">provides a sample business-rule policy named samplebtarnpolicy.xml in \<*drive*\>:\Program Files\ Microsoft BizTalk Accelerator for RosettaNet \<version\>\SDK\PipAutomation\3A4.</span></span> <span data-ttu-id="9deba-125">有关详细信息，请参阅[BTARN 业务策略示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9deba-125">For more information, see [Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span></span>  
  
 <span data-ttu-id="9deba-126">若要使用示例，请设置业务规则。</span><span class="sxs-lookup"><span data-stu-id="9deba-126">To work with the sample, set up a business rule.</span></span> <span data-ttu-id="9deba-127">如果消息满足业务规则中，则该过程将传入操作消息保存在 MessagesToLOB 表中，将传递状态设置为 2。</span><span class="sxs-lookup"><span data-stu-id="9deba-127">If the message meets the business rule, then the process saves the incoming action message in the MessagesToLOB table, setting the Delivered Status to 2.</span></span> <span data-ttu-id="9deba-128">传递列的值必须为非零，以便业务线应用程序知道它无需生成此请求的确认消息。</span><span class="sxs-lookup"><span data-stu-id="9deba-128">The Delivered column value must be nonzero, so that the line-of-business application knows that it does not have to generate a confirmation for this request.</span></span> <span data-ttu-id="9deba-129">进程，然后将 3A4 请求消息映射为 3A4 确认消息，并提交给 MessageStorageIn 表使用响应`SubmitRNIF`方法。</span><span class="sxs-lookup"><span data-stu-id="9deba-129">The process then maps the 3A4 request message to a 3A4 confirmation message, and submits the response to the MessageStorageIn table using the `SubmitRNIF` method.</span></span>  
  
 <span data-ttu-id="9deba-130">如果消息不满足业务规则，该过程将传入操作消息保存在 MessageStorageOut 表中，并将传递状态设置为 0。</span><span class="sxs-lookup"><span data-stu-id="9deba-130">If the message does not meet the business rule, the process saves the incoming action message in the MessageStorageOut table, and sets Delivered Status to 0.</span></span>  
  
 <span data-ttu-id="9deba-131">此示例包含可用于设置发送端口 (PrivateResponder_To_LOB)、 接收端口 (LOB_To_PrivateResponder) 和接收位置 (LOB_To_PrivateResponder) 用于 PIP3A4PrivateResponder.odx 一个绑定文件 (Binding.xml)业务流程。</span><span class="sxs-lookup"><span data-stu-id="9deba-131">This sample includes a binding file (Binding.xml) that you can use to set up a send port (PrivateResponder_To_LOB), a receive port (LOB_To_PrivateResponder), and a receive location (LOB_To_PrivateResponder) for use with the PIP3A4PrivateResponder.odx orchestration.</span></span> <span data-ttu-id="9deba-132">使用 BTSTask 命令导入 Binding.xml 文件中的绑定。</span><span class="sxs-lookup"><span data-stu-id="9deba-132">Use the BTSTask command to import the bindings in the Binding.xml file.</span></span> <span data-ttu-id="9deba-133">有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。</span><span class="sxs-lookup"><span data-stu-id="9deba-133">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9deba-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="9deba-134">See Also</span></span>  
 <span data-ttu-id="9deba-135">[双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="9deba-135">[Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md) </span></span>  
 <span data-ttu-id="9deba-136">[BTARN 业务策略示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span><span class="sxs-lookup"><span data-stu-id="9deba-136">[Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span></span>  
 [<span data-ttu-id="9deba-137">业务流程示例</span><span class="sxs-lookup"><span data-stu-id="9deba-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)