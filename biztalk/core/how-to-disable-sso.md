---
title: 如何禁用 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7096a9c77dda72bbf0aea3ec76423c759fa90df
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968851"
---
# <a name="how-to-disable-sso"></a><span data-ttu-id="3ea46-102">如何禁用 SSO</span><span class="sxs-lookup"><span data-stu-id="3ea46-102">How to Disable SSO</span></span>
<span data-ttu-id="3ea46-103">通过使用 MMC 管理单元或命令行，可以禁用整个单一登录系统。</span><span class="sxs-lookup"><span data-stu-id="3ea46-103">You can disable the entire Single Sign-On system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="3ea46-104">禁用所有单一登录服务器将有短时间的延迟，因为它们会轮询 SSO 数据库以获取最新的全局信息。</span><span class="sxs-lookup"><span data-stu-id="3ea46-104">There will be a short delay for all Single Sign-On Servers to be disabled, as they poll the SSO database for the latest global information.</span></span>  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a><span data-ttu-id="3ea46-105">使用 MMC 管理单元禁用企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3ea46-105">To disable Enterprise Single Sign-On using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="3ea46-106">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="3ea46-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="3ea46-107">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="3ea46-107">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="3ea46-108">右键单击**系统**，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="3ea46-108">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a><span data-ttu-id="3ea46-109">使用命令行禁用企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3ea46-109">To disable Enterprise Single Sign-On using the command line</span></span>  
  
1.  <span data-ttu-id="3ea46-110">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="3ea46-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="3ea46-111">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="3ea46-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3ea46-112">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="3ea46-112">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="3ea46-113">类型**ssomanage-disablesso**。</span><span class="sxs-lookup"><span data-stu-id="3ea46-113">Type **ssomanage –disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3ea46-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="3ea46-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea46-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ea46-115">See Also</span></span>  
 <span data-ttu-id="3ea46-116">[如何启用 SSO](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="3ea46-116">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 [<span data-ttu-id="3ea46-117">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="3ea46-117">Using SSO</span></span>](../core/using-sso.md)