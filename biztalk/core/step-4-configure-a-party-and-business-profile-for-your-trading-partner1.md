---
title: 步骤 4： 配置参与方和业务配置文件贸易 Partner1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db50d0f6-e838-4e92-8548-a63a2c445d55
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa53034af1a07ca55574e2e37eecb7c0875f8a2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989678"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="71d0e-102">步骤 4： 为贸易合作伙伴配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="71d0e-102">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>
<span data-ttu-id="71d0e-103">![步骤 4 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="71d0e-103">![Step 4 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="71d0e-104">在此步骤中，你将为你的贸易合作伙伴 Fabrikam 配置一个参与方和业务配置文件，以便向组织发送 850 消息，并接收返回的 997 确认消息。</span><span class="sxs-lookup"><span data-stu-id="71d0e-104">In this step, you configure a party and business profile for your trading partner Fabrikam to send an 850 message to your organization and receive a 997 acknowledgment message in return.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71d0e-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="71d0e-105">Prerequisites</span></span>  
 <span data-ttu-id="71d0e-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="71d0e-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="71d0e-107">为你的贸易合作伙伴配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="71d0e-107">To configure a party and business profile for your trading partner</span></span>  
  
1. <span data-ttu-id="71d0e-108">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="71d0e-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="71d0e-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="71d0e-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="71d0e-110">右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="71d0e-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="71d0e-111">在中**参与方属性**对话框框中，输入**Fabrikam**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="71d0e-111">In the **Party Properties** dialog box, enter **Fabrikam** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="71d0e-112">清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="71d0e-112">Clear the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="71d0e-113">通过清除复选框指定的参与方 (在这种情况下， **Fabrikam**) 不托管 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="71d0e-113">By clearing the check box you specify that the party (in this case, **Fabrikam**) does not host BizTalk Server.</span></span>  
  
5. <span data-ttu-id="71d0e-114">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="71d0e-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="71d0e-115">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="71d0e-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="71d0e-116">在中**配置文件属性**对话框中，在**常规**页上，输入`Fabrikam_Profile`中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="71d0e-116">In the **Profile Properties** dialog box, on the **General** page, enter `Fabrikam_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="71d0e-117">一个配置文件时创建的参与方，名为*PartyName*（_p） 自动创建。</span><span class="sxs-lookup"><span data-stu-id="71d0e-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="71d0e-118">你可以使用此配置文件，不必创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="71d0e-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="71d0e-119">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="71d0e-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="71d0e-120">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="71d0e-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="71d0e-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="71d0e-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="71d0e-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="71d0e-122">Next Steps</span></span>  
 <span data-ttu-id="71d0e-123">配置接收位置 (**fromTHEM_4010_850**) 以从 Fabrikam 接收 850 消息中所述[步骤 5： 配置接收端口和接收位置](../core/step-5-configure-a-receive-port-and-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="71d0e-123">You configure the receive location (**fromTHEM_4010_850**) to receive the 850 message from Fabrikam, as described in [Step 5: Configure a Receive Port and Receive Location](../core/step-5-configure-a-receive-port-and-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d0e-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="71d0e-124">See Also</span></span>  
 [<span data-ttu-id="71d0e-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="71d0e-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)