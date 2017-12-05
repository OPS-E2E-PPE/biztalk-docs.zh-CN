---
title: "步骤 8A： 配置方信息 ADT System_hl7_main |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9683fd02f94b96ead6817c72298338c064a14cc1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a><span data-ttu-id="fdedf-102">步骤 8A： 配置 ADT System_hl7_main 方信息</span><span class="sxs-lookup"><span data-stu-id="fdedf-102">Step 8A: Configure Party Information for the ADT System_hl7_main</span></span>
<span data-ttu-id="fdedf-103">在此步骤中，你可以配置 ADT 系统的方信息。</span><span class="sxs-lookup"><span data-stu-id="fdedf-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="fdedf-104">若要配置的 ADT 系统方信息</span><span class="sxs-lookup"><span data-stu-id="fdedf-104">To configure the ADT System party information</span></span>  
  
1.  <span data-ttu-id="fdedf-105">在 BizTalk 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-105">In the BizTalk Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="fdedf-106">右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-106">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="fdedf-107">在参与方属性对话框中，在**名称**字段中，键入**ADT**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-107">In the Party Properties dialog box, in the **Name** field, type **ADT**.</span></span> <span data-ttu-id="fdedf-108">（在此框中键入的值应匹配原始 HL7 消息实例，QRY^Q01.txt MSH3。）</span><span class="sxs-lookup"><span data-stu-id="fdedf-108">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH3.)</span></span>  
  
3.  <span data-ttu-id="fdedf-109">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-109">In the Console Tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="fdedf-110">在**发送端口**窗格中，为**名称**在第一行中，选择**ADT_Send**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-110">In the **Send Port** pane, for **Name** in the first row, select **ADT_Send**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="fdedf-111">单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-111">Click **Start**, point to **Programs**, point to **Microsoft  BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="fdedf-112">在 BTAHL7 配置资源管理器中，单击**确认**选项卡。有关**确认类型**，选择**EnhancedMode**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-112">In BTAHL7 Configuration Explorer, click the **Acknowledgment** tab. For **Acknowledgment Type**, select **EnhancedMode**.</span></span>  
  
7.  <span data-ttu-id="fdedf-113">中的 Inboiund 消息窗格中，确认属性为**MSH15-接受确认类型**，选择**AL**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-113">In the Acknowledgment Properties in Inboiund Message pane, for **MSH15 - Accept Acknowledgment Type**, select **AL**.</span></span>  
  
8.  <span data-ttu-id="fdedf-114">在确认属性窗格中，为**MSH16-应用程序确认类型**，选择**NE**。</span><span class="sxs-lookup"><span data-stu-id="fdedf-114">In the Acknowledgment Properties pane, for **MSH16 - Application Acknowledgment Type**, select **NE**.</span></span>  
  
9. <span data-ttu-id="fdedf-115">单击**保存**，然后关闭 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="fdedf-115">Click **Save**, and then close BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="fdedf-116">继续执行[步骤 8B： 配置 HI 系统的当事方信息](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md)。</span><span class="sxs-lookup"><span data-stu-id="fdedf-116">Proceed to [Step 8B: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md).</span></span>