---
title: 从早期版本的 SSO 升级 |Microsoft Docs
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
ms.openlocfilehash: bb758aea5910f14ff345ecd8408e52218cc6860c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398574"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a><span data-ttu-id="b89de-102">从早期版本的 SSO 升级</span><span class="sxs-lookup"><span data-stu-id="b89de-102">Upgrading from a Previous Version of SSO</span></span>
<span data-ttu-id="b89de-103">如果在安装企业单一登录功能，并且已有以前的版本 （例如，从 Microsoft BizTalk Server 2009) 在计算机上部署，则必须完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b89de-103">If you are installing the Enterprise Single Sign-on feature and you already have a previous version deployed on your computer (for example, from Microsoft BizTalk Server 2009), you must complete the steps below.</span></span>  
  
1. <span data-ttu-id="b89de-104">SSO 数据库备份到安全的位置</span><span class="sxs-lookup"><span data-stu-id="b89de-104">Back up the SSO database to a secure location</span></span>  
  
2. <span data-ttu-id="b89de-105">在主服务器上备份主密钥</span><span class="sxs-lookup"><span data-stu-id="b89de-105">Back up the master secret key on the master secret server</span></span>  
  
3. <span data-ttu-id="b89de-106">通过运行更新主密钥服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，选择**自定义安装**，然后选择**企业单一登录**。</span><span class="sxs-lookup"><span data-stu-id="b89de-106">Update the master secret server by running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, choosing **Custom Installation**, and then selecting **Enterprise Single Sign-On**.</span></span>  
  
4. <span data-ttu-id="b89de-107">选择后**在此计算机上启用企业单一登录**，选择**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="b89de-107">After selecting **Enable Enterprise Single Sign-on on this computer**, select **Join an existing SSO system**.</span></span>  
  
   <span data-ttu-id="b89de-108">不需要更新与其他 SSO 服务器 （非主密钥服务器） 从您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="b89de-108">It is not necessary to update the other SSO servers (non-master secret servers) from your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="b89de-109">但是，如果所需的新企业单一登录功能在这些服务器上可用，则必须更新它们通过使用上面所述的相同过程。</span><span class="sxs-lookup"><span data-stu-id="b89de-109">However, if you want the new Enterprise Single Sign-On features to be available on those servers, you must update them by using the same procedure outlined above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b89de-110">这些注意事项也适用如果您正在安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要更新的服务器与主机集成 Server 2009 Enterprise Single Sign-On 和你的现有安装的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b89de-110">These considerations also apply if you are installing Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer with an existing installation of Host Integration Server 2009 Enterprise Single Sign-On, and you want to update the servers.</span></span>  
  
 <span data-ttu-id="b89de-111">如果要在计算机上安装 Host Integration Server 其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是已安装，不要选择企业单一登录功能。</span><span class="sxs-lookup"><span data-stu-id="b89de-111">If you are installing Host Integration Server on a computer where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is already installed, do not select the Enterprise Single Sign-On feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b89de-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b89de-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b89de-113">使用主机启动的 SSO 功能</span><span class="sxs-lookup"><span data-stu-id="b89de-113">Using Host Initiated SSO Functionality</span></span>](../core/using-host-initiated-sso-functionality.md)  
  
-   [<span data-ttu-id="b89de-114">用于 SSO 的处理服务器</span><span class="sxs-lookup"><span data-stu-id="b89de-114">Processing Servers for SSO</span></span>](../core/processing-servers-for-sso.md)