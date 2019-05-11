---
title: 创建关联应用程序用于 TIBCO Rendezvous |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba94161fa534187392e64e6138b6f8ae18920377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354024"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="4dc14-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="4dc14-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="4dc14-103">以下步骤介绍如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="4dc14-103">The following steps describe how to start working with affiliate applications and Single Sign-On (SSO).</span></span> <span data-ttu-id="4dc14-104">有关如何使用企业单一登录的完整信息，请参阅 Microsoft 文档。</span><span class="sxs-lookup"><span data-stu-id="4dc14-104">For complete information about how to use Enterprise Single Sign-On, see the Microsoft documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dc14-105">如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="4dc14-105">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="4dc14-106">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="4dc14-106">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="4dc14-107">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="4dc14-107">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="4dc14-108">在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="4dc14-108">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="4dc14-109">在命令提示符中，将目录更改为 Enterprise Single Sign-on 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4dc14-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span> <span data-ttu-id="4dc14-110">例如：</span><span class="sxs-lookup"><span data-stu-id="4dc14-110">For example:</span></span>  
  
     <span data-ttu-id="4dc14-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="4dc14-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="4dc14-112">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="4dc14-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="4dc14-113">命令的列表，请 **-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="4dc14-113">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="4dc14-114">若要使用创建的关联应用程序 \*。XML 作为一个开始，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="4dc14-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="4dc14-115">其中：</span><span class="sxs-lookup"><span data-stu-id="4dc14-115">Where:</span></span>  
  
     <span data-ttu-id="4dc14-116">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4dc14-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
     <span data-ttu-id="4dc14-117">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="4dc14-117">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="4dc14-118">例如：</span><span class="sxs-lookup"><span data-stu-id="4dc14-118">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="4dc14-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="4dc14-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="4dc14-120">键入以下命令来控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="4dc14-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="4dc14-121">回答以下问题，如所示：</span><span class="sxs-lookup"><span data-stu-id="4dc14-121">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  <span data-ttu-id="4dc14-122">完成后，你将收到以下确认：</span><span class="sxs-lookup"><span data-stu-id="4dc14-122">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="4dc14-123">**在此计算机上使用 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="4dc14-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="4dc14-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="4dc14-124">Enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="4dc14-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="4dc14-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  <span data-ttu-id="4dc14-126">键入以下命令列出应用程序并验证已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="4dc14-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="4dc14-127">在列表中显示可供使用的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="4dc14-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="4dc14-128">**可用的应用程序用于 IBI\YourID-TIBCO RendezvousApp**</span><span class="sxs-lookup"><span data-stu-id="4dc14-128">**Applications available for IBI\YourID - TIBCO RendezvousApp**</span></span>  
  
3.  <span data-ttu-id="4dc14-129">键入以下命令，设置关联应用程序凭据：</span><span class="sxs-lookup"><span data-stu-id="4dc14-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  <span data-ttu-id="4dc14-130">输入用户名和密码在提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="4dc14-130">Enter the User name and password at the prompts.</span></span>  
  
5.  <span data-ttu-id="4dc14-131">输入 TIBCO RendezvousApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="4dc14-131">Enter the logon credentials for the TIBCO RendezvousApp affiliate application.</span></span>  
  
     <span data-ttu-id="4dc14-132">例如，输入用户标识和用户输入到通过 SSO 服务器系统的密码。</span><span class="sxs-lookup"><span data-stu-id="4dc14-132">For example, enter the user identification and the password for the user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="4dc14-133">用户 ID： 用户</span><span class="sxs-lookup"><span data-stu-id="4dc14-133">User ID: user</span></span>  
  
    -   <span data-ttu-id="4dc14-134">密码: \* \* \*</span><span class="sxs-lookup"><span data-stu-id="4dc14-134">Password: \*\*\*\*\*\*</span></span>  
  
    -   <span data-ttu-id="4dc14-135">确认密码: \* \* \*</span><span class="sxs-lookup"><span data-stu-id="4dc14-135">Confirm Password: \*\*\*\*\*\*</span></span>  
  
6.  <span data-ttu-id="4dc14-136">关联应用程序将显示在 BizTalk 适配器用于 TIBCO Rendezvous**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="4dc14-136">The affiliate application appears in the BizTalk Adapter for TIBCO Rendezvous **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc14-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc14-137">See Also</span></span>  
 [<span data-ttu-id="4dc14-138">用于 TIBCO Rendezvous 的 BizTalk 适配器的安全性</span><span class="sxs-lookup"><span data-stu-id="4dc14-138">Security in BizTalk Adapter for TIBCO Rendezvous</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   