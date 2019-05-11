---
title: LOBApplication | Microsoft Docs
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
ms.openlocfilehash: a3f65980015d689cd79f1d006441c1687d15be01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283327"
---
# <a name="lobapplication"></a><span data-ttu-id="ecf9e-102">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="ecf9e-102">LOBApplication</span></span>
<span data-ttu-id="ecf9e-103">使用 LOBApplication 实用工具提交给贸易合作伙伴，模拟实际的业务线 (LOB) 桌面程序的操作或响应消息。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-103">You use the LOBApplication utility to submit an action or response message to a trading partner, simulating an actual line-of-business (LOB) desktop program.</span></span>  
  
 <span data-ttu-id="ecf9e-104">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供了示例消息中的\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-104">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides sample messages in the \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="ecf9e-105">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="ecf9e-105">Location in SDK</span></span>  
 <span data-ttu-id="ecf9e-106">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication</span><span class="sxs-lookup"><span data-stu-id="ecf9e-106">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication</span></span>  
  
## <a name="running-lobapplication"></a><span data-ttu-id="ecf9e-107">运行 LOBApplication</span><span class="sxs-lookup"><span data-stu-id="ecf9e-107">Running LOBApplication</span></span>  
  
#### <a name="to-run-lobapplication"></a><span data-ttu-id="ecf9e-108">若要运行 LOBApplication</span><span class="sxs-lookup"><span data-stu-id="ecf9e-108">To run LOBApplication</span></span>  
  
1.  <span data-ttu-id="ecf9e-109">在 Windows 资源管理器，转至\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-109">In Windows Explorer, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
2.  <span data-ttu-id="ecf9e-110">双击**LOBApplication.exe**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-110">Double-click **LOBApplication.exe**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="ecf9e-111">向导中的页面将提示你输入是运行该实用程序所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-111">The pages that follow prompt you for the information that is required to run the utility.</span></span>  
  
## <a name="syntax-for-lobapplication"></a><span data-ttu-id="ecf9e-112">LOBApplication 的语法</span><span class="sxs-lookup"><span data-stu-id="ecf9e-112">Syntax for LOBApplication</span></span>  
 <span data-ttu-id="ecf9e-113">使用**LOB 应用程序代理**页后，可以指定与合作伙伴的名称、 合作伙伴接口流程 (PIP) 属性和 LOBApplication 实用工具发送的消息的消息属性。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-113">Use the **LOB Application Proxy** page to specify home and partner names, Partner Interface Process (PIP) properties, and message properties for the message sent by the LOBApplication utility.</span></span>  
  
 <span data-ttu-id="ecf9e-114">下表介绍了如何使用每个字段**LOB 应用程序代理**页。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-114">The following table describes how to use each field on the **LOB Application Proxy** page.</span></span>  
  
