---
title: LOBApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9859e210036806cebcd76f63235d47ca972976
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978574"
---
# <a name="lobapplication"></a><span data-ttu-id="b98e5-102">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="b98e5-102">LOBApplication</span></span>
<span data-ttu-id="b98e5-103">使用 LOBApplication 实用工具可以将操作或响应消息提交给贸易合作伙伴，并模拟实际的业务线 (LOB) 桌面程序。</span><span class="sxs-lookup"><span data-stu-id="b98e5-103">You use the LOBApplication utility to submit an action or response message to a trading partner, simulating an actual line-of-business (LOB) desktop program.</span></span>  
  
 <span data-ttu-id="b98e5-104">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供了示例消息中的\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b98e5-104">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides sample messages in the \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="b98e5-105">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="b98e5-105">Location in SDK</span></span>  
 <span data-ttu-id="b98e5-106">\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication</span><span class="sxs-lookup"><span data-stu-id="b98e5-106">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication</span></span>  
  
## <a name="running-lobapplication"></a><span data-ttu-id="b98e5-107">运行 LOBApplication</span><span class="sxs-lookup"><span data-stu-id="b98e5-107">Running LOBApplication</span></span>  
  
#### <a name="to-run-lobapplication"></a><span data-ttu-id="b98e5-108">若要运行 LOBApplication</span><span class="sxs-lookup"><span data-stu-id="b98e5-108">To run LOBApplication</span></span>  
  
1.  <span data-ttu-id="b98e5-109">在 Windows 资源管理器，转至\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="b98e5-109">In Windows Explorer, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
2.  <span data-ttu-id="b98e5-110">双击**LOBApplication.exe**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="b98e5-110">Double-click **LOBApplication.exe**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="b98e5-111">之后显示的页将提示你输入运行该实用工具所需的信息。</span><span class="sxs-lookup"><span data-stu-id="b98e5-111">The pages that follow prompt you for the information that is required to run the utility.</span></span>  
  
## <a name="syntax-for-lobapplication"></a><span data-ttu-id="b98e5-112">LOBApplication 的语法</span><span class="sxs-lookup"><span data-stu-id="b98e5-112">Syntax for LOBApplication</span></span>  
 <span data-ttu-id="b98e5-113">使用**LOB 应用程序代理**页后，可以指定与合作伙伴的名称、 合作伙伴接口流程 (PIP) 属性和 LOBApplication 实用工具发送的消息的消息属性。</span><span class="sxs-lookup"><span data-stu-id="b98e5-113">Use the **LOB Application Proxy** page to specify home and partner names, Partner Interface Process (PIP) properties, and message properties for the message sent by the LOBApplication utility.</span></span>  
  
 <span data-ttu-id="b98e5-114">下表介绍了如何使用每个字段**LOB 应用程序代理**页。</span><span class="sxs-lookup"><span data-stu-id="b98e5-114">The following table describes how to use each field on the **LOB Application Proxy** page.</span></span>  
  
