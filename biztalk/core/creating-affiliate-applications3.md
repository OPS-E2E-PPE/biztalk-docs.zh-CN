---
title: 创建关联 Applications3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48aaf4d7cd6df05d99f31a9ddce7c6ccb6e7ae68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353950"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="b26d0-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="b26d0-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="b26d0-103">以下步骤介绍如何开始使用单一登录 (SSO) 关联应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="b26d0-103">The following steps describe how to get started with affiliate applications using Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26d0-104">如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为这会影响 ESSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="b26d0-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the ESSO service.</span></span> <span data-ttu-id="b26d0-105">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="b26d0-105">SSO only functions under a domain account.</span></span>  
  
## <a name="creating-an-affiliate-application"></a><span data-ttu-id="b26d0-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="b26d0-106">Creating an Affiliate Application</span></span>  
  
#### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="b26d0-107">若要创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="b26d0-107">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="b26d0-108">在中**Control Panel**，打开**服务**，并验证是否正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="b26d0-108">In **Control Panel**, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="b26d0-109">在命令提示符中，将目录更改为 Enterprise Single Sign-on 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b26d0-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="b26d0-110">例如：</span><span class="sxs-lookup"><span data-stu-id="b26d0-110">For example:</span></span>  
  
     <span data-ttu-id="b26d0-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="b26d0-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="b26d0-112">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="b26d0-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="b26d0-113">对于命令的列表，请使用-help 开关。</span><span class="sxs-lookup"><span data-stu-id="b26d0-113">For a list of commands, use the -help switch.</span></span>  
  
     <span data-ttu-id="b26d0-114">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="b26d0-114">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4.  <span data-ttu-id="b26d0-115">若要创建关联应用程序使用 \*。XML 作为一个开始，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b26d0-115">To create the affiliate application using the \*.XML as a beginning, type in the following command:</span></span>  
  
     <span data-ttu-id="b26d0-116">**ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**</span><span class="sxs-lookup"><span data-stu-id="b26d0-116">**ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**</span></span>  
  
     <span data-ttu-id="b26d0-117">其中：</span><span class="sxs-lookup"><span data-stu-id="b26d0-117">where:</span></span>  
  
     <span data-ttu-id="b26d0-118">C:\SSOtest 是包含 XML 应用程序的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b26d0-118">C:\SSOtest is the folder containing your application XML.</span></span>  
  
     <span data-ttu-id="b26d0-119">AffiliateApplication.xml 是应用程序创建包含登录信息的 XML。</span><span class="sxs-lookup"><span data-stu-id="b26d0-119">AffiliateApplication.xml is the application XML you created containing the Sign On information.</span></span>  
  
     <span data-ttu-id="b26d0-120">例如：</span><span class="sxs-lookup"><span data-stu-id="b26d0-120">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="JDEdwardsApp">  
              <description>JDEdwards SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
              <userGroup>ibi\Domain Users</userGroup>  
              <!—-an existing group on the domain controller - >   
              <appAdminGroup>ibi\YourID</appAdminGroup>  
              <!-- an existing account within the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a><span data-ttu-id="b26d0-121">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="b26d0-121">Creating Single Sign-On Tickets</span></span>  
  
#### <a name="to-create-sso-tickets"></a><span data-ttu-id="b26d0-122">若要创建 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="b26d0-122">To create SSO tickets</span></span>  
  
1.  <span data-ttu-id="b26d0-123">键入以下命令来控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="b26d0-123">Type in the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="b26d0-124">回答的问题：</span><span class="sxs-lookup"><span data-stu-id="b26d0-124">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="b26d0-125">完成后你收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="b26d0-125">On completion you receive a confirmation:</span></span>  
  
     <span data-ttu-id="b26d0-126">**在此计算机上使用 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="b26d0-126">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enabling-the-affiliate-application-xml"></a><span data-ttu-id="b26d0-127">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="b26d0-127">Enabling the Affiliate Application XML</span></span>  
  
#### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="b26d0-128">若要启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="b26d0-128">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="b26d0-129">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b26d0-129">Type in the following command:</span></span>  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  <span data-ttu-id="b26d0-130">键入以下命令以列出的应用程序并验证已创建应用程序中：</span><span class="sxs-lookup"><span data-stu-id="b26d0-130">Type in the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="b26d0-131">列表中将显示关联应用程序可供使用。</span><span class="sxs-lookup"><span data-stu-id="b26d0-131">The Affiliate Applications available for use appear in a list.</span></span>  
  
     <span data-ttu-id="b26d0-132">**可用的应用程序用于 IBI\YourID-JDEdwardsApp**</span><span class="sxs-lookup"><span data-stu-id="b26d0-132">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3.  <span data-ttu-id="b26d0-133">键入以下命令，设置关联应用程序凭据：</span><span class="sxs-lookup"><span data-stu-id="b26d0-133">Type in the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  <span data-ttu-id="b26d0-134">输入用户名和密码在提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="b26d0-134">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="b26d0-135">输入 JDEdwardsApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="b26d0-135">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span> <span data-ttu-id="b26d0-136">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="b26d0-136">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="b26d0-137">**用户 ID:** 用户</span><span class="sxs-lookup"><span data-stu-id="b26d0-137">**User ID:** user</span></span>  
  
    -   <span data-ttu-id="b26d0-138">**密码：** \*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b26d0-138">**Password:** \*\*\*\*\*\*</span></span>  
  
    -   <span data-ttu-id="b26d0-139">**确认？密码：** \*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b26d0-139">**Confirm? Password:** \*\*\*\*\*\*</span></span>  
  
5.  <span data-ttu-id="b26d0-140">用于 JD Edwards OneWorld 传输属性对话框中的 BizTalk 适配器的下拉列表中显示的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b26d0-140">The affiliate application appears in the drop-down list of the BizTalk Adapter for JD Edwards OneWorld Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26d0-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="b26d0-141">See Also</span></span>  
 [<span data-ttu-id="b26d0-142">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="b26d0-142">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)