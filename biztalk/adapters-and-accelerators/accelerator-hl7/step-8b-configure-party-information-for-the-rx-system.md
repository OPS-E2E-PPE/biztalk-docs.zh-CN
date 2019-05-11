---
title: 步骤 8B:配置 RX 系统的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc35ab8493be410edaf1f1faf5f653d4038daaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286573"
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a><span data-ttu-id="cc586-102">步骤 8B:配置 RX 系统的参与方信息</span><span class="sxs-lookup"><span data-stu-id="cc586-102">Step 8B: Configure Party Information for the RX System</span></span>
<span data-ttu-id="cc586-103">在此步骤中，你可以配置 RX 系统的参与方信息。</span><span class="sxs-lookup"><span data-stu-id="cc586-103">In this step, you configure the party information for the RX System.</span></span>  

### <a name="to-configure-the-rx-system-party-information"></a><span data-ttu-id="cc586-104">若要配置 RX 系统参与方信息</span><span class="sxs-lookup"><span data-stu-id="cc586-104">To configure the RX System party information</span></span>  

1. <span data-ttu-id="cc586-105">在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="cc586-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="cc586-106">在参与方属性对话框中，在**名称**框中，键入**Tutorial_RXSystem**。</span><span class="sxs-lookup"><span data-stu-id="cc586-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_RXSystem**.</span></span>  

3. <span data-ttu-id="cc586-107">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="cc586-107">In the console tree, click **Send Ports**.</span></span>  

4. <span data-ttu-id="cc586-108">在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_sendMsg_RX**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc586-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendMsg_RX**, and then click **OK**.</span></span>  

5. <span data-ttu-id="cc586-109">单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="cc586-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

6. <span data-ttu-id="cc586-110">在 BTAHL7 配置资源管理器中，选择**MSH 映射**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc586-110">In the BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  


   | <span data-ttu-id="cc586-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cc586-111">Use this</span></span> |                    <span data-ttu-id="cc586-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cc586-112">To do this</span></span>                    |
   |----------|--------------------------------------------------|
   | <span data-ttu-id="cc586-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="cc586-113">**MSH3**</span></span> |      <span data-ttu-id="cc586-114">类型**BTAHL7**左侧的文本框中。</span><span class="sxs-lookup"><span data-stu-id="cc586-114">Type **BTAHL7** in the left text box.</span></span>       |
   | <span data-ttu-id="cc586-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="cc586-115">**MSH5**</span></span> | <span data-ttu-id="cc586-116">类型**Tutorial_RXSystem**左侧的文本框中。</span><span class="sxs-lookup"><span data-stu-id="cc586-116">Type **Tutorial_RXSystem** in the left text box.</span></span> |


7. <span data-ttu-id="cc586-117">单击**保存**，然后关闭 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="cc586-117">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  

   <span data-ttu-id="cc586-118">请继续执行[步骤 8c:配置 HI 系统的参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md)。</span><span class="sxs-lookup"><span data-stu-id="cc586-118">Proceed to [Step 8C: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).</span></span>