---
title: 如何更新 SSO 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets [SSO], modifying
- managing [SSO], modifying Credential cache timeout
- tickets [SSO], timeouts
- modifying, SSO database
- managing [SSO], modifying ticket timeouts
- SSO database, modifying
ms.assetid: 45eb6a77-d91a-44a8-b26d-05508c288c36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbb7ea650a2845d8ebdcdcc2204f8346c5737c43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971315"
---
# <a name="how-to-update-the-sso-database"></a><span data-ttu-id="c4e63-102">如何更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="c4e63-102">How to Update the SSO Database</span></span>
<span data-ttu-id="c4e63-103">可以使用 MMC 管理单元或命令行来更改 SSO 数据库中诸如主密钥服务器标识、帐户名、数据库中的审核、票证超时和凭据缓存超时之类的全局信息。</span><span class="sxs-lookup"><span data-stu-id="c4e63-103">You can change the global information in the SSO database, such as the master secret server identification, the account names, auditing in the database, ticket timeout, and credential cache timeout, by using either the MMC Snap-In or the command line.</span></span>  
  
## <a name="changing-timeouts-for-the-sso-system"></a><span data-ttu-id="c4e63-104">更改 SSO 系统的超时</span><span class="sxs-lookup"><span data-stu-id="c4e63-104">Changing timeouts for the SSO System</span></span>  
 <span data-ttu-id="c4e63-105">可以在企业单一登录 (SSO) 系统级别上修改两个超时：</span><span class="sxs-lookup"><span data-stu-id="c4e63-105">You can modify two timeouts at the Enterprise Single Sign-On (SSO) system level:</span></span>  
  
 <span data-ttu-id="c4e63-106">**票证超时。**</span><span class="sxs-lookup"><span data-stu-id="c4e63-106">**Ticket timeout.**</span></span> <span data-ttu-id="c4e63-107">此属性指定 SSO 颁发的票据的有效时长。</span><span class="sxs-lookup"><span data-stu-id="c4e63-107">This property specifies the length of time for which a ticket SSO issues is valid.</span></span> <span data-ttu-id="c4e63-108">为满足企业中使用 SSO 的大部分情况，默认的票证超时为 2 分钟。</span><span class="sxs-lookup"><span data-stu-id="c4e63-108">To satisfy most of the scenarios in an enterprise that use SSO, the default ticket timeout is 2 minutes.</span></span> <span data-ttu-id="c4e63-109">SSO 管理员可以根据应用程序要求来更改此属性。</span><span class="sxs-lookup"><span data-stu-id="c4e63-109">The SSO administrator can change this based on the application requirements.</span></span>  
  
 <span data-ttu-id="c4e63-110">**凭据缓存超时值。**</span><span class="sxs-lookup"><span data-stu-id="c4e63-110">**Credential Cache timeout.**</span></span> <span data-ttu-id="c4e63-111">此属性可指定所有 SSO 服务器的凭据缓冲超时。</span><span class="sxs-lookup"><span data-stu-id="c4e63-111">This property specifies the credential cache timeout for all SSO Servers.</span></span> <span data-ttu-id="c4e63-112">SSO 服务器在第一次查找后将对凭据进行缓存。</span><span class="sxs-lookup"><span data-stu-id="c4e63-112">SSO Servers cache the credentials after the first lookup.</span></span> <span data-ttu-id="c4e63-113">默认情况下，凭据缓存超时为 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="c4e63-113">By default, the credential cache timeout is 60 minutes.</span></span> <span data-ttu-id="c4e63-114">SSO 管理员可以根据安全要求将此属性更改为适当的值。</span><span class="sxs-lookup"><span data-stu-id="c4e63-114">The SSO administrator can change this to a suitable value based on the security requirements.</span></span>  
  
 <span data-ttu-id="c4e63-115">通过更新 SSO 数据库，可以更改这两种超时。</span><span class="sxs-lookup"><span data-stu-id="c4e63-115">You change both of these timeouts by updating the SSO database.</span></span>  
  
 <span data-ttu-id="c4e63-116">更新 SSO 数据库的示例 XML 文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4e63-116">A sample XML file for updating the SSO database is:</span></span>  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
<secretServer>ComputerA</secretServer>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
<ticketTimeout>2</ticketTimeout>  
<credCacheTimeout>60</credCacheTimeout>  
</globalInfo>  
</sso>  
  
```  
  
#### <a name="to-change-timeouts-using-the-mmc-snap-in"></a><span data-ttu-id="c4e63-117">使用 MMC 管理单元更改超时</span><span class="sxs-lookup"><span data-stu-id="c4e63-117">To change timeouts using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="c4e63-118">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="c4e63-118">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="c4e63-119">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="c4e63-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="c4e63-120">右键单击“系统” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="c4e63-120">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c4e63-121">在“系统属性”  对话框上，单击“常规”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="c4e63-121">On the **System Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="c4e63-122">输入相应的设置，然后单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c4e63-122">Enter the appropriate settings, and click **OK**.</span></span>  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="c4e63-123">使用 MMC 管理单元更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="c4e63-123">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="c4e63-124">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="c4e63-124">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="c4e63-125">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="c4e63-125">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="c4e63-126">右键单击“系统” ，然后单击“升级数据库” 。</span><span class="sxs-lookup"><span data-stu-id="c4e63-126">Right-click **System**, and then click **Upgrade Database**.</span></span>  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="c4e63-127">使用命令行更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="c4e63-127">To update the SSO database using the command line</span></span>  
  
1.  <span data-ttu-id="c4e63-128">依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="c4e63-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="c4e63-129">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="c4e63-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="c4e63-130">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="c4e63-130">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="c4e63-131">类型**ssomanage-updatedb\<更新文件\>**，其中**\<更新文件\>** 是路径和文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c4e63-131">Type **ssomanage –updatedb \<update file\>**, where **\<update file\>** is the path and name of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4e63-132">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c4e63-132">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e63-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4e63-133">See Also</span></span>  
 <span data-ttu-id="c4e63-134">[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="c4e63-134">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="c4e63-135">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="c4e63-135">Using SSO</span></span>](../core/using-sso.md)