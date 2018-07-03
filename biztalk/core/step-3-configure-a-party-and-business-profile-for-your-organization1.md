---
title: 步骤 3： 配置参与方和业务配置文件在 Organization1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 849e5146-a82a-41f2-bb96-089841b2444d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5427ca12ff031bb7fa045a78709f97fdbb49fdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023475"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="cd20c-102">步骤 3： 为你的组织配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="cd20c-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="cd20c-103">![第 3 部分，共 9 步](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="cd20c-103">![Step 3 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  
  
 <span data-ttu-id="cd20c-104">在此步骤中，你将为组织配置参与方和业务配置文件，以便接收来自贸易合作伙伴的 850 消息，并返回 997 确认消息。</span><span class="sxs-lookup"><span data-stu-id="cd20c-104">In this step, you configure a party and a business profile for your organization to receive an 850 message from your trading partner and return a 997 acknowledgment message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cd20c-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="cd20c-105">Prerequisites</span></span>  
 <span data-ttu-id="cd20c-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cd20c-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="cd20c-107">为组织配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="cd20c-107">To configure a party and business profile for your organization</span></span>  
  
1. <span data-ttu-id="cd20c-108">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cd20c-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cd20c-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="cd20c-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="cd20c-110">右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="cd20c-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="cd20c-111">在中**参与方属性**对话框框中，输入**OrderSystem**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="cd20c-111">In the **Party Properties** dialog box, enter **OrderSystem** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="cd20c-112">选择**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="cd20c-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="cd20c-113">通过选中复选框来指定的参与方 (在这种情况下， **OrderSystem**) 还托管 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="cd20c-113">By selecting the check box you specify that the party (in this case, **OrderSystem**) also hosts BizTalk Server.</span></span>  
  
5. <span data-ttu-id="cd20c-114">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="cd20c-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="cd20c-115">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="cd20c-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="cd20c-116">在中**配置文件属性**对话框中，在**常规**页上，输入`OrderSystem_Profile`中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="cd20c-116">In the **Profile Properties** dialog box, on the **General** page, enter `OrderSystem_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cd20c-117">一个配置文件时创建的参与方，名为*PartyName*（_p） 自动创建。</span><span class="sxs-lookup"><span data-stu-id="cd20c-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="cd20c-118">你可以使用此配置文件，不必创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cd20c-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="cd20c-119">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="cd20c-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="cd20c-120">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cd20c-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="cd20c-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="cd20c-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cd20c-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd20c-122">Next Steps</span></span>  
 <span data-ttu-id="cd20c-123">为你的合作伙伴组织配置参与方和业务配置文件 (**Fabrikam**)，如中所述[步骤 4： 为您的贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。</span><span class="sxs-lookup"><span data-stu-id="cd20c-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd20c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd20c-124">See Also</span></span>  
 [<span data-ttu-id="cd20c-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="cd20c-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)