|<span data-ttu-id="ecf9e-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ecf9e-115">Use this</span></span>|<span data-ttu-id="ecf9e-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ecf9e-116">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="ecf9e-117">**本组织配置文件名称**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-117">**Home Profile Name**</span></span>|<span data-ttu-id="ecf9e-118">键入本组织 （源参与方） 的名称。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-118">Type the name of the home organization (source party).</span></span>|  
|<span data-ttu-id="ecf9e-119">**贸易合作伙伴名称**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-119">**Trading Partner Name**</span></span>|<span data-ttu-id="ecf9e-120">键入贸易合作伙伴 （目标参与方） 的名称。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-120">Type the name of the trading partner (destination party).</span></span>|  
|<span data-ttu-id="ecf9e-121">**PIP 名称**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-121">**PIP Name**</span></span>|<span data-ttu-id="ecf9e-122">键入 PIP，例如，类型的显示代码**3A2**。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-122">Type the display code of the PIP, for example, type **3A2**.</span></span> <span data-ttu-id="ecf9e-123">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-123">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="ecf9e-124">**PIP 版本**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-124">**PIP Version**</span></span>|<span data-ttu-id="ecf9e-125">键入 PIP 的版本，例如，类型**V02.00**。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-125">Type the version of the PIP, for example, type **V02.00**.</span></span> <span data-ttu-id="ecf9e-126">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-126">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="ecf9e-127">**PIP 实例 ID** （可选）</span><span class="sxs-lookup"><span data-stu-id="ecf9e-127">**PIP Instance ID** (optional)</span></span>|<span data-ttu-id="ecf9e-128">键入的字母数字实例 ID 对于 PIP，例如，键入**STD_3A2_V02.02**。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-128">Type an alphanumeric instance ID for the PIP, for example, type **STD_3A2_V02.02**.</span></span> <span data-ttu-id="ecf9e-129">不要使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-129">Avoid special characters.</span></span> <span data-ttu-id="ecf9e-130">ID 应为每个合作伙伴和每个 PIP 代码唯一。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-130">The ID should be unique per partner and per PIP code.</span></span> <span data-ttu-id="ecf9e-131">对于标记为操作消息，如果实例 ID 是空的消息，LOBApplication 实用工具用于生成的 HUID 值 PIP 实例 id。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-131">For messages that are marked as action messages, if the Instance ID is empty, the LOBApplication utility uses a generated HUID value for the PIP Instance ID.</span></span> <span data-ttu-id="ecf9e-132">**注意：** 当选择**响应**中**消息类别**，必须在此字段中键入 PIP 实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-132">**Note:**  When you select **Response** in the **Message Category**, you must type the PIP Instance ID in this field.</span></span>|  
|<span data-ttu-id="ecf9e-133">**文件名**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-133">**File Name**</span></span>|<span data-ttu-id="ecf9e-134">单击省略号按钮 （...），转到包含 PIP 实例文件的文件夹，然后单击 PIP 实例文件。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-134">Click the ellipsis button (...), go to the folder that contains the PIP instance file, and then click the PIP instance file.</span></span>|  
|<span data-ttu-id="ecf9e-135">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-135">**Message Category**</span></span>|<span data-ttu-id="ecf9e-136">选择消息类型 (**操作**或**响应**)。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-136">Select the type of message (**Action** or **Response**).</span></span>|  
|<span data-ttu-id="ecf9e-137">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-137">**Attachments**</span></span>|<span data-ttu-id="ecf9e-138">单击**外**，转到包含附件文件的文件夹，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-138">Click **Add**, move to the folder that contains the attachment file, and then click **Open**.</span></span>|  
|<span data-ttu-id="ecf9e-139">**提交消息**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-139">**Submit Message**</span></span>|<span data-ttu-id="ecf9e-140">单击此项可将消息发送。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-140">Click to send the message.</span></span>|  
|<span data-ttu-id="ecf9e-141">**“状态”**</span><span class="sxs-lookup"><span data-stu-id="ecf9e-141">**Status**</span></span>|<span data-ttu-id="ecf9e-142">阅读此字段中的操作的状态。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-142">Read the status of the action in this field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecf9e-143">备注</span><span class="sxs-lookup"><span data-stu-id="ecf9e-143">Remarks</span></span>  
 <span data-ttu-id="ecf9e-144">LOBApplication 实用工具创建具有指定的属性的消息，并将其发送给贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-144">The LOBApplication utility creates a message with the properties specified, and sends it to the trading partner.</span></span> <span data-ttu-id="ecf9e-145">此实用程序将消息中的服务内容数据写入到 BTARNDATA 数据库的 MessageFromLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-145">This utility writes the service content data in the message to the BTARNDATA database, in the MessageFromLOB table.</span></span> <span data-ttu-id="ecf9e-146">此实用工具模拟发送操作消息。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-146">This utility simulates sending an action message.</span></span>  
  
 <span data-ttu-id="ecf9e-147">中的 LOBApplication 文件夹下的 SampleInstances 文件夹中的示例消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 已预先配置为假定以下全局业务标识符 (Gbi):本组织和合作伙伴组织为 987654321 123456789。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-147">The sample messages in the SampleInstances folder under the LOBApplication folder in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK are preconfigured to assume the following Global Business Identifiers (GBIs): 123456789 for the home organization and 987654321 for the partner organization.</span></span> <span data-ttu-id="ecf9e-148">必须更改文本编辑器中的示例消息，以使用其他 Gbi。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-148">You must change the sample messages in a text editor to use other GBIs.</span></span>  
  
 <span data-ttu-id="ecf9e-149">使用 LOBApplication 实用工具来模拟业务线桌面程序提交消息。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-149">You use the LOBApplication utility to simulate a line-of-business desktop program submitting a message.</span></span> <span data-ttu-id="ecf9e-150">使用 LOBWebApplication 实用工具来模拟业务线 Web 应用程序提交一条消息。</span><span class="sxs-lookup"><span data-stu-id="ecf9e-150">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf9e-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecf9e-151">See Also</span></span>  
 <span data-ttu-id="ecf9e-152">[实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="ecf9e-152">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="ecf9e-153">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ecf9e-153">LOBWebApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
