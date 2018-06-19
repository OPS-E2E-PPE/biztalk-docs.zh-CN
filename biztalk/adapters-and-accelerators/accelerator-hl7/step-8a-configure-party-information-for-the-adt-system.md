---
title: 步骤 8A： 配置 ADT 系统的当事方信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42b92e3b55cd4de181103e28526abf3ecde29412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962043"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a><span data-ttu-id="368a5-102">步骤 8A： 配置 ADT 系统的当事方信息</span><span class="sxs-lookup"><span data-stu-id="368a5-102">Step 8A: Configure Party Information for the ADT System</span></span>
<span data-ttu-id="368a5-103">在此步骤中，你可以配置 ADT 系统的方信息。</span><span class="sxs-lookup"><span data-stu-id="368a5-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="368a5-104">若要配置的 ADT 系统方信息</span><span class="sxs-lookup"><span data-stu-id="368a5-104">To configure the ADT System party information</span></span>  
  
1.  <span data-ttu-id="368a5-105">在 BizTalk Server 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="368a5-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="368a5-106">在参与方属性对话框中，在**名称**框中，键入**Tutorial_ADTSystem**。</span><span class="sxs-lookup"><span data-stu-id="368a5-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_ADTSystem**.</span></span> <span data-ttu-id="368a5-107">（在此框中键入的值是从原始 HL7 消息实例，ADT^A03.txt MSH3。）</span><span class="sxs-lookup"><span data-stu-id="368a5-107">(The value you type in this box is from the original HL7 message instance, ADT^A03.txt MSH3.)</span></span>  
  
3.  <span data-ttu-id="368a5-108">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="368a5-108">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="368a5-109">在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_sendAck_ADT**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="368a5-109">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendAck_ADT**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="368a5-110">单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="368a5-110">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="368a5-111">在 BTAHL7 配置资源管理器中，选择**确认**选项卡。有关**确认类型**，选择**EnhancedMode**。</span><span class="sxs-lookup"><span data-stu-id="368a5-111">In the BTAHL7 Configuration Explorer, select the **Acknowledgment** tab. For **Acknowledgment type**, select **EnhancedMode**.</span></span>  
  
7.  <span data-ttu-id="368a5-112">单击**保存**，然后关闭 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="368a5-112">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="368a5-113">继续执行[步骤 8B： 配置 RX 系统的当事方信息](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md)。</span><span class="sxs-lookup"><span data-stu-id="368a5-113">Proceed to [Step 8B: Configure Party Information for the RX System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span></span>