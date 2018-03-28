---
title: 如何列出关联应用程序的属性 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac15775-39d0-470e-b9d2-21b2d02e1de7
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: e35f1f068f63d4db9738733bcada55047e81a19a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="5b275-102">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="5b275-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="5b275-103">**Displayapp**命令显示有关关联应用程序的以下信息。</span><span class="sxs-lookup"><span data-stu-id="5b275-103">The **displayapp** command shows the following information about the affiliate application.</span></span> <span data-ttu-id="5b275-104">有关关联应用程序的属性的详细信息，请参阅[SSO Affiliate 应用程序](../esso/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="5b275-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../esso/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="5b275-105">单一登录 (SSO) 系统中获取此信息用于更新关联应用程序的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="5b275-105">The Single Sign-On (SSO) system obtains this information from the XML file that you used to update the affiliate application.</span></span> <span data-ttu-id="5b275-106">有关详细信息，请参阅[如何更新关联的应用程序的属性](../esso/how-to-update-the-properties-of-an-affiliate-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5b275-106">For more information, see [How to Update the Properties of an Affiliate Application](../esso/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="5b275-107">使用管理实用工具显示关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="5b275-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1.  <span data-ttu-id="5b275-108">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="5b275-108">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="5b275-109">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="5b275-109">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="5b275-110">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="5b275-110">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="5b275-111">类型`ssomanage –displayapp <application name>`，其中*\<应用程序名称 >*是你想要显示的属性的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="5b275-111">Type `ssomanage –displayapp <application name>`, where *\<application name>* is the name of the affiliate application that you want to display the properties for.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="5b275-112">使用客户端实用工具显示关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="5b275-112">To display the properties of an affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="5b275-113">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="5b275-113">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="5b275-114">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="5b275-114">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="5b275-115">默认安装目录是\<*安装驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="5b275-115">The default installation directory is \<*install drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="5b275-116">类型`ssoclient –displayapp <application name>`，其中*\<应用程序名称 >*是你想要显示的属性的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="5b275-116">Type `ssoclient –displayapp <application name>`, where *\<application name>* is the name of the affiliate application that you want to display the properties for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b275-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b275-117">See Also</span></span>  
 <span data-ttu-id="5b275-118">[管理用户映射](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="5b275-118">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="5b275-119">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="5b275-119">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)