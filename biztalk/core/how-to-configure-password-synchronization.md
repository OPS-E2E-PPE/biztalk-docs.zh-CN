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
ms.openlocfilehash: fb913c1719f4833ef36cf9f73f6a96432217f2af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-password-synchronization"></a><span data-ttu-id="12b33-102">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="12b33-102">How to Configure Password Synchronization</span></span>
<span data-ttu-id="12b33-103">使用 SSOCONFIG 命令行实用工具可配置密码同步设置。</span><span class="sxs-lookup"><span data-stu-id="12b33-103">Use the SSOCONFIG command line utility to configure your password synchronization settings.</span></span>  
  
### <a name="to-specify-the-directory-for-replay-files"></a><span data-ttu-id="12b33-104">为重播文件指定目录</span><span class="sxs-lookup"><span data-stu-id="12b33-104">To specify the directory for replay files</span></span>  
  
1.  <span data-ttu-id="12b33-105">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="12b33-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="12b33-106">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12b33-106">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="12b33-107">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="12b33-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="12b33-108">默认值是\<驱动器 >: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="12b33-108">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="12b33-109">类型**ssoconfig replayfiles\<重播文件目录 > &#124; 默认**，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="12b33-109">Type **ssoconfig -replayfiles \<replay files directory> &#124; -default** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12b33-110">更改服务帐户时不会删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="12b33-110">Replay files are not deleted when you change the service account.</span></span> <span data-ttu-id="12b33-111">如果更改此帐户，则需要手动删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="12b33-111">If you change this account, you will need to delete the replay files manually.</span></span>  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a><span data-ttu-id="12b33-112">显示或更改密码同步最长期限</span><span class="sxs-lookup"><span data-stu-id="12b33-112">To display or change maximum password synchronization age</span></span>  
  
1.  <span data-ttu-id="12b33-113">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="12b33-113">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="12b33-114">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12b33-114">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="12b33-115">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="12b33-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="12b33-116">默认值是\<驱动器 >: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="12b33-116">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="12b33-117">类型**ssoconfig-syncage\<以小时为单位的密码最长期限 >** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="12b33-117">Type **ssoconfig -syncage \<maximum password age in hours>** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12b33-118">SSOCONFIG 实用工具将 SQL Server 计算机上的时间用作其系统时间。</span><span class="sxs-lookup"><span data-stu-id="12b33-118">The SSOCONFIG utility uses the time on the SQL Server computer as its system time.</span></span> <span data-ttu-id="12b33-119">在使用与时间相关的任何命令时，请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="12b33-119">Remember this when using any commands related to time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b33-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12b33-120">See Also</span></span>  
 [<span data-ttu-id="12b33-121">密码同步</span><span class="sxs-lookup"><span data-stu-id="12b33-121">Password Synchronization</span></span>](../core/password-synchronization2.md)