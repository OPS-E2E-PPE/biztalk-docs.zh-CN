---
title: 创建用于 TIBCO EMS 的关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 325b663f569b9cfce6fab8a65cc8b1f400d9d263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353931"
---
# <a name="create-affiliate-applications"></a><span data-ttu-id="12f3c-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="12f3c-102">Create Affiliate Applications</span></span>
<span data-ttu-id="12f3c-103">以下步骤介绍如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="12f3c-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12f3c-104">如果收到 SSO 错误，请验证您配置 BizTalk Server; 时使用域帐户这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="12f3c-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="12f3c-105">SSO 仅在域帐户下起作用</span><span class="sxs-lookup"><span data-stu-id="12f3c-105">SSO only functions under a domain account</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="12f3c-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="12f3c-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="12f3c-107">在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="12f3c-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="12f3c-108">在命令提示符中，将目录更改为 Enterprise Single Sign-on 文件夹。</span><span class="sxs-lookup"><span data-stu-id="12f3c-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="12f3c-109">例如：</span><span class="sxs-lookup"><span data-stu-id="12f3c-109">For example:</span></span>  
  
    <span data-ttu-id="12f3c-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="12f3c-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="12f3c-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="12f3c-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="12f3c-112">命令的列表，请 **-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="12f3c-112">For a list of commands, use the **-help** switch.</span></span>  
  
4. <span data-ttu-id="12f3c-113">若要使用创建的关联应用程序 \*。XML 作为一个开始，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="12f3c-113">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="12f3c-114">其中：</span><span class="sxs-lookup"><span data-stu-id="12f3c-114">where:</span></span>  
  
   - <span data-ttu-id="12f3c-115">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="12f3c-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="12f3c-116">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="12f3c-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="12f3c-117">例如：</span><span class="sxs-lookup"><span data-stu-id="12f3c-117">For example:</span></span>  
  
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
  
   <span data-ttu-id="12f3c-118">通过使用示例 XML，关联应用程序，TIBCO EMS App 包含的值，如在命令提示符中所示。</span><span class="sxs-lookup"><span data-stu-id="12f3c-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="12f3c-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="12f3c-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="12f3c-120">键入以下命令来控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="12f3c-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="12f3c-121">回答的问题：</span><span class="sxs-lookup"><span data-stu-id="12f3c-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="12f3c-122">完成后，你将收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="12f3c-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="12f3c-123">**在此计算机上使用 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="12f3c-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="12f3c-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="12f3c-124">Enable affiliate application XML</span></span>  
  
1. <span data-ttu-id="12f3c-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="12f3c-125">Type the following command:</span></span>  
  
    `ssomanage -enableapp TIBCO EMSApp`  
  
2. <span data-ttu-id="12f3c-126">键入以下命令列出应用程序并验证已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="12f3c-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
    `ssoclient.exe –listapps`  
  
    <span data-ttu-id="12f3c-127">在列表中显示可供使用的关联应用程序：</span><span class="sxs-lookup"><span data-stu-id="12f3c-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
    <span data-ttu-id="12f3c-128">**可用的应用程序用于 IBI\YourID-TIBCO emsapp 的应用程序**</span><span class="sxs-lookup"><span data-stu-id="12f3c-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3. <span data-ttu-id="12f3c-129">键入以下命令，设置关联应用程序凭据：</span><span class="sxs-lookup"><span data-stu-id="12f3c-129">Type the following command to set the affiliate application credentials:</span></span>  
  
    `soclient.exe -setcredentials TIBCO EMSApp`  
  
4. <span data-ttu-id="12f3c-130">输入用户名和密码在提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="12f3c-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="12f3c-131">输入 TIBCO EMS App 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="12f3c-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
    <span data-ttu-id="12f3c-132">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="12f3c-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
   - <span data-ttu-id="12f3c-133">用户 ID:**用户**</span><span class="sxs-lookup"><span data-stu-id="12f3c-133">User ID: **user**</span></span>  
  
   - <span data-ttu-id="12f3c-134">密码： `******`</span><span class="sxs-lookup"><span data-stu-id="12f3c-134">Password: `******`</span></span>  
  
   - <span data-ttu-id="12f3c-135">确认？</span><span class="sxs-lookup"><span data-stu-id="12f3c-135">Confirm?</span></span> <span data-ttu-id="12f3c-136">密码： `******`</span><span class="sxs-lookup"><span data-stu-id="12f3c-136">Password: `******`</span></span>  
  
     <span data-ttu-id="12f3c-137">关联应用程序将显示在 BizTalk 适配器用于 TIBCO EMS**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12f3c-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f3c-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="12f3c-138">See Also</span></span>  
[<span data-ttu-id="12f3c-139">保护适配器</span><span class="sxs-lookup"><span data-stu-id="12f3c-139">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)