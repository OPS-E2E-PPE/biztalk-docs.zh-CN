---
title: 单步 8B： 配置 HI 系统的当事方信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96338c05-1440-416e-a56a-6f5b19b55a60
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 460840cf3bbbd6556b1684b25851a16778be92b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206309"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a><span data-ttu-id="1ac97-102">单步 8B： 配置 HI 系统的当事方信息</span><span class="sxs-lookup"><span data-stu-id="1ac97-102">Step 8B: Configure Party Information for the HI System</span></span>
<span data-ttu-id="1ac97-103">在此步骤中，你可以配置 HI 系统的方信息。</span><span class="sxs-lookup"><span data-stu-id="1ac97-103">In this step, you configure the party information for the HI System.</span></span>  
  
### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="1ac97-104">若要配置的 HI 系统方信息</span><span class="sxs-lookup"><span data-stu-id="1ac97-104">To configure the HI System party information</span></span>  
  
1.  <span data-ttu-id="1ac97-105">在 BizTalk 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="1ac97-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="1ac97-106">在参与方属性对话框中，在**名称**字段中，键入**HIS**。</span><span class="sxs-lookup"><span data-stu-id="1ac97-106">In the Party Properties dialog box, in the **Name** field, type **HIS**.</span></span> <span data-ttu-id="1ac97-107">（在此框中键入的值应匹配原始 HL7 消息实例，QRY^Q01.txt MSH5。）</span><span class="sxs-lookup"><span data-stu-id="1ac97-107">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH5.)</span></span>  
  
3.  <span data-ttu-id="1ac97-108">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="1ac97-108">In the Console Tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="1ac97-109">在**发送端口**窗格中，为**名称**在第一行中，选择**HIS_Send**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1ac97-109">In the **Send Port** pane, for **Name** in the first row, select **HIS_Send**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="1ac97-110">继续执行[步骤 9： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac97-110">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).</span></span>