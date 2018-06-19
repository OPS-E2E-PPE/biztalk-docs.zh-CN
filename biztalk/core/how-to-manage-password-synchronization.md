---
title: 如何管理密码同步 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], managing
- managing [SSO], disabling features
- managing [SSO], enabling features
- Password Synchronization [SSO], SSOMANAGE command line utility
- SSO database, SSOMANAGE command line utility
- managing, Password Synchronization [SSO]
- SSO database, database settings
- SSOMANAGE command line utility
ms.assetid: 033e63f2-e5b0-4400-99c3-145679d9b84e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce76f2ca16cca44af1658983c49d11f6931e931
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972651"
---
# <a name="how-to-manage-password-synchronization"></a><span data-ttu-id="33dc8-102">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="33dc8-102">How to Manage Password Synchronization</span></span>
<span data-ttu-id="33dc8-103">使用 MMC 管理单元或 SSOMANAGE 命令行实用工具可以启用或禁用 SSO 功能，并显示当前 SSO 数据库设置。</span><span class="sxs-lookup"><span data-stu-id="33dc8-103">Use the MMC Snap-in or the SSOMANAGE command line utility to enable or disable SSO features, and to display current SSO database settings.</span></span>  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a><span data-ttu-id="33dc8-104">使用 MMC 管理单元管理功能或显示设置</span><span class="sxs-lookup"><span data-stu-id="33dc8-104">To manage features or display settings using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="33dc8-105">右键单击相应的功能或数据库。</span><span class="sxs-lookup"><span data-stu-id="33dc8-105">Right-click the appropriate feature or database.</span></span>  
  
2.  <span data-ttu-id="33dc8-106">单击相应的菜单项。</span><span class="sxs-lookup"><span data-stu-id="33dc8-106">Click the appropriate menu item.</span></span>  
  
### <a name="to-enable-sso-features-using-the-command-line"></a><span data-ttu-id="33dc8-107">使用命令行启用 SSO 功能</span><span class="sxs-lookup"><span data-stu-id="33dc8-107">To enable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="33dc8-108">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="33dc8-108">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="33dc8-109">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="33dc8-109">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="33dc8-110">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="33dc8-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="33dc8-111">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="33dc8-111">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="33dc8-112">类型**ssomanage-启用**，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="33dc8-112">Type **ssomanage -enable** and press Enter.</span></span>  
  
### <a name="to-disable-sso-features-using-the-command-line"></a><span data-ttu-id="33dc8-113">使用命令行禁用 SSO 功能</span><span class="sxs-lookup"><span data-stu-id="33dc8-113">To disable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="33dc8-114">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="33dc8-114">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="33dc8-115">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="33dc8-115">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="33dc8-116">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="33dc8-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="33dc8-117">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="33dc8-117">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="33dc8-118">类型**ssomanage-禁用**，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="33dc8-118">Type **ssomanage -disable** and press Enter.</span></span>  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a><span data-ttu-id="33dc8-119">使用命令行显示当前数据库设置</span><span class="sxs-lookup"><span data-stu-id="33dc8-119">To display current database settings using the command line</span></span>  
  
1.  <span data-ttu-id="33dc8-120">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="33dc8-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="33dc8-121">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="33dc8-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="33dc8-122">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="33dc8-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="33dc8-123">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="33dc8-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="33dc8-124">类型**ssomanage displaydb** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="33dc8-124">Type **ssomanage -displaydb** and press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33dc8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33dc8-125">See Also</span></span>  
 [<span data-ttu-id="33dc8-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="33dc8-126">Password Synchronization</span></span>](../core/password-synchronization2.md)