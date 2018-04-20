---
title: 如何审核 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27528cf6da53c69db4b2bc6c9e1d296472b24186
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-audit-sso"></a><span data-ttu-id="e48d8-102">如何审核 SSO</span><span class="sxs-lookup"><span data-stu-id="e48d8-102">How to Audit SSO</span></span>
<span data-ttu-id="e48d8-103">可以使用 MMC 管理单元中或命令行设置这两种正值和负值审核级别。</span><span class="sxs-lookup"><span data-stu-id="e48d8-103">You can use the MMC Snap-In or the command line to set both the positive and negative auditing levels.</span></span> <span data-ttu-id="e48d8-104">审核的结果存储在事件日志和审核日志中的数据库。</span><span class="sxs-lookup"><span data-stu-id="e48d8-104">Results of the auditing are stored in both the event logs and the audit logs of the database.</span></span>  
  
 <span data-ttu-id="e48d8-105">SSO 管理员可以设置适合其公司策略的成功和失败审核级别。</span><span class="sxs-lookup"><span data-stu-id="e48d8-105">SSO administrators can set the positive and negative audit levels that suit their corporate policies.</span></span> <span data-ttu-id="e48d8-106">您可以将成功和失败审核设置为以下级别之一：</span><span class="sxs-lookup"><span data-stu-id="e48d8-106">You can set positive and negative audits to one of the following levels:</span></span>  
  
 <span data-ttu-id="e48d8-107">0 = 无</span><span class="sxs-lookup"><span data-stu-id="e48d8-107">0 = None</span></span>  
  
 <span data-ttu-id="e48d8-108">1 = 低</span><span class="sxs-lookup"><span data-stu-id="e48d8-108">1 = Low</span></span>  
  
 <span data-ttu-id="e48d8-109">2 = 中等</span><span class="sxs-lookup"><span data-stu-id="e48d8-109">2 = Medium</span></span>  
  
 <span data-ttu-id="e48d8-110">3 = 高。</span><span class="sxs-lookup"><span data-stu-id="e48d8-110">3 = High.</span></span> <span data-ttu-id="e48d8-111">此级别问题方式许多尽可能审核消息。</span><span class="sxs-lookup"><span data-stu-id="e48d8-111">This level issues as many audit messages as possible.</span></span>  
  
 <span data-ttu-id="e48d8-112">成功审核的默认值为 0（无），失败审核的默认值为 1（低）。</span><span class="sxs-lookup"><span data-stu-id="e48d8-112">The default value for positive auditing is 0 (none), and the default value for negative auditing is 1(low).</span></span>  
  
 <span data-ttu-id="e48d8-113">若要更改数据库级别审核，必须更新 SSO 数据库使用的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e48d8-113">To change the database level auditing, you must update the SSO database using an XML file.</span></span> <span data-ttu-id="e48d8-114">更新 SSO 数据库的示例 XML 文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="e48d8-114">A sample XML file for updating the SSO database is:</span></span>  
  
```  
<sso>  
<globalnfo>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
</globalInfo>  
</sso>  
  
```  
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a><span data-ttu-id="e48d8-115">审核上单一登录使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="e48d8-115">To audit Single Sign-On using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="e48d8-116">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="e48d8-116">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="e48d8-117">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="e48d8-117">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="e48d8-118">右键单击“系统” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="e48d8-118">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="e48d8-119">上  **系统属性** 对话框中，单击 **审核** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e48d8-119">On the  **System Properties** dialog box, click the **Audits** tab.</span></span>  
  
5.  <span data-ttu-id="e48d8-120">输入相应的设置，然后单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e48d8-120">Enter the appropriate settings, and click **OK**.</span></span>  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a><span data-ttu-id="e48d8-121">单一登录使用命令行审核</span><span class="sxs-lookup"><span data-stu-id="e48d8-121">To audit Single Sign-On using the command line</span></span>  
  
1.  <span data-ttu-id="e48d8-122">上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="e48d8-122">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="e48d8-123">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="e48d8-123">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e48d8-124">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="e48d8-124">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="e48d8-125">类型**ssoconfig-auditlevel\<正\>\<负\>**，其中**\<正\>**是的级别审核操作成功，和**\<负\>**是审核操作失败时的级别。</span><span class="sxs-lookup"><span data-stu-id="e48d8-125">Type **ssoconfig –auditlevel \<positive\>\<negative\>**, where **\<positive\>** is the level of auditing when actions succeed, and **\<negative\>** is the level of auditing when actions fail.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e48d8-126">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e48d8-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-audit-the-sso-database"></a><span data-ttu-id="e48d8-127">若要审核的 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="e48d8-127">To audit the SSO database</span></span>  
  
1.  <span data-ttu-id="e48d8-128">依次单击 **“开始”**和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="e48d8-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="e48d8-129">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="e48d8-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e48d8-130">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="e48d8-130">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="e48d8-131">类型**ssomanage-updatedb\<更新文件\>**，其中**\<更新文件\>**是路径和文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e48d8-131">Type **ssomanage –updatedb \<update file\>**, where **\<update file\>**is the path and name of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e48d8-132">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e48d8-132">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e48d8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e48d8-133">See Also</span></span>  
 <span data-ttu-id="e48d8-134">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="e48d8-134">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="e48d8-135">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="e48d8-135">Using SSO</span></span>](../core/using-sso.md)