---
title: "步骤 8 C： 配置 HI 系统的当事方信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0b9e1538ea667eab2299a1a02021c1237bc985
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a><span data-ttu-id="164af-102">步骤 8 C： 配置 HI 系统的当事方信息</span><span class="sxs-lookup"><span data-stu-id="164af-102">Step 8C: Configure Party Information for the HI System</span></span>
<span data-ttu-id="164af-103">在此步骤中，你可以配置 HI 系统的方信息。</span><span class="sxs-lookup"><span data-stu-id="164af-103">In this step, you configure the party information for the HI System.</span></span>  
  
### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="164af-104">若要配置的 HI 系统方信息</span><span class="sxs-lookup"><span data-stu-id="164af-104">To configure the HI System party information</span></span>  
  
1.  <span data-ttu-id="164af-105">在 BizTalk Server 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="164af-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="164af-106">在参与方属性对话框中，在**名称**框中，键入**Tutorial_HISystem**。</span><span class="sxs-lookup"><span data-stu-id="164af-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_HISystem**.</span></span>  
  
3.  <span data-ttu-id="164af-107">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="164af-107">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="164af-108">在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_MllpSend**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="164af-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_MllpSend**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="164af-109">单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本 > Accelerator for HL7**，然后单击**BTAHL7配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="164af-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="164af-110">在 BTAHL7 配置资源管理器中，选择**MSH 映射**选项卡，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="164af-110">In BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="164af-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="164af-111">Use this</span></span>|<span data-ttu-id="164af-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="164af-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="164af-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="164af-113">**MSH3**</span></span>|<span data-ttu-id="164af-114">类型**BTAHL7**， **IE**，和**UUID**中第一个，第二周、 和第三个消息框中，分别。</span><span class="sxs-lookup"><span data-stu-id="164af-114">Type **BTAHL7**, **IE**, and **UUID** in the first, second, and third message boxes, respectively.</span></span>|  
    |<span data-ttu-id="164af-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="164af-115">**MSH5**</span></span>|<span data-ttu-id="164af-116">类型**HI**，**系统**，和**GUID**中第一个，第二周、 和第三个消息框中，分别。</span><span class="sxs-lookup"><span data-stu-id="164af-116">Type **HI**, **System**, and **GUID** in the first, second, and third message boxes, respectively.</span></span>|  
    |<span data-ttu-id="164af-117">**MSH9**</span><span class="sxs-lookup"><span data-stu-id="164af-117">**MSH9**</span></span>|<span data-ttu-id="164af-118">类型**ADT**和**A04**在第一个和第二个消息框中，分别。</span><span class="sxs-lookup"><span data-stu-id="164af-118">Type **ADT** and **A04** in the first and second message boxes, respectively.</span></span>|  
    |<span data-ttu-id="164af-119">**MSH12**</span><span class="sxs-lookup"><span data-stu-id="164af-119">**MSH12**</span></span>|<span data-ttu-id="164af-120">类型**2.4**。</span><span class="sxs-lookup"><span data-stu-id="164af-120">Type **2.4**.</span></span>|  
    |<span data-ttu-id="164af-121">**MSH15**</span><span class="sxs-lookup"><span data-stu-id="164af-121">**MSH15**</span></span>|<span data-ttu-id="164af-122">选择**SU**后要将发送确认成功的消息传输。</span><span class="sxs-lookup"><span data-stu-id="164af-122">Select **SU** to send acknowledgments after successful transmission of a message.</span></span>|  
    |<span data-ttu-id="164af-123">**MSH16**</span><span class="sxs-lookup"><span data-stu-id="164af-123">**MSH16**</span></span>|<span data-ttu-id="164af-124">选择**NE**永远不会发送确认。</span><span class="sxs-lookup"><span data-stu-id="164af-124">Select **NE** to never send acknowledgments.</span></span>|  
  
7.  <span data-ttu-id="164af-125">单击**保存**，然后关闭 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="164af-125">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="164af-126">你不需要创建方信息对于 BTAHL7 接口引擎系统，因为不需要这种情况下配置信息。</span><span class="sxs-lookup"><span data-stu-id="164af-126">You do not need to create party information for the BTAHL7 Interface Engine System, because configuration information is not required for this scenario.</span></span>  
  
 <span data-ttu-id="164af-127">继续执行[步骤 9： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="164af-127">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).</span></span>