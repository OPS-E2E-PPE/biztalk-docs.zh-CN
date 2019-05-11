---
title: 标准 SSO 安装选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, installing
ms.assetid: 59aeb503-f369-4145-8a3c-ab60e9ed31a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cbba3615048b8028f5daebcadd8a649afb0f16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392995"
---
# <a name="standard-sso-installation-options"></a><span data-ttu-id="5fb97-102">标准 SSO 安装选项</span><span class="sxs-lookup"><span data-stu-id="5fb97-102">Standard SSO Installation Options</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5fb97-103">利用安全地存储凭据的企业单一登录 (SSO) 功能，以启用单一登录方案。</span><span class="sxs-lookup"><span data-stu-id="5fb97-103">leverages the Enterprise Single Sign-On (SSO) capabilities for securely storing credentials to enable single sign-on scenarios.</span></span>  
  
 <span data-ttu-id="5fb97-104">BizTalk Server 还使用 SSO 来安全地存储适配器的自定义配置数据。</span><span class="sxs-lookup"><span data-stu-id="5fb97-104">BizTalk Server also uses SSO to store custom configuration data of Adapters securely.</span></span> <span data-ttu-id="5fb97-105">若要执行此操作，BizTalk Server 运行时和管理功能安装为依存功能的 SSO。</span><span class="sxs-lookup"><span data-stu-id="5fb97-105">To do this, BizTalk Server runtime and administration features install SSO as a dependent feature.</span></span> <span data-ttu-id="5fb97-106">BizTalk Server 的默认安装时会安装企业 SSO。</span><span class="sxs-lookup"><span data-stu-id="5fb97-106">The default installation of BizTalk Server installs Enterprise SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fb97-107">安装企业单一登录 （服务器组件） 时，需要进行配置。</span><span class="sxs-lookup"><span data-stu-id="5fb97-107">When Enterprise Single Sign-on (Server component) is installed, configuration needs to be performed.</span></span> <span data-ttu-id="5fb97-108">若要设置 SSO 系统的第一步是配置主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="5fb97-108">The first step to set up an SSO System is to configure the master secret server.</span></span> <span data-ttu-id="5fb97-109">建议设置独立的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="5fb97-109">It is recommended to set up a stand-alone master secret server.</span></span> <span data-ttu-id="5fb97-110">这可以通过仅从 BizTalk Server 安装程序中的自定义功能树选择企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="5fb97-110">This can be done by only selecting Enterprise Single Sign-on from the custom feature tree in BizTalk Server setup.</span></span>  
>   
>  <span data-ttu-id="5fb97-111">我们还建议的任何计算机运行企业单一登录已运行的时间同步服务。</span><span class="sxs-lookup"><span data-stu-id="5fb97-111">We also recommend that any computer running Enterprise Single Sign-On have a time synchronization service running.</span></span> <span data-ttu-id="5fb97-112">这会使计算机时间与系统，这是对于 SSO 票证服务才能正常运行所必需的其余部分保持同步。</span><span class="sxs-lookup"><span data-stu-id="5fb97-112">This keeps the computer time in sync with the rest of the system, which is necessary for SSO ticketing services to function properly.</span></span>  
  
 <span data-ttu-id="5fb97-113">**安装选项的列表**:运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="5fb97-113">**List of installation options**: Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup program.</span></span> <span data-ttu-id="5fb97-114">选择**自定义安装**，然后从以下列表中选择相应的选项：</span><span class="sxs-lookup"><span data-stu-id="5fb97-114">Select **Custom Installation**, and then select the appropriate option from the following list:</span></span>  
  
- <span data-ttu-id="5fb97-115">**企业单一登录管理 ―** 映射并连接到企业单一登录服务用于管理和客户端工具。</span><span class="sxs-lookup"><span data-stu-id="5fb97-115">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
- <span data-ttu-id="5fb97-116">**企业单一登录主密钥服务器 ―** 充当 SSO 系统中的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="5fb97-116">**Enterprise Single Sign-On Master Secret Server ―** Acts as the Master Secret Server in the SSO System.</span></span> <span data-ttu-id="5fb97-117">这是需要部署在 SSO 系统中的第一个服务器，这使您可以创建 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="5fb97-117">This is the first server in the SSO System that needs to deployed and this allows you to create the SSO database.</span></span>  
  
  <span data-ttu-id="5fb97-118">此外可以使用添加或删除程序实用程序来添加安装完成后，以下：</span><span class="sxs-lookup"><span data-stu-id="5fb97-118">You can also add the following after setup, by using the Add or Remove Programs utility:</span></span>  
  
- <span data-ttu-id="5fb97-119">**服务器运行时 ―** 核心服务，以启用单一登录，并安全地存储/访问配置数据。</span><span class="sxs-lookup"><span data-stu-id="5fb97-119">**Server Runtime ―** Core services to enable single sign-on and to store/access configuration data securely.</span></span>  
  
- <span data-ttu-id="5fb97-120">**企业单一登录管理 ―** 映射并连接到企业单一登录服务用于管理和客户端工具。</span><span class="sxs-lookup"><span data-stu-id="5fb97-120">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
- <span data-ttu-id="5fb97-121">**企业单一登录服务与密码同步 ―** 服务以启用企业 SSO 系统中的密码同步功能。</span><span class="sxs-lookup"><span data-stu-id="5fb97-121">**Enterprise Single Sign-On Services with Password Synchronization ―** Services to enable the Password Synchronization feature in the Enterprise SSO System.</span></span> <span data-ttu-id="5fb97-122">这些服务还与 Microsoft 密码更改通知服务集成。</span><span class="sxs-lookup"><span data-stu-id="5fb97-122">These services also integrate with the Microsoft Password Change Notification Service.</span></span> <span data-ttu-id="5fb97-123">一旦您已安装的核心企业单一登录服务，你可以安装企业 SSO 密码同步功能从 BizTalk Server 包启动 \Platform\SSO\Setup.exe，然后选择密码同步功能。</span><span class="sxs-lookup"><span data-stu-id="5fb97-123">Once you have installed the core Enterprise Single Sign-On services, you can install the Password Synchronization feature of Enterprise SSO from the BizTalk Server package by launching the \Platform\SSO\Setup.exe and selecting the Password Synchronization feature.</span></span>  
  
- <span data-ttu-id="5fb97-124">**软件开发工具包**编程和参考信息。</span><span class="sxs-lookup"><span data-stu-id="5fb97-124">**Software Development Kit** Programming and Reference information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fb97-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="5fb97-125">In This Section</span></span>  
  
-   [<span data-ttu-id="5fb97-126">如何安装 SSO 管理组件</span><span class="sxs-lookup"><span data-stu-id="5fb97-126">How to Install the SSO Administration Component</span></span>](../core/how-to-install-the-sso-administration-component.md)  
  
-   [<span data-ttu-id="5fb97-127">如何安装 SSO 客户端实用工具</span><span class="sxs-lookup"><span data-stu-id="5fb97-127">How to Install the SSO Client Utility</span></span>](../core/how-to-install-the-sso-client-utility.md)