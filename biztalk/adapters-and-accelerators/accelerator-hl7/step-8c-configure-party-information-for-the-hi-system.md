---
title: 步骤 8c： 配置 HI 系统的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aba42674a78bbed850c0994ec23c477c36b29c2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970822"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a><span data-ttu-id="b96c6-102">步骤 8c： 配置 HI 系统的参与方信息</span><span class="sxs-lookup"><span data-stu-id="b96c6-102">Step 8C: Configure Party Information for the HI System</span></span>
<span data-ttu-id="b96c6-103">在此步骤中，你可以配置 HI 系统的参与方信息。</span><span class="sxs-lookup"><span data-stu-id="b96c6-103">In this step, you configure the party information for the HI System.</span></span>  

### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="b96c6-104">若要配置 HI 系统的参与方信息</span><span class="sxs-lookup"><span data-stu-id="b96c6-104">To configure the HI System party information</span></span>  

1. <span data-ttu-id="b96c6-105">在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="b96c6-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="b96c6-106">在参与方属性对话框中，在**名称**框中，键入**Tutorial_HISystem**。</span><span class="sxs-lookup"><span data-stu-id="b96c6-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_HISystem**.</span></span>  

3. <span data-ttu-id="b96c6-107">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b96c6-107">In the console tree, click **Send Ports**.</span></span>  

4. <span data-ttu-id="b96c6-108">在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_MllpSend**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b96c6-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_MllpSend**, and then click **OK**.</span></span>  

5. <span data-ttu-id="b96c6-109">单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="b96c6-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

6. <span data-ttu-id="b96c6-110">BTAHL7 配置资源管理器中选择**MSH 映射**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b96c6-110">In BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  


   | <span data-ttu-id="b96c6-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b96c6-111">Use this</span></span>  |                                             <span data-ttu-id="b96c6-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b96c6-112">To do this</span></span>                                             |
   |-----------|----------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="b96c6-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="b96c6-113">**MSH3**</span></span>  | <span data-ttu-id="b96c6-114">类型**BTAHL7**， **IE**，并**UUID**在第一个，第二、 第三个消息和框中，分别。</span><span class="sxs-lookup"><span data-stu-id="b96c6-114">Type **BTAHL7**, **IE**, and **UUID** in the first, second, and third message boxes, respectively.</span></span> |
   | <span data-ttu-id="b96c6-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="b96c6-115">**MSH5**</span></span>  | <span data-ttu-id="b96c6-116">类型**HI**，**系统**，并**GUID**在第一个，第二、 第三个消息和框中，分别。</span><span class="sxs-lookup"><span data-stu-id="b96c6-116">Type **HI**, **System**, and **GUID** in the first, second, and third message boxes, respectively.</span></span> |
   | <span data-ttu-id="b96c6-117">**MSH9**</span><span class="sxs-lookup"><span data-stu-id="b96c6-117">**MSH9**</span></span>  |           <span data-ttu-id="b96c6-118">类型**ADT**并**A04**中第一个和第二个消息框中，分别。</span><span class="sxs-lookup"><span data-stu-id="b96c6-118">Type **ADT** and **A04** in the first and second message boxes, respectively.</span></span>            |
   | <span data-ttu-id="b96c6-119">**MSH12**</span><span class="sxs-lookup"><span data-stu-id="b96c6-119">**MSH12**</span></span> |                                           <span data-ttu-id="b96c6-120">类型**2.4**。</span><span class="sxs-lookup"><span data-stu-id="b96c6-120">Type **2.4**.</span></span>                                            |
   | <span data-ttu-id="b96c6-121">**MSH15**</span><span class="sxs-lookup"><span data-stu-id="b96c6-121">**MSH15**</span></span> |         <span data-ttu-id="b96c6-122">选择**SU**后要将发送确认的消息成功传输。</span><span class="sxs-lookup"><span data-stu-id="b96c6-122">Select **SU** to send acknowledgments after successful transmission of a message.</span></span>          |
   | <span data-ttu-id="b96c6-123">**MSH16**</span><span class="sxs-lookup"><span data-stu-id="b96c6-123">**MSH16**</span></span> |                            <span data-ttu-id="b96c6-124">选择**NE**永远不会发送确认。</span><span class="sxs-lookup"><span data-stu-id="b96c6-124">Select **NE** to never send acknowledgments.</span></span>                            |


7. <span data-ttu-id="b96c6-125">单击**保存**，然后关闭 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="b96c6-125">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b96c6-126">您不需要创建参与方信息 BTAHL7 接口引擎系统，因为不需要此方案的配置信息。</span><span class="sxs-lookup"><span data-stu-id="b96c6-126">You do not need to create party information for the BTAHL7 Interface Engine System, because configuration information is not required for this scenario.</span></span>  

   <span data-ttu-id="b96c6-127">请继续执行[步骤 9： 重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b96c6-127">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).</span></span>