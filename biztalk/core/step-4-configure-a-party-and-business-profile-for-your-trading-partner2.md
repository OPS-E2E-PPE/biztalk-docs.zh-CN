---
title: 步骤 4： 配置参与方和业务配置文件贸易 Partner2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce07a1a6-4d5d-44ea-b1cb-04d7ae85747f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0ecc92a435455d15db31e2de454ff935c1504f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977926"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="d44b0-102">步骤 4： 为贸易合作伙伴配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="d44b0-102">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>
<span data-ttu-id="d44b0-103">![步骤 4 11](../core/media/tut-step4-of-11.gif "Tut_Step4_of_11")</span><span class="sxs-lookup"><span data-stu-id="d44b0-103">![Step 4 of 11](../core/media/tut-step4-of-11.gif "Tut_Step4_of_11")</span></span>  
  
 <span data-ttu-id="d44b0-104">在此步骤中，您将为您的贸易合作伙伴 Fabrikam 配置参与方和业务配置文件，以便向组织发送 864 消息，并接收返回的 997 确认消息和异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="d44b0-104">In this step, you configure a party and business profile for your trading partner Fabrikam to send an 864 message to your organization and receive a 997 acknowledgment message and an asynchronous MDN in return.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d44b0-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="d44b0-105">Prerequisites</span></span>  
 <span data-ttu-id="d44b0-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="d44b0-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="d44b0-107">为你的贸易合作伙伴配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="d44b0-107">To configure a party and business profile for your trading partner</span></span>  
  
1. <span data-ttu-id="d44b0-108">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**.</span><span class="sxs-lookup"><span data-stu-id="d44b0-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d44b0-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="d44b0-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="d44b0-110">右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="d44b0-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="d44b0-111">在中**参与方属性**对话框框中，输入**Fabrikam**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="d44b0-111">In the **Party Properties** dialog box, enter **Fabrikam** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="d44b0-112">清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="d44b0-112">Clear the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="d44b0-113">通过清除复选框指定的参与方 (在这种情况下， **Fabrikam**) 不托管 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d44b0-113">By clearing the check box you specify that the party (in this case, **Fabrikam**) does not host BizTalk Server.</span></span>  
  
5. <span data-ttu-id="d44b0-114">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d44b0-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="d44b0-115">右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="d44b0-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="d44b0-116">在中**配置文件属性**对话框中，在**常规**页上，输入`Fabrikam_Profile`中**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="d44b0-116">In the **Profile Properties** dialog box, on the **General** page, enter `Fabrikam_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d44b0-117">创建一个参与方时，还创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="d44b0-117">When you create a party, a profile is also created.</span></span> <span data-ttu-id="d44b0-118">可以重命名，并使用该配置文件而不是创建一个新。</span><span class="sxs-lookup"><span data-stu-id="d44b0-118">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="d44b0-119">若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="d44b0-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="d44b0-120">在中**常规**页上，指定配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d44b0-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="d44b0-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d44b0-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d44b0-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d44b0-122">Next Steps</span></span>  
 <span data-ttu-id="d44b0-123">配置 BTS ISAPI 筛选器和 Fabrikam 和 Contoso Web 页[步骤 5： 配置贸易合作伙伴网页](../core/step-5-configure-the-trading-partner-web-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="d44b0-123">You configure the BTS ISAPI filter and the Fabrikam and Contoso Web pages in [Step 5: Configure the Trading Partner Web Pages](../core/step-5-configure-the-trading-partner-web-pages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44b0-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d44b0-124">See Also</span></span>  
 [<span data-ttu-id="d44b0-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="d44b0-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)