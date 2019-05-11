---
title: 步骤 3：为你 Organization2 配置参与方和业务配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 024d1ec7-237a-43cb-8159-90f9c71a670e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a0f357a996edd78a7f6aefb16b8b4d00bc1fb2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392688"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="13b20-102">步骤 3：为你的组织配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="13b20-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="13b20-103">![步骤 3 中 11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")</span><span class="sxs-lookup"><span data-stu-id="13b20-103">![Step 3 of 11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")</span></span>  
  
 <span data-ttu-id="13b20-104">在此步骤中，您可以配置以接收来自贸易合作伙伴的 864 消息，并返回 997 确认消息和异步 MDN 的参与方和业务配置文件为你的组织。</span><span class="sxs-lookup"><span data-stu-id="13b20-104">In this step, you configure a party and a business profile for your organization to receive an 864 message from your trading partner and return a 997 acknowledgment message and an asynchronous MDN.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="13b20-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="13b20-105">Prerequisites</span></span>  
 <span data-ttu-id="13b20-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="13b20-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="13b20-107">若要配置你的组织的参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="13b20-107">To configure a party and business profile for your organization</span></span>  
  
1. <span data-ttu-id="13b20-108">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**.</span><span class="sxs-lookup"><span data-stu-id="13b20-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="13b20-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="13b20-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="13b20-110">右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="13b20-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="13b20-111">在中**参与方属性**对话框框中，输入**Contoso**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="13b20-111">In the **Party Properties** dialog box, enter **Contoso** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="13b20-112">选择**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="13b20-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="13b20-113">通过选中复选框来指定的参与方 (在这种情况下， **Contoso**) 还托管 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="13b20-113">By selecting the check box you specify that the party (in this case, **Contoso**) also hosts BizTalk Server.</span></span>  
  
5. <span data-ttu-id="13b20-114">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="13b20-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="13b20-115">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="13b20-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="13b20-116">在中**配置文件属性**对话框中，在**常规**页上，输入`Contoso_Profile`中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="13b20-116">In the **Profile Properties** dialog box, on the **General** page, enter `Contoso_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="13b20-117">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="13b20-117">When you create a party, a profile is also created.</span></span> <span data-ttu-id="13b20-118">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="13b20-118">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="13b20-119">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="13b20-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="13b20-120">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="13b20-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="13b20-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="13b20-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="13b20-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="13b20-122">Next Steps</span></span>  
 <span data-ttu-id="13b20-123">为你的合作伙伴组织配置参与方和业务配置文件 (**Fabrikam**)，如中所述[步骤 4:为您的贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)。</span><span class="sxs-lookup"><span data-stu-id="13b20-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b20-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="13b20-124">See Also</span></span>  
 [<span data-ttu-id="13b20-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="13b20-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)