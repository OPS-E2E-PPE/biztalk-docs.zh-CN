---
title: "创建 PeopleSoft 企业的关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a77926fa9d98606770ad2fe7715a3b0ff66ea5c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="80446-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="80446-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="80446-103">下列步骤显示如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="80446-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80446-104">如果收到 SSO 错误，请确认您在配置 BizTalk Server 时使用的是域帐户，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="80446-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="80446-105">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="80446-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="80446-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="80446-106">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="80446-107">在 Control Panel 中，打开**服务**，并验证企业单一登录服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="80446-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="80446-108">在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="80446-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="80446-109">例如：</span><span class="sxs-lookup"><span data-stu-id="80446-109">For example:</span></span>  
  
     <span data-ttu-id="80446-110">**C:\Program Files\Common Files\Enterprise 上单一登录 >**</span><span class="sxs-lookup"><span data-stu-id="80446-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="80446-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="80446-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="80446-112">有关命令的列表，使用**-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="80446-112">For a list of commands, use the **-help** switch.</span></span>  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  <span data-ttu-id="80446-113">若要使用 *.XML 作为创建关联应用程序的起始操作，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="80446-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="80446-114">其中：</span><span class="sxs-lookup"><span data-stu-id="80446-114">where:</span></span>  
  
    -   <span data-ttu-id="80446-115">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="80446-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="80446-116">AffiliateApplication.xml 是已创建的包含登录信息的应用程序 XML。</span><span class="sxs-lookup"><span data-stu-id="80446-116">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="80446-117">例如：</span><span class="sxs-lookup"><span data-stu-id="80446-117">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="80446-118">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="80446-118">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="80446-119">键入以下命令以便控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="80446-119">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="80446-120">回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="80446-120">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="80446-121">完成时，你将收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="80446-121">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="80446-122">**使用此计算机上的 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="80446-122">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="80446-123">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="80446-123">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="80446-124">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="80446-124">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="80446-125">键入以下命令列出应用程序并验证是否已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="80446-125">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="80446-126">列表中将显示可供使用的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="80446-126">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="80446-127">**有关 IBI\YourID-PeopleSoftApp 可用应用程序**</span><span class="sxs-lookup"><span data-stu-id="80446-127">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="80446-128">键入以下命令以设置应用程序凭据的关联：</span><span class="sxs-lookup"><span data-stu-id="80446-128">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="80446-129">在提示符下输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="80446-129">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="80446-130">输入 PeopleSoftApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="80446-130">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="80446-131">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="80446-131">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="80446-132">**用户 ID:**`user`</span><span class="sxs-lookup"><span data-stu-id="80446-132">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="80446-133">**密码：**`******`</span><span class="sxs-lookup"><span data-stu-id="80446-133">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="80446-134">**确认？密码：**`******`</span><span class="sxs-lookup"><span data-stu-id="80446-134">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="80446-135">关联应用程序将显示在用于 PeopleSoft Enterprise 的 BizTalk 适配器的“传输属性”对话框中。</span><span class="sxs-lookup"><span data-stu-id="80446-135">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80446-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80446-136">See Also</span></span>  
 [<span data-ttu-id="80446-137">安全适配器</span><span class="sxs-lookup"><span data-stu-id="80446-137">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)