|<span data-ttu-id="b98e5-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b98e5-115">Use this</span></span>|<span data-ttu-id="b98e5-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b98e5-116">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="b98e5-117">**本组织配置文件名称**</span><span class="sxs-lookup"><span data-stu-id="b98e5-117">**Home Profile Name**</span></span>|<span data-ttu-id="b98e5-118">键入本组织的名称（源参与方）。</span><span class="sxs-lookup"><span data-stu-id="b98e5-118">Type the name of the home organization (source party).</span></span>|  
|<span data-ttu-id="b98e5-119">**贸易合作伙伴名称**</span><span class="sxs-lookup"><span data-stu-id="b98e5-119">**Trading Partner Name**</span></span>|<span data-ttu-id="b98e5-120">键入贸易合作伙伴的名称（目标参与方）。</span><span class="sxs-lookup"><span data-stu-id="b98e5-120">Type the name of the trading partner (destination party).</span></span>|  
|<span data-ttu-id="b98e5-121">**PIP 名称**</span><span class="sxs-lookup"><span data-stu-id="b98e5-121">**PIP Name**</span></span>|<span data-ttu-id="b98e5-122">键入 PIP，例如，类型的显示代码**3A2**。</span><span class="sxs-lookup"><span data-stu-id="b98e5-122">Type the display code of the PIP, for example, type **3A2**.</span></span> <span data-ttu-id="b98e5-123">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b98e5-123">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="b98e5-124">**PIP 版本**</span><span class="sxs-lookup"><span data-stu-id="b98e5-124">**PIP Version**</span></span>|<span data-ttu-id="b98e5-125">键入 PIP 的版本，例如，类型**V02.00**。</span><span class="sxs-lookup"><span data-stu-id="b98e5-125">Type the version of the PIP, for example, type **V02.00**.</span></span> <span data-ttu-id="b98e5-126">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b98e5-126">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="b98e5-127">**PIP 实例 ID** （可选）</span><span class="sxs-lookup"><span data-stu-id="b98e5-127">**PIP Instance ID** (optional)</span></span>|<span data-ttu-id="b98e5-128">键入的字母数字实例 ID 对于 PIP，例如，键入**STD_3A2_V02.02**。</span><span class="sxs-lookup"><span data-stu-id="b98e5-128">Type an alphanumeric instance ID for the PIP, for example, type **STD_3A2_V02.02**.</span></span> <span data-ttu-id="b98e5-129">不要使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="b98e5-129">Avoid special characters.</span></span> <span data-ttu-id="b98e5-130">该 ID 对于每个合作伙伴和每个 PIP 代码应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b98e5-130">The ID should be unique per partner and per PIP code.</span></span> <span data-ttu-id="b98e5-131">对于标记为操作消息的消息，如果实例 ID 为空，则 LOBApplication 实用工具将使用生成的 HUID 值作为 PIP 实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b98e5-131">For messages that are marked as action messages, if the Instance ID is empty, the LOBApplication utility uses a generated HUID value for the PIP Instance ID.</span></span> <span data-ttu-id="b98e5-132">**注意：** 当选**响应**中**消息类别**，必须在此字段中键入 PIP 实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b98e5-132">**Note:**  When you select **Response** in the **Message Category**, you must type the PIP Instance ID in this field.</span></span>|  
|<span data-ttu-id="b98e5-133">**文件名**</span><span class="sxs-lookup"><span data-stu-id="b98e5-133">**File Name**</span></span>|<span data-ttu-id="b98e5-134">单击省略号按钮 (...)，转到包含 PIP 实例文件的文件夹，然后单击该 PIP 实例文件。</span><span class="sxs-lookup"><span data-stu-id="b98e5-134">Click the ellipsis button (...), go to the folder that contains the PIP instance file, and then click the PIP instance file.</span></span>|  
|<span data-ttu-id="b98e5-135">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="b98e5-135">**Message Category**</span></span>|<span data-ttu-id="b98e5-136">选择消息类型 (**操作**或**响应**)。</span><span class="sxs-lookup"><span data-stu-id="b98e5-136">Select the type of message (**Action** or **Response**).</span></span>|  
|<span data-ttu-id="b98e5-137">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="b98e5-137">**Attachments**</span></span>|<span data-ttu-id="b98e5-138">单击**外**，转到包含附件文件的文件夹，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b98e5-138">Click **Add**, move to the folder that contains the attachment file, and then click **Open**.</span></span>|  
|<span data-ttu-id="b98e5-139">**提交消息**</span><span class="sxs-lookup"><span data-stu-id="b98e5-139">**Submit Message**</span></span>|<span data-ttu-id="b98e5-140">单击以发送消息。</span><span class="sxs-lookup"><span data-stu-id="b98e5-140">Click to send the message.</span></span>|  
|<span data-ttu-id="b98e5-141">**“状态”**</span><span class="sxs-lookup"><span data-stu-id="b98e5-141">**Status**</span></span>|<span data-ttu-id="b98e5-142">在此字段中读取操作的状态。</span><span class="sxs-lookup"><span data-stu-id="b98e5-142">Read the status of the action in this field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b98e5-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="b98e5-143">Remarks</span></span>  
 <span data-ttu-id="b98e5-144">LOBApplication 实用工具创建具有指定属性的消息，并将其发送给贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="b98e5-144">The LOBApplication utility creates a message with the properties specified, and sends it to the trading partner.</span></span> <span data-ttu-id="b98e5-145">此实用工具将消息中的服务内容数据写入到 BTARNDATA 数据库的 MessageFromLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="b98e5-145">This utility writes the service content data in the message to the BTARNDATA database, in the MessageFromLOB table.</span></span> <span data-ttu-id="b98e5-146">此实用工具模拟发送操作消息的过程。</span><span class="sxs-lookup"><span data-stu-id="b98e5-146">This utility simulates sending an action message.</span></span>  
  
 <span data-ttu-id="b98e5-147">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 的 LOBApplication 文件夹下的 SampleInstances 文件夹中提供了示例消息，这些消息根据以下假定进行了预配置：假定全局业务标识符 (GBI) 为 123456789（用于本组织）和 987654321（对于合作伙伴组织）。</span><span class="sxs-lookup"><span data-stu-id="b98e5-147">The sample messages in the SampleInstances folder under the LOBApplication folder in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK are preconfigured to assume the following Global Business Identifiers (GBIs): 123456789 for the home organization and 987654321 for the partner organization.</span></span> <span data-ttu-id="b98e5-148">若要使用其他 GBI，则必须在文本编辑器中更改示例消息。</span><span class="sxs-lookup"><span data-stu-id="b98e5-148">You must change the sample messages in a text editor to use other GBIs.</span></span>  
  
 <span data-ttu-id="b98e5-149">使用 LOBApplication 实用工具可以模拟业务线桌面程序提交消息的过程。</span><span class="sxs-lookup"><span data-stu-id="b98e5-149">You use the LOBApplication utility to simulate a line-of-business desktop program submitting a message.</span></span> <span data-ttu-id="b98e5-150">使用 LOBWebApplication 实用工具还可以模拟业务线 Web 应用程序提交消息的过程。</span><span class="sxs-lookup"><span data-stu-id="b98e5-150">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98e5-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="b98e5-151">See Also</span></span>  
 <span data-ttu-id="b98e5-152">[实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="b98e5-152">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="b98e5-153">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="b98e5-153">LOBWebApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
