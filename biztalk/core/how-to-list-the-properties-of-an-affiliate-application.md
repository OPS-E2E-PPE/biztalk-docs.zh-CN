---
title: "如何列出关联应用程序的属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], listing properties
- managing [SSO applications], listing properties
ms.assetid: a120acd7-2f0b-4c72-8a8a-f8e500a773c8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 651c629a0290fef9af20dce3771d87dbb9eeb82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="aee63-102">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="aee63-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="aee63-103">此命令显示有关关联应用程序的以下信息。</span><span class="sxs-lookup"><span data-stu-id="aee63-103">This command shows the following information about the affiliate application.</span></span> <span data-ttu-id="aee63-104">有关关联应用程序的属性的详细信息，请参阅[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="aee63-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="aee63-105">SSO 系统从用于更新关联应用程序的 xml 文件获取这些信息。</span><span class="sxs-lookup"><span data-stu-id="aee63-105">The SSO system obtains this information from the xml file that you used to update the affiliate application.</span></span> <span data-ttu-id="aee63-106">有关详细信息，请参阅[如何更新关联的应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)。</span><span class="sxs-lookup"><span data-stu-id="aee63-106">For more information, see [How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="aee63-107">使用管理实用工具显示关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="aee63-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1.  <span data-ttu-id="aee63-108">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="aee63-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="aee63-109">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="aee63-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aee63-110">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="aee63-110">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="aee63-111">类型**ssomanage-displayapp *\<应用程序名称 >***，其中*\<应用程序名称 >*是 Affiliate 应用程序的名称你想要显示的属性。</span><span class="sxs-lookup"><span data-stu-id="aee63-111">Type **ssomanage –displayapp *\<application name>***, where *\<application name>* is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aee63-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="aee63-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="aee63-113">使用客户端实用工具显示关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="aee63-113">To display the properties of an affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="aee63-114">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="aee63-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="aee63-115">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="aee63-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aee63-116">默认安装目录是\<*安装驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="aee63-116">The default installation directory is \<*install drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="aee63-117">类型**ssoclient – displayapp *\<应用程序名称 >***，其中*\<应用程序名称 >*是 Affiliate 应用程序的名称你想要显示的属性。</span><span class="sxs-lookup"><span data-stu-id="aee63-117">Type **ssoclient –displayapp *\<application name>***, where *\<application name>* is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aee63-118">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="aee63-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee63-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aee63-119">See Also</span></span>  
 <span data-ttu-id="aee63-120">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="aee63-120">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="aee63-121">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="aee63-121">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)