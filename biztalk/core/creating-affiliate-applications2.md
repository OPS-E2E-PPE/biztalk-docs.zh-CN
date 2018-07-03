---
title: 创建适用于 PeopleSoft Enterprise 的关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f436c9c3193a895d38df630c1bec88abfadc12c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022883"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="bec7d-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="bec7d-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="bec7d-103">下列步骤显示如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="bec7d-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bec7d-104">如果收到 SSO 错误，请确认您在配置 BizTalk Server 时使用的是域帐户，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="bec7d-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="bec7d-105">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="bec7d-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="bec7d-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="bec7d-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="bec7d-107">在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="bec7d-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="bec7d-108">在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bec7d-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="bec7d-109">例如：</span><span class="sxs-lookup"><span data-stu-id="bec7d-109">For example:</span></span>  
  
    <span data-ttu-id="bec7d-110">**C:\Program Files\Common Files\Enterprise Single Sign-on >**</span><span class="sxs-lookup"><span data-stu-id="bec7d-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="bec7d-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="bec7d-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="bec7d-112">命令的列表，请 **-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="bec7d-112">For a list of commands, use the **-help** switch.</span></span>  
  
    <span data-ttu-id="bec7d-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="bec7d-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4. <span data-ttu-id="bec7d-114">若要使用 \*.XML 作为创建关联应用程序的起始操作，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="bec7d-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="bec7d-115">其中：</span><span class="sxs-lookup"><span data-stu-id="bec7d-115">where:</span></span>  
  
   - <span data-ttu-id="bec7d-116">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bec7d-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="bec7d-117">AffiliateApplication.xml 是已创建的包含登录信息的应用程序 XML。</span><span class="sxs-lookup"><span data-stu-id="bec7d-117">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="bec7d-118">例如：</span><span class="sxs-lookup"><span data-stu-id="bec7d-118">For example:</span></span>  
  
   ```  
   <?xml version="1.0"?>  
   <SSO>  
        <application name="PeopleSoftApp">  
             <description>PeopleSoft SSO Application</description>  
             <contact>someone@microsoft.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
             <!—-an existing group on the domain controller - >   
             <appAdminAccount>DomainName\AppAdminGroup<appAdminAccount>   
             <!-- an existing account in the domain group - >   
             <field ordinal="0" label="User ID" masked="no" />  
             <field ordinal="1" label="Password" masked="yes" />  
             <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
   </SSO>  
   ```  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="bec7d-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="bec7d-119">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="bec7d-120">键入以下命令以便控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="bec7d-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="bec7d-121">回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="bec7d-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="bec7d-122">完成后，你将收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="bec7d-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="bec7d-123">**在此计算机上使用 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="bec7d-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="bec7d-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="bec7d-124">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="bec7d-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="bec7d-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="bec7d-126">键入以下命令列出应用程序并验证是否已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="bec7d-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="bec7d-127">列表中将显示可供使用的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="bec7d-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="bec7d-128">**可用的应用程序用于 IBI\YourID-PeopleSoftApp**</span><span class="sxs-lookup"><span data-stu-id="bec7d-128">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="bec7d-129">键入以下命令，设置关联应用程序凭据：</span><span class="sxs-lookup"><span data-stu-id="bec7d-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="bec7d-130">在提示符下输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="bec7d-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="bec7d-131">输入 PeopleSoftApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="bec7d-131">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="bec7d-132">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="bec7d-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="bec7d-133">**用户 ID:** `user`</span><span class="sxs-lookup"><span data-stu-id="bec7d-133">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="bec7d-134">**密码：** `******`</span><span class="sxs-lookup"><span data-stu-id="bec7d-134">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="bec7d-135">**确认？密码：** `******`</span><span class="sxs-lookup"><span data-stu-id="bec7d-135">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="bec7d-136">关联应用程序将显示在用于 PeopleSoft Enterprise 的 BizTalk 适配器的“传输属性”对话框中。</span><span class="sxs-lookup"><span data-stu-id="bec7d-136">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec7d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="bec7d-137">See Also</span></span>  
 [<span data-ttu-id="bec7d-138">保护适配器</span><span class="sxs-lookup"><span data-stu-id="bec7d-138">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)