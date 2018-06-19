---
title: 从以前版本的 SSO 升级 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf36c33b9480c0e8658089fdc9d996b3701d7660
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286965"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a><span data-ttu-id="fe6d8-102">升级从早期版本的 SSO</span><span class="sxs-lookup"><span data-stu-id="fe6d8-102">Upgrading from a Previous Version of SSO</span></span>
<span data-ttu-id="fe6d8-103">如果您要安装企业单一登录功能，并且计算机中已部署了一个早期版本（例如，Microsoft BizTalk Server 2009），则必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fe6d8-103">If you are installing the Enterprise Single Sign-on feature and you already have a previous version deployed on your computer (for example, from Microsoft BizTalk Server 2009), you must complete the steps below.</span></span>  
  
1.  <span data-ttu-id="fe6d8-104">将 SSO 数据库备份到安全的位置</span><span class="sxs-lookup"><span data-stu-id="fe6d8-104">Back up the SSO database to a secure location</span></span>  
  
2.  <span data-ttu-id="fe6d8-105">备份主密钥服务器中的主密钥</span><span class="sxs-lookup"><span data-stu-id="fe6d8-105">Back up the master secret key on the master secret server</span></span>  
  
3.  <span data-ttu-id="fe6d8-106">通过运行更新主密钥服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装过程中，选择**自定义安装**，然后选择**企业单一登录**。</span><span class="sxs-lookup"><span data-stu-id="fe6d8-106">Update the master secret server by running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, choosing **Custom Installation**, and then selecting **Enterprise Single Sign-On**.</span></span>  
  
4.  <span data-ttu-id="fe6d8-107">选择后**启用企业单一登录此计算机上**，选择**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="fe6d8-107">After selecting **Enable Enterprise Single Sign-on on this computer**, select **Join an existing SSO system**.</span></span>  
  
 <span data-ttu-id="fe6d8-108">不需要从更新其他 SSO 服务器 （非主机密服务器） 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="fe6d8-108">It is not necessary to update the other SSO servers (non-master secret servers) from your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="fe6d8-109">但是，如果希望在这些服务器上使用新的企业单一登录功能，则必须通过使用与上述过程相同的过程来更新这些服务器。</span><span class="sxs-lookup"><span data-stu-id="fe6d8-109">However, if you want the new Enterprise Single Sign-On features to be available on those servers, you must update them by using the same procedure outlined above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe6d8-110">这些注意事项也适用如果正在安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要更新的服务器在与主机集成 Server 2009 Enterprise Single Sign-On 和你的现有安装的计算机上。</span><span class="sxs-lookup"><span data-stu-id="fe6d8-110">These considerations also apply if you are installing Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer with an existing installation of Host Integration Server 2009 Enterprise Single Sign-On, and you want to update the servers.</span></span>  
  
 <span data-ttu-id="fe6d8-111">如果在已安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上安装 Host Integration Server，则不要选择企业单一登录功能。</span><span class="sxs-lookup"><span data-stu-id="fe6d8-111">If you are installing Host Integration Server on a computer where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is already installed, do not select the Enterprise Single Sign-On feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe6d8-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="fe6d8-112">In This Section</span></span>  
  
-   [<span data-ttu-id="fe6d8-113">使用主机启动的 SSO 功能</span><span class="sxs-lookup"><span data-stu-id="fe6d8-113">Using Host Initiated SSO Functionality</span></span>](../core/using-host-initiated-sso-functionality.md)  
  
-   [<span data-ttu-id="fe6d8-114">SSO 的处理服务器</span><span class="sxs-lookup"><span data-stu-id="fe6d8-114">Processing Servers for SSO</span></span>](../core/processing-servers-for-sso.md)