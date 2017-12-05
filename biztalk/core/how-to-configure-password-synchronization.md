---
title: "如何配置密码同步 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2e8348cdf78db3e95ed75e5d83e6ea53bdffdee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-password-synchronization"></a><span data-ttu-id="a4f09-102">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="a4f09-102">How to Configure Password Synchronization</span></span>
<span data-ttu-id="a4f09-103">使用 SSOCONFIG 命令行实用工具可配置密码同步设置。</span><span class="sxs-lookup"><span data-stu-id="a4f09-103">Use the SSOCONFIG command line utility to configure your password synchronization settings.</span></span>  
  
### <a name="to-specify-the-directory-for-replay-files"></a><span data-ttu-id="a4f09-104">为重播文件指定目录</span><span class="sxs-lookup"><span data-stu-id="a4f09-104">To specify the directory for replay files</span></span>  
  
1.  <span data-ttu-id="a4f09-105">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="a4f09-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="a4f09-106">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4f09-106">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="a4f09-107">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="a4f09-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a4f09-108">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="a4f09-108">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="a4f09-109">类型**ssoconfig replayfiles\<重播文件目录\>&#124; 默认**，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="a4f09-109">Type **ssoconfig -replayfiles \<replay files directory\> &#124; -default** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4f09-110">更改服务帐户时不会删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="a4f09-110">Replay files are not deleted when you change the service account.</span></span> <span data-ttu-id="a4f09-111">如果更改此帐户，则需要手动删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="a4f09-111">If you change this account, you will need to delete the replay files manually.</span></span>  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a><span data-ttu-id="a4f09-112">显示或更改密码同步最长期限</span><span class="sxs-lookup"><span data-stu-id="a4f09-112">To display or change maximum password synchronization age</span></span>  
  
1.  <span data-ttu-id="a4f09-113">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="a4f09-113">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="a4f09-114">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4f09-114">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="a4f09-115">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="a4f09-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a4f09-116">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="a4f09-116">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="a4f09-117">类型**ssoconfig-syncage\<以小时为单位的密码最长期限\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="a4f09-117">Type **ssoconfig -syncage \<maximum password age in hours\>** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4f09-118">SSOCONFIG 实用工具将 SQL Server 计算机上的时间用作其系统时间。</span><span class="sxs-lookup"><span data-stu-id="a4f09-118">The SSOCONFIG utility uses the time on the SQL Server computer as its system time.</span></span> <span data-ttu-id="a4f09-119">在使用与时间相关的任何命令时，请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="a4f09-119">Remember this when using any commands related to time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f09-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4f09-120">See Also</span></span>  
 [<span data-ttu-id="a4f09-121">密码同步</span><span class="sxs-lookup"><span data-stu-id="a4f09-121">Password Synchronization</span></span>](../core/password-synchronization2.md)