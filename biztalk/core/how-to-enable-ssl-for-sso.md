---
title: "如何启用 SSO 的 SSL |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae2f3840cd2620f9c03a5b207b32d8bbd4feee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-ssl-for-sso"></a><span data-ttu-id="f9d49-102">如何启用 SSO 的 SSL</span><span class="sxs-lookup"><span data-stu-id="f9d49-102">How to Enable SSL for SSO</span></span>
<span data-ttu-id="f9d49-103">使用此命令可以在所有企业单一登录 (SSO) 服务器与 SSO 数据库间启用安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="f9d49-103">Use this command to enable Secure Sockets Layer (SSL) between all the Enterprise Single Sign-On (SSO) servers and the SSO database.</span></span>  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a><span data-ttu-id="f9d49-104">为企业单一登录启用 SSL</span><span class="sxs-lookup"><span data-stu-id="f9d49-104">To enable SSL for Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="f9d49-105">依次单击 **“开始”**和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="f9d49-105">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="f9d49-106">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="f9d49-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="f9d49-107">默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="f9d49-107">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="f9d49-108">类型**ssoconfig-setSSL\<是/否 >**，其中\<**是/否**> 该值指示是否要启用 SSO 系统中的 SSL。</span><span class="sxs-lookup"><span data-stu-id="f9d49-108">Type **ssoconfig –setSSL \<yes/no>**, where \<**yes/no**> indicates whether you want to enable SSL in the SSO system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9d49-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="f9d49-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d49-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9d49-110">See Also</span></span>  
 [<span data-ttu-id="f9d49-111">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="f9d49-111">Using SSO</span></span>](../core/using-sso.md)