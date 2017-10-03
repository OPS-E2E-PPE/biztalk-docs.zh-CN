---
title: "步骤 3： 为你 Organization1 配置方和业务配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 849e5146-a82a-41f2-bb96-089841b2444d
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eff579959840f760449422ebbe7af35792e7cc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="14b86-102">步骤 3： 为你的组织配置方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="14b86-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="14b86-103">![步骤 3 中 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="14b86-103">![Step 3 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  
  
 <span data-ttu-id="14b86-104">在此步骤中，你将为组织配置参与方和业务配置文件，以便接收来自贸易合作伙伴的 850 消息，并返回 997 确认消息。</span><span class="sxs-lookup"><span data-stu-id="14b86-104">In this step, you configure a party and a business profile for your organization to receive an 850 message from your trading partner and return a 997 acknowledgment message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="14b86-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="14b86-105">Prerequisites</span></span>  
 <span data-ttu-id="14b86-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="14b86-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="14b86-107">为组织配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="14b86-107">To configure a party and business profile for your organization</span></span>  
  
1.  <span data-ttu-id="14b86-108">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，通过单击**启动**，依次指向**所有程序**，依次指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="14b86-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="14b86-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="14b86-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="14b86-110">右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="14b86-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3.  <span data-ttu-id="14b86-111">在**参与方属性**对话框框中，输入**OrderSystem**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="14b86-111">In the **Party Properties** dialog box, enter **OrderSystem** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="14b86-112">选择**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="14b86-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="14b86-113">通过选中复选框指定的当事方 (在这种情况下， **OrderSystem**) 也承载 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="14b86-113">By selecting the check box you specify that the party (in this case, **OrderSystem**) also hosts BizTalk Server.</span></span>  
  
5.  <span data-ttu-id="14b86-114">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="14b86-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="14b86-115">右键单击方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="14b86-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7.  <span data-ttu-id="14b86-116">在**配置文件属性**对话框中，在**常规**页上，输入`OrderSystem_Profile`中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="14b86-116">In the **Profile Properties** dialog box, on the **General** page, enter `OrderSystem_Profile` in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b86-117">一个配置文件时创建一个参与方，名为*PartyName*_Profile 自动创建。</span><span class="sxs-lookup"><span data-stu-id="14b86-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="14b86-118">你可以使用此配置文件，不必创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="14b86-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="14b86-119">若要重命名配置文件，右键单击配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="14b86-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="14b86-120">在**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="14b86-120">In the **General** page, specify a name for the profile.</span></span>  
  
8.  <span data-ttu-id="14b86-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="14b86-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="14b86-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="14b86-122">Next Steps</span></span>  
 <span data-ttu-id="14b86-123">为你的合作伙伴组织配置方和业务配置文件 (**Fabrikam**) 中所述，[步骤 4： 为你的贸易合作伙伴配置方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。</span><span class="sxs-lookup"><span data-stu-id="14b86-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b86-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14b86-124">See Also</span></span>  
 [<span data-ttu-id="14b86-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="14b86-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)