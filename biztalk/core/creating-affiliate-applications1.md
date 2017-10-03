---
title: "创建 Affiliate Applications1 |Microsoft 文档"
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
- tickets, SSO
- affiliate applications, enabling XML
- SSO tickets
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f52c59caf451a2e0b55c775bf70a36a9a05ae9c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="e4768-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e4768-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="e4768-103">以下步骤描述如何开始使用项目应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="e4768-103">The following steps describe how to start working with affiliate applications and Single Sign-On (SSO).</span></span> <span data-ttu-id="e4768-104">有关如何使用企业单一登录的详细信息，请参阅 Microsoft 文档。</span><span class="sxs-lookup"><span data-stu-id="e4768-104">For complete information about how to use Enterprise Single Sign-On, see the Microsoft documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4768-105">如果你收到 SSO 错误，请验证使用域帐户时配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="e4768-105">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="e4768-106">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="e4768-106">SSO only functions under a domain account.</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="e4768-107">若要创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e4768-107">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="e4768-108">在 Control Panel 中，打开**服务**，并验证企业单一登录服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="e4768-108">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="e4768-109">在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4768-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span> <span data-ttu-id="e4768-110">例如：</span><span class="sxs-lookup"><span data-stu-id="e4768-110">For example:</span></span>  
  
     <span data-ttu-id="e4768-111">**C:\Program Files\Common Files\Enterprise 上单一登录 >**</span><span class="sxs-lookup"><span data-stu-id="e4768-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="e4768-112">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="e4768-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="e4768-113">有关命令的列表，使用**-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="e4768-113">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="e4768-114">若要使用 *.XML 作为创建关联应用程序的起始操作，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e4768-114">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="e4768-115">其中：</span><span class="sxs-lookup"><span data-stu-id="e4768-115">Where:</span></span>  
  
     <span data-ttu-id="e4768-116">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4768-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
     <span data-ttu-id="e4768-117">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="e4768-117">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="e4768-118">例如：</span><span class="sxs-lookup"><span data-stu-id="e4768-118">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO RendezvousApp">  
            <description> TIBCO Rendezvous SSO Application</description>  
            <contact>someone@microsoft.com</contact>  
            <userGroup>ibi\Domain Users</userGroup>  
            <!—an existing group on the domain controller - >   
            <appAdminGroup>ibi\YourID</appAdminGroup>  
            <!-- an existing account within the domain group - >   
  
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
  
        </application>  
    </SSO>  
    ```  
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="e4768-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="e4768-119">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="e4768-120">键入以下命令以便控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="e4768-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="e4768-121">回答如下所示的问题：</span><span class="sxs-lookup"><span data-stu-id="e4768-121">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  <span data-ttu-id="e4768-122">完成时，你将收到以下确认：</span><span class="sxs-lookup"><span data-stu-id="e4768-122">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="e4768-123">**使用此计算机上的 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="e4768-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="e4768-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="e4768-124">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="e4768-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e4768-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  <span data-ttu-id="e4768-126">键入以下命令列出应用程序并验证是否已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="e4768-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="e4768-127">列表中将显示可供使用的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4768-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="e4768-128">**有关 IBI\YourID-TIBCO RendezvousApp 可用应用程序**</span><span class="sxs-lookup"><span data-stu-id="e4768-128">**Applications available for IBI\YourID - TIBCO RendezvousApp**</span></span>  
  
3.  <span data-ttu-id="e4768-129">键入以下命令以设置应用程序凭据的关联：</span><span class="sxs-lookup"><span data-stu-id="e4768-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  <span data-ttu-id="e4768-130">输入用户名和密码提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="e4768-130">Enter the User name and password at the prompts.</span></span>  
  
5.  <span data-ttu-id="e4768-131">输入 TIBCO RendezvousApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="e4768-131">Enter the logon credentials for the TIBCO RendezvousApp affiliate application.</span></span>  
  
     <span data-ttu-id="e4768-132">例如，为通过 SSO 服务器进入系统的用户输入用户标识和密码。</span><span class="sxs-lookup"><span data-stu-id="e4768-132">For example, enter the user identification and the password for the user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="e4768-133">用户 ID：user</span><span class="sxs-lookup"><span data-stu-id="e4768-133">User ID: user</span></span>  
  
    -   <span data-ttu-id="e4768-134">密码: * * *</span><span class="sxs-lookup"><span data-stu-id="e4768-134">Password: ******</span></span>  
  
    -   <span data-ttu-id="e4768-135">确认密码: * * *</span><span class="sxs-lookup"><span data-stu-id="e4768-135">Confirm Password: ******</span></span>  
  
6.  <span data-ttu-id="e4768-136">关联应用程序中的 BizTalk Adapter 显示个 TIBCO 会合**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e4768-136">The affiliate application appears in the BizTalk Adapter for TIBCO Rendezvous **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4768-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4768-137">See Also</span></span>  
 <span data-ttu-id="e4768-138">[用于 TIBCO 会合的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="e4768-138">[Security in BizTalk Adapter for TIBCO Rendezvous](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="e4768-139">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="e4768-139">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)