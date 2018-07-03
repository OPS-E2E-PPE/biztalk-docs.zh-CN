---
title: 如何设置 SSO 服务器使用客户端实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f212bb5e6601274a473c6f9854d5e23af9715cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008862"
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a><span data-ttu-id="efe04-102">如何设置 SSO 服务器使用客户端实用工具</span><span class="sxs-lookup"><span data-stu-id="efe04-102">How to Set the SSO Server Using the Client Utility</span></span>
<span data-ttu-id="efe04-103">每次使用 ssoclient，您必须首先将用户指引到正确实现单一登录的服务器包含它们的配置信息。</span><span class="sxs-lookup"><span data-stu-id="efe04-103">Each time you use ssoclient, you must first point the user to the correct Single Sign-On server that contains their configuration information.</span></span>  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a><span data-ttu-id="efe04-104">若要为用户使用客户端实用工具设置 SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="efe04-104">To set the SSO Server for a user using the client utility</span></span>  
  
1. <span data-ttu-id="efe04-105">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="efe04-105">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="efe04-106">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="efe04-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="efe04-107">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="efe04-107">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="efe04-108">类型<strong>ssoclient – 服务器*\<单一登录服务器\></strong><em>，其中\<</em>单一登录服务器\>* 是要连接到单一登录服务器用户的名称。</span><span class="sxs-lookup"><span data-stu-id="efe04-108">Type <strong>ssoclient –server *\<Single Sign-On Server\></strong><em>, where \<</em>Single Sign-On Server\>* is the name of the Single Sign-On server the user wants to connect to.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="efe04-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="efe04-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe04-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="efe04-110">See Also</span></span>  
 <span data-ttu-id="efe04-111">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="efe04-111">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="efe04-112">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="efe04-112">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)