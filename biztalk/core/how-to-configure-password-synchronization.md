---
title: 如何配置密码同步 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1b18d6f59b364a12a9ffe775d64a57e310f76e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341303"
---
# <a name="how-to-configure-password-synchronization"></a><span data-ttu-id="98cfa-102">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="98cfa-102">How to Configure Password Synchronization</span></span>
<span data-ttu-id="98cfa-103">使用 SSOCONFIG 命令行实用工具来配置密码同步设置。</span><span class="sxs-lookup"><span data-stu-id="98cfa-103">Use the SSOCONFIG command line utility to configure your password synchronization settings.</span></span>  
  
### <a name="to-specify-the-directory-for-replay-files"></a><span data-ttu-id="98cfa-104">若要指定为重播文件目录</span><span class="sxs-lookup"><span data-stu-id="98cfa-104">To specify the directory for replay files</span></span>  
  
1.  <span data-ttu-id="98cfa-105">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="98cfa-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="98cfa-106">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98cfa-106">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="98cfa-107">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="98cfa-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="98cfa-108">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="98cfa-108">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="98cfa-109">类型**ssoconfig-replayfiles\<重播文件目录\>&#124;的默认**并按 Enter。</span><span class="sxs-lookup"><span data-stu-id="98cfa-109">Type **ssoconfig -replayfiles \<replay files directory\> &#124; -default** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98cfa-110">当您更改服务帐户时，不会删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="98cfa-110">Replay files are not deleted when you change the service account.</span></span> <span data-ttu-id="98cfa-111">如果更改此帐户，你将需要手动删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="98cfa-111">If you change this account, you will need to delete the replay files manually.</span></span>  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a><span data-ttu-id="98cfa-112">若要显示或更改最长密码同步期限</span><span class="sxs-lookup"><span data-stu-id="98cfa-112">To display or change maximum password synchronization age</span></span>  
  
1.  <span data-ttu-id="98cfa-113">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="98cfa-113">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="98cfa-114">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98cfa-114">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="98cfa-115">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="98cfa-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="98cfa-116">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="98cfa-116">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="98cfa-117">类型**ssoconfig-syncage\<以小时为单位的最长密码期限\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="98cfa-117">Type **ssoconfig -syncage \<maximum password age in hours\>** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98cfa-118">SSOCONFIG 实用工具在 SQL Server 计算机上使用的时间用作其系统时间。</span><span class="sxs-lookup"><span data-stu-id="98cfa-118">The SSOCONFIG utility uses the time on the SQL Server computer as its system time.</span></span> <span data-ttu-id="98cfa-119">使用与时间相关的任何命令时请记住这一点。</span><span class="sxs-lookup"><span data-stu-id="98cfa-119">Remember this when using any commands related to time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98cfa-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="98cfa-120">See Also</span></span>  
 [<span data-ttu-id="98cfa-121">密码同步</span><span class="sxs-lookup"><span data-stu-id="98cfa-121">Password Synchronization</span></span>](../core/password-synchronization2.md)