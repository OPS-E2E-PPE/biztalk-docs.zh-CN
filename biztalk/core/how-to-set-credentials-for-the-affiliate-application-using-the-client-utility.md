---
title: 如何为使用客户端实用工具的关联应用程序设置凭据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebe3e1a9e8d2ea8df421d0bade60f35d6925459
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971563"
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="4b707-102">如何为使用客户端实用工具的关联应用程序设置凭据</span><span class="sxs-lookup"><span data-stu-id="4b707-102">How to Set Credentials for the Affiliate Application Using the Client Utility</span></span>
<span data-ttu-id="4b707-103">使用此命令可为用户设置凭据以便该用户能够访问特定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b707-103">Use this command to set the credentials for a user so that the user is able to access a specific application.</span></span> <span data-ttu-id="4b707-104">此命令还将自动启用映射。</span><span class="sxs-lookup"><span data-stu-id="4b707-104">This command also automatically enables the mapping.</span></span>  
  
 <span data-ttu-id="4b707-105">在键入密码时，此命令不显示该密码。</span><span class="sxs-lookup"><span data-stu-id="4b707-105">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="4b707-106">如果用户映射已存在，则此命令将设置该现有映射的凭据。</span><span class="sxs-lookup"><span data-stu-id="4b707-106">If the user mapping already exists, this command will set the credentials for that existing mapping.</span></span> <span data-ttu-id="4b707-107">如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="4b707-107">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="4b707-108">使用客户端实用工具设置关联应用程序的凭据</span><span class="sxs-lookup"><span data-stu-id="4b707-108">To set credentials for the affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="4b707-109">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="4b707-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="4b707-110">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="4b707-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="4b707-111">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="4b707-111">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="4b707-112">类型**ssoclient – setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>** 是为其所需的特定应用程序若要设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="4b707-112">Type **ssoclient –setcredentials \<application name\>**, where **\<application name\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b707-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4b707-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="4b707-114">当提示输入用户凭据时，请输入此应用程序的用户密码。</span><span class="sxs-lookup"><span data-stu-id="4b707-114">When prompted for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="4b707-115">如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="4b707-115">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b707-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b707-116">See Also</span></span>  
 <span data-ttu-id="4b707-117">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="4b707-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="4b707-118">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="4b707-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)