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
ms.openlocfilehash: ca67c8637f3738169e9818795eebefd9faeabe70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390003"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="e911e-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e911e-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="e911e-103">以下步骤说明如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="e911e-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e911e-104">如果收到 SSO 错误，请验证域帐户时使用在配置 BizTalk Server，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="e911e-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="e911e-105">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="e911e-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="e911e-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e911e-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="e911e-107">在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="e911e-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="e911e-108">在命令提示符中，将目录更改为 Enterprise Single Sign-on 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e911e-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="e911e-109">例如：</span><span class="sxs-lookup"><span data-stu-id="e911e-109">For example:</span></span>  
  
    <span data-ttu-id="e911e-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="e911e-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="e911e-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="e911e-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="e911e-112">命令的列表，请 **-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="e911e-112">For a list of commands, use the **-help** switch.</span></span>  
  
    <span data-ttu-id="e911e-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="e911e-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4. <span data-ttu-id="e911e-114">若要使用创建的关联应用程序 \*。XML 作为一个开始，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e911e-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="e911e-115">其中：</span><span class="sxs-lookup"><span data-stu-id="e911e-115">where:</span></span>  
  
   - <span data-ttu-id="e911e-116">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e911e-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="e911e-117">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="e911e-117">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="e911e-118">例如：</span><span class="sxs-lookup"><span data-stu-id="e911e-118">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="e911e-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="e911e-119">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="e911e-120">键入以下命令来控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="e911e-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="e911e-121">回答的问题：</span><span class="sxs-lookup"><span data-stu-id="e911e-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="e911e-122">完成后，你将收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="e911e-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="e911e-123">**在此计算机上使用 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="e911e-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="e911e-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="e911e-124">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="e911e-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e911e-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="e911e-126">键入以下命令列出应用程序并验证已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="e911e-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="e911e-127">在列表中显示可供使用的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="e911e-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="e911e-128">**Applications available for IBI\YourID - PeopleSoftApp**</span><span class="sxs-lookup"><span data-stu-id="e911e-128">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="e911e-129">键入以下命令，设置关联应用程序凭据：</span><span class="sxs-lookup"><span data-stu-id="e911e-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="e911e-130">输入用户名和密码在提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="e911e-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="e911e-131">输入 PeopleSoftApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="e911e-131">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="e911e-132">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="e911e-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="e911e-133">**用户 ID:** `user`</span><span class="sxs-lookup"><span data-stu-id="e911e-133">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="e911e-134">**密码：** `******`</span><span class="sxs-lookup"><span data-stu-id="e911e-134">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="e911e-135">**确认？密码：** `******`</span><span class="sxs-lookup"><span data-stu-id="e911e-135">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="e911e-136">关联应用程序将显示在 PeopleSoft Enterprise 传输属性对话框的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="e911e-136">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e911e-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e911e-137">See Also</span></span>  
 [<span data-ttu-id="e911e-138">保护适配器</span><span class="sxs-lookup"><span data-stu-id="e911e-138">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)