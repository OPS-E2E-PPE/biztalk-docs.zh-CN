---
title: 如何为使用客户端实用工具的关联应用程序设置凭据 |Microsoft Docs
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
ms.openlocfilehash: abc8c329b46e5eab5f04f5082064f1dea63505bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334523"
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="6e757-102">如何为使用客户端实用工具的关联应用程序设置凭据</span><span class="sxs-lookup"><span data-stu-id="6e757-102">How to Set Credentials for the Affiliate Application Using the Client Utility</span></span>
<span data-ttu-id="6e757-103">使用此命令为用户设置凭据，以便用户能够访问特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e757-103">Use this command to set the credentials for a user so that the user is able to access a specific application.</span></span> <span data-ttu-id="6e757-104">此命令还会自动启用映射。</span><span class="sxs-lookup"><span data-stu-id="6e757-104">This command also automatically enables the mapping.</span></span>  
  
 <span data-ttu-id="6e757-105">此命令不显示密码，并在您键入。</span><span class="sxs-lookup"><span data-stu-id="6e757-105">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="6e757-106">如果用户映射已存在，此命令将设置为现有映射的凭据。</span><span class="sxs-lookup"><span data-stu-id="6e757-106">If the user mapping already exists, this command will set the credentials for that existing mapping.</span></span> <span data-ttu-id="6e757-107">如果尚未创建用户映射，SSO 系统将提示你提供应用程序的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="6e757-107">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="6e757-108">为关联应用程序使用客户端实用工具设置凭据</span><span class="sxs-lookup"><span data-stu-id="6e757-108">To set credentials for the affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="6e757-109">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="6e757-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="6e757-110">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="6e757-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6e757-111">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="6e757-111">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="6e757-112">类型**ssoclient – setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>** 是为其所需的特定应用程序若要设置的凭据。</span><span class="sxs-lookup"><span data-stu-id="6e757-112">Type **ssoclient –setcredentials \<application name\>**, where **\<application name\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e757-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="6e757-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="6e757-114">当系统提示输入用户凭据，请输入此应用程序的用户密码。</span><span class="sxs-lookup"><span data-stu-id="6e757-114">When prompted for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="6e757-115">如果尚未创建用户映射，SSO 系统将提示你提供应用程序的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="6e757-115">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e757-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e757-116">See Also</span></span>  
 <span data-ttu-id="6e757-117">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="6e757-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="6e757-118">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="6e757-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)