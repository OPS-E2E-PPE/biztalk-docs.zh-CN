---
title: 创建关联 Applications4 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets, Single Sign-On
- affiliate applications, setting credentials
- affiliate applications
- Single Sign-On, creating tickets
- SSO tickets
ms.assetid: 790fbe21-8081-4d57-803f-23014c8a3135
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e240fbc99705c18a0e789a1ddea0e26d8f479e55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984038"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="d5b81-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="d5b81-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="d5b81-103">以下步骤介绍如何使用 SSO 开始使用关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5b81-103">The following steps describe how to get started with affiliate applications using SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5b81-104">如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="d5b81-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="d5b81-105">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="d5b81-105">SSO only functions under a domain account.</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="d5b81-106">若要创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="d5b81-106">To create an affiliate application</span></span>  
  
1. <span data-ttu-id="d5b81-107">在控制面板中，打开**Services**，并验证是否正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="d5b81-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="d5b81-108">在命令提示符下，将目录更改为 Enterprise Single Sign On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5b81-108">In a command prompt, change directories to the Enterprise Single Sign On folder.</span></span>  
  
    <span data-ttu-id="d5b81-109">例如：</span><span class="sxs-lookup"><span data-stu-id="d5b81-109">For example:</span></span>  
  
    <span data-ttu-id="d5b81-110">**C:\Program Files\Common Files\Enterprise Single Sign-on >**</span><span class="sxs-lookup"><span data-stu-id="d5b81-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="d5b81-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="d5b81-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="d5b81-112">命令的列表，请 **-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="d5b81-112">For a list of commands, use the **-help** switch.</span></span>  
  
4. <span data-ttu-id="d5b81-113">若要以使用 \*.XML 作为创建关联应用程序的起始操作，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d5b81-113">To create the affiliate application using \*.XML as a beginning, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="d5b81-114">其中：</span><span class="sxs-lookup"><span data-stu-id="d5b81-114">where:</span></span>  
  
   - <span data-ttu-id="d5b81-115">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5b81-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="d5b81-116">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="d5b81-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="d5b81-117">例如：</span><span class="sxs-lookup"><span data-stu-id="d5b81-117">For example:</span></span>  
  
   ```  
   <?xml version="1.0"?>  
   <SSO>  
       <application name="JDEdwardsApp">  
           <description>JDEdwards SSO Application</description>  
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
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="d5b81-118">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="d5b81-118">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="d5b81-119">键入以下命令以便控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="d5b81-119">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="d5b81-120">回答如下所示的问题：</span><span class="sxs-lookup"><span data-stu-id="d5b81-120">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="d5b81-121">完成后，你将收到以下确认：</span><span class="sxs-lookup"><span data-stu-id="d5b81-121">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="d5b81-122">**在此计算机上使用 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="d5b81-122">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="d5b81-123">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="d5b81-123">To enable affiliate application XML</span></span>  
  
1. <span data-ttu-id="d5b81-124">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d5b81-124">Type the following command:</span></span>  
  
    `ssomanage -enableapp JDEdwardsApp`  
  
2. <span data-ttu-id="d5b81-125">键入以下命令列出应用程序并验证是否已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="d5b81-125">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
    `ssoclient.exe –listapps`  
  
    <span data-ttu-id="d5b81-126">可用于关联应用程序使用显示在列表中：</span><span class="sxs-lookup"><span data-stu-id="d5b81-126">The affiliate applications that are available for use display in a list:</span></span>  
  
    <span data-ttu-id="d5b81-127">**可用的应用程序用于 IBI\YourID-JDEdwardsApp**</span><span class="sxs-lookup"><span data-stu-id="d5b81-127">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3. <span data-ttu-id="d5b81-128">键入以下命令，设置关联应用程序凭据：</span><span class="sxs-lookup"><span data-stu-id="d5b81-128">Type the following command to set the affiliate application credentials:</span></span>  
  
    `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4. <span data-ttu-id="d5b81-129">在提示符下输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="d5b81-129">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="d5b81-130">输入 JDEdwardsApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="d5b81-130">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span>  
  
    <span data-ttu-id="d5b81-131">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="d5b81-131">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
   - <span data-ttu-id="d5b81-132">用户 ID:**用户**</span><span class="sxs-lookup"><span data-stu-id="d5b81-132">User ID: **user**</span></span>  
  
   - <span data-ttu-id="d5b81-133">密码： `******`</span><span class="sxs-lookup"><span data-stu-id="d5b81-133">Password: `******`</span></span>  
  
   - <span data-ttu-id="d5b81-134">确认？</span><span class="sxs-lookup"><span data-stu-id="d5b81-134">Confirm?</span></span> <span data-ttu-id="d5b81-135">密码： `******`</span><span class="sxs-lookup"><span data-stu-id="d5b81-135">Password: `******`</span></span>  
  
     <span data-ttu-id="d5b81-136">关联应用程序将显示在 BizTalk 适配器用于 JD Edwards EnterpriseOne**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d5b81-136">The affiliate application appears in the BizTalk Adapter for JD Edwards EnterpriseOne **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b81-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5b81-137">See Also</span></span>  
 [<span data-ttu-id="d5b81-138">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="d5b81-138">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)