---
title: "创建 Affiliate Applications5 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, affiliate
- Single Sign-On, tickets
- affiliate applications
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- SSO tickets
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc6b42a6f3251d9e897af21fcb4207b6790e91cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="33eeb-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="33eeb-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="33eeb-103">以下步骤描述如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="33eeb-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33eeb-104">如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户；这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="33eeb-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="33eeb-105">SSO 仅在域帐户下起作用</span><span class="sxs-lookup"><span data-stu-id="33eeb-105">SSO only functions under a domain account</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="33eeb-106">若要创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="33eeb-106">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="33eeb-107">在 Control Panel 中，打开**服务**，并验证企业单一登录服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="33eeb-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="33eeb-108">在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="33eeb-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="33eeb-109">例如：</span><span class="sxs-lookup"><span data-stu-id="33eeb-109">For example:</span></span>  
  
     <span data-ttu-id="33eeb-110">**C:\Program Files\Common Files\Enterprise 上单一登录 >**</span><span class="sxs-lookup"><span data-stu-id="33eeb-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="33eeb-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="33eeb-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="33eeb-112">有关命令的列表，使用**-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="33eeb-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="33eeb-113">若要使用 *.XML 作为创建关联应用程序的起始操作，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="33eeb-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="33eeb-114">其中：</span><span class="sxs-lookup"><span data-stu-id="33eeb-114">where:</span></span>  
  
    -   <span data-ttu-id="33eeb-115">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="33eeb-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="33eeb-116">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="33eeb-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="33eeb-117">例如：</span><span class="sxs-lookup"><span data-stu-id="33eeb-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO EMS App">  
            <description>TIBCO EMS SSO Application</description>  
            <contact>someone@example.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
            <!—an existing group on the domain controller - >   
            <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
            <!-- an existing account in the domain group - >   
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
    </SSO>  
    ```  
  
 <span data-ttu-id="33eeb-118">通过使用示例 XML，关联应用程序（TIBCO EMS App）会包含命令提示符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="33eeb-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="33eeb-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="33eeb-119">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="33eeb-120">键入以下命令以便控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="33eeb-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="33eeb-121">回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="33eeb-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="33eeb-122">完成时，你将收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="33eeb-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="33eeb-123">**使用此计算机上的 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="33eeb-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="33eeb-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="33eeb-124">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="33eeb-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="33eeb-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  <span data-ttu-id="33eeb-126">键入以下命令列出应用程序并验证是否已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="33eeb-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="33eeb-127">列表中将显示可供使用的关联应用程序：</span><span class="sxs-lookup"><span data-stu-id="33eeb-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
     <span data-ttu-id="33eeb-128">**有关 IBI\YourID-TIBCO EMSApp 可用应用程序**</span><span class="sxs-lookup"><span data-stu-id="33eeb-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3.  <span data-ttu-id="33eeb-129">键入以下命令以设置应用程序凭据的关联：</span><span class="sxs-lookup"><span data-stu-id="33eeb-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  <span data-ttu-id="33eeb-130">在提示符下输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="33eeb-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="33eeb-131">输入 TIBCO EMS App 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="33eeb-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
     <span data-ttu-id="33eeb-132">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="33eeb-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="33eeb-133">用户 ID:**用户**</span><span class="sxs-lookup"><span data-stu-id="33eeb-133">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="33eeb-134">密码：`******`</span><span class="sxs-lookup"><span data-stu-id="33eeb-134">Password: `******`</span></span>  
  
    -   <span data-ttu-id="33eeb-135">确认？</span><span class="sxs-lookup"><span data-stu-id="33eeb-135">Confirm?</span></span> <span data-ttu-id="33eeb-136">密码：`******`</span><span class="sxs-lookup"><span data-stu-id="33eeb-136">Password: `******`</span></span>  
  
     <span data-ttu-id="33eeb-137">关联应用程序中的 BizTalk Adapter 显示个 TIBCO EMS**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="33eeb-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33eeb-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33eeb-138">See Also</span></span>  
 [<span data-ttu-id="33eeb-139">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="33eeb-139">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)