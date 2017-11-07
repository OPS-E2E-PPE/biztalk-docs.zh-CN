---
title: "创建 Affiliate Applications3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 857ee7edd623332e72176ac09082f0ec9fc460f4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="f0886-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="f0886-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="f0886-103">下列步骤介绍了如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="f0886-103">The following steps describe how to get started with affiliate applications using Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0886-104">如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户，因为它会影响 ESSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="f0886-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the ESSO service.</span></span> <span data-ttu-id="f0886-105">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="f0886-105">SSO only functions under a domain account.</span></span>  
  
## <a name="creating-an-affiliate-application"></a><span data-ttu-id="f0886-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="f0886-106">Creating an Affiliate Application</span></span>  
  
#### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="f0886-107">若要创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="f0886-107">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="f0886-108">在**控制面板**，打开**服务**，并验证企业单一登录服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="f0886-108">In **Control Panel**, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="f0886-109">在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f0886-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="f0886-110">例如：</span><span class="sxs-lookup"><span data-stu-id="f0886-110">For example:</span></span>  
  
     <span data-ttu-id="f0886-111">**C:\Program Files\Common Files\Enterprise 上单一登录 >**</span><span class="sxs-lookup"><span data-stu-id="f0886-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="f0886-112">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="f0886-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="f0886-113">有关命令列表，请使用 -help 开关。</span><span class="sxs-lookup"><span data-stu-id="f0886-113">For a list of commands, use the -help switch.</span></span>  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  <span data-ttu-id="f0886-114">若要创建关联应用程序中使用 *。XML 作为一个开始，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0886-114">To create the affiliate application using the *.XML as a beginning, type in the following command:</span></span>  
  
     <span data-ttu-id="f0886-115">**ssomanage.exe createapps C:\SSOtest\AffiliateApplication.xml**</span><span class="sxs-lookup"><span data-stu-id="f0886-115">**ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**</span></span>  
  
     <span data-ttu-id="f0886-116">其中：</span><span class="sxs-lookup"><span data-stu-id="f0886-116">where:</span></span>  
  
     <span data-ttu-id="f0886-117">C:\SSOtest 是包含你的应用程序 XML 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f0886-117">C:\SSOtest is the folder containing your application XML.</span></span>  
  
     <span data-ttu-id="f0886-118">AffiliateApplication.xml 是应用程序创建包含登录信息的 XML。</span><span class="sxs-lookup"><span data-stu-id="f0886-118">AffiliateApplication.xml is the application XML you created containing the Sign On information.</span></span>  
  
     <span data-ttu-id="f0886-119">例如：</span><span class="sxs-lookup"><span data-stu-id="f0886-119">For example:</span></span>  
  
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
  
## <a name="creating-single-sign-on-tickets"></a><span data-ttu-id="f0886-120">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="f0886-120">Creating Single Sign-On Tickets</span></span>  
  
#### <a name="to-create-sso-tickets"></a><span data-ttu-id="f0886-121">创建 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="f0886-121">To create SSO tickets</span></span>  
  
1.  <span data-ttu-id="f0886-122">键入以下命令来控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="f0886-122">Type in the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="f0886-123">回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="f0886-123">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="f0886-124">完成后，您将收到以下确认：</span><span class="sxs-lookup"><span data-stu-id="f0886-124">On completion you receive a confirmation:</span></span>  
  
     <span data-ttu-id="f0886-125">**使用此计算机上的 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="f0886-125">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enabling-the-affiliate-application-xml"></a><span data-ttu-id="f0886-126">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="f0886-126">Enabling the Affiliate Application XML</span></span>  
  
#### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="f0886-127">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="f0886-127">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="f0886-128">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0886-128">Type in the following command:</span></span>  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  <span data-ttu-id="f0886-129">键入以下命令以列出应用程序并验证是否已创建该应用程序：</span><span class="sxs-lookup"><span data-stu-id="f0886-129">Type in the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="f0886-130">列表中显示 Affiliate 应用程序可供使用。</span><span class="sxs-lookup"><span data-stu-id="f0886-130">The Affiliate Applications available for use appear in a list.</span></span>  
  
     <span data-ttu-id="f0886-131">**有关 IBI\YourID-JDEdwardsApp 可用应用程序**</span><span class="sxs-lookup"><span data-stu-id="f0886-131">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3.  <span data-ttu-id="f0886-132">键入以下命令，设置关联应用程序的凭据：</span><span class="sxs-lookup"><span data-stu-id="f0886-132">Type in the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  <span data-ttu-id="f0886-133">在提示符下输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f0886-133">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="f0886-134">输入 JDEdwardsApp 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="f0886-134">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span> <span data-ttu-id="f0886-135">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="f0886-135">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="f0886-136">**用户 ID:**用户</span><span class="sxs-lookup"><span data-stu-id="f0886-136">**User ID:** user</span></span>  
  
    -   <span data-ttu-id="f0886-137">**密码：** ******</span><span class="sxs-lookup"><span data-stu-id="f0886-137">**Password:** ******</span></span>  
  
    -   <span data-ttu-id="f0886-138">**确认？密码：** ******</span><span class="sxs-lookup"><span data-stu-id="f0886-138">**Confirm? Password:** ******</span></span>  
  
5.  <span data-ttu-id="f0886-139">此关联应用程序显示在“JD Edwards OneWorld 传输属性”对话框的 BizTalk 适配器的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="f0886-139">The affiliate application appears in the drop-down list of the BizTalk Adapter for JD Edwards OneWorld Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0886-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0886-140">See Also</span></span>  
 [<span data-ttu-id="f0886-141">适配器中的安全</span><span class="sxs-lookup"><span data-stu-id="f0886-141">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)