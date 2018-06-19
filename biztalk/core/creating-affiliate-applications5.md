---
title: 创建 TIBCO EMS 的关联应用程序 |Microsoft 文档
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
ms.openlocfilehash: ce5df15794886f9177f12f2a9e9a33e3ffdc335f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015284"
---
# <a name="create-affiliate-applications"></a><span data-ttu-id="ee4f4-102">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="ee4f4-102">Create Affiliate Applications</span></span>
<span data-ttu-id="ee4f4-103">以下步骤描述如何开始使用关联应用程序和单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee4f4-104">如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户；这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="ee4f4-105">SSO 仅在域帐户下起作用</span><span class="sxs-lookup"><span data-stu-id="ee4f4-105">SSO only functions under a domain account</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="ee4f4-106">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="ee4f4-106">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="ee4f4-107">在 Control Panel 中，打开**服务**，并验证企业单一登录服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="ee4f4-108">在命令提示符下，将目录更改为 Enterprise Single Sign-On 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="ee4f4-109">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-109">For example:</span></span>  
  
     <span data-ttu-id="ee4f4-110">**C:\Program Files\Common Files\Enterprise 上单一登录 >**</span><span class="sxs-lookup"><span data-stu-id="ee4f4-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="ee4f4-111">使用企业单一登录命令。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="ee4f4-112">有关命令的列表，使用 **-帮助**切换。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="ee4f4-113">若要使用 \*.XML 作为创建关联应用程序的起始操作，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-113">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="ee4f4-114">其中：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-114">where:</span></span>  
  
    -   <span data-ttu-id="ee4f4-115">C:\SSOtest 是您的应用程序 XML 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="ee4f4-116">AffiliateApplication.xml 是应用程序创建的 XML，其中包含登录信息。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="ee4f4-117">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-117">For example:</span></span>  
  
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
  
 <span data-ttu-id="ee4f4-118">通过使用示例 XML，关联应用程序（TIBCO EMS App）会包含命令提示符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="ee4f4-119">创建单一登录票证</span><span class="sxs-lookup"><span data-stu-id="ee4f4-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="ee4f4-120">键入以下命令以便控制 SSO 票证行为：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="ee4f4-121">回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="ee4f4-122">完成时，你将收到一条确认消息：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="ee4f4-123">**使用此计算机上的 SSO 服务器。已成功完成该操作。**</span><span class="sxs-lookup"><span data-stu-id="ee4f4-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="ee4f4-124">启用关联应用程序 XML</span><span class="sxs-lookup"><span data-stu-id="ee4f4-124">Enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="ee4f4-125">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  <span data-ttu-id="ee4f4-126">键入以下命令列出应用程序并验证是否已创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="ee4f4-127">列表中将显示可供使用的关联应用程序：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
     <span data-ttu-id="ee4f4-128">**有关 IBI\YourID-TIBCO EMSApp 可用应用程序**</span><span class="sxs-lookup"><span data-stu-id="ee4f4-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3.  <span data-ttu-id="ee4f4-129">键入以下命令以设置应用程序凭据的关联：</span><span class="sxs-lookup"><span data-stu-id="ee4f4-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  <span data-ttu-id="ee4f4-130">在提示符下输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="ee4f4-131">输入 TIBCO EMS App 关联应用程序的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
     <span data-ttu-id="ee4f4-132">例如，输入用户标识和该用户就可以通过 SSO 服务器系统中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="ee4f4-133">用户 ID:**用户**</span><span class="sxs-lookup"><span data-stu-id="ee4f4-133">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="ee4f4-134">密码：`******`</span><span class="sxs-lookup"><span data-stu-id="ee4f4-134">Password: `******`</span></span>  
  
    -   <span data-ttu-id="ee4f4-135">确认？</span><span class="sxs-lookup"><span data-stu-id="ee4f4-135">Confirm?</span></span> <span data-ttu-id="ee4f4-136">密码：`******`</span><span class="sxs-lookup"><span data-stu-id="ee4f4-136">Password: `******`</span></span>  
  
     <span data-ttu-id="ee4f4-137">关联应用程序中的 BizTalk Adapter 显示个 TIBCO EMS**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ee4f4-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4f4-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee4f4-138">See Also</span></span>  
[<span data-ttu-id="ee4f4-139">安全适配器</span><span class="sxs-lookup"><span data-stu-id="ee4f4-139">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)