---
title: 单一登录：Event 10511 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98371982-0db5-4ae0-9f92-f05a58e23b83
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531e32a2c23c30095dc744c6e73d111ce9cccc13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400244"
---
# <a name="single-sign-on-event-10511"></a><span data-ttu-id="58321-102">单一登录：事件 10511</span><span class="sxs-lookup"><span data-stu-id="58321-102">Single Sign-On: Event 10511</span></span>
## <a name="details"></a><span data-ttu-id="58321-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="58321-103">Details</span></span>  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="58321-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="58321-104">Product Name</span></span>   |                                                     <span data-ttu-id="58321-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="58321-105">Enterprise Single Sign-On</span></span>                                                     |
| <span data-ttu-id="58321-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="58321-106">Product Version</span></span> |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    <span data-ttu-id="58321-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="58321-107">Event ID</span></span>     |                                                               <span data-ttu-id="58321-108">10511</span><span class="sxs-lookup"><span data-stu-id="58321-108">10511</span></span>                                                               |
|  <span data-ttu-id="58321-109">事件源</span><span class="sxs-lookup"><span data-stu-id="58321-109">Event Source</span></span>   |                                                              <span data-ttu-id="58321-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="58321-110">ENTSSO</span></span>                                                               |
|    <span data-ttu-id="58321-111">组件</span><span class="sxs-lookup"><span data-stu-id="58321-111">Component</span></span>    |                                                                <span data-ttu-id="58321-112">N\A</span><span class="sxs-lookup"><span data-stu-id="58321-112">N\A</span></span>                                                                |
|  <span data-ttu-id="58321-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="58321-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="58321-114">SSO_ERROR_NO_DSN</span><span class="sxs-lookup"><span data-stu-id="58321-114">SSO_ERROR_NO_DSN</span></span>                                                          |
|  <span data-ttu-id="58321-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="58321-115">Message Text</span></span>   | <span data-ttu-id="58321-116">在注册表中找不到 SQL Server 和 SSO 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="58321-116">The SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="58321-117">使用 SSO 管理工具来配置这些值。</span><span class="sxs-lookup"><span data-stu-id="58321-117">Use the SSO administration tools to configure these values.</span></span> |

## <a name="explanation"></a><span data-ttu-id="58321-118">解释</span><span class="sxs-lookup"><span data-stu-id="58321-118">Explanation</span></span>  
 <span data-ttu-id="58321-119">此错误事件表示，在注册表中未找到 SQL Server 和 SSO 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="58321-119">This Error event indicates that the SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="58321-120">SSO 服务需要使用此信息，以便它可以连接到 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="58321-120">The SSO service requires this information so it can connect to the SSO database.</span></span> <span data-ttu-id="58321-121">在配置期间，如果在注册表中设置此信息。</span><span class="sxs-lookup"><span data-stu-id="58321-121">This information is set in the registry during configuration.</span></span> <span data-ttu-id="58321-122">这可能表示配置未正确完成，或注册表项已被删除后配置已完成。</span><span class="sxs-lookup"><span data-stu-id="58321-122">This may indicate that configuration did not complete correctly or that the registry entries have been deleted after configuration was completed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="58321-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="58321-123">User Action</span></span>  
 <span data-ttu-id="58321-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="58321-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="58321-125">如果您怀疑更广泛的配置失败，取消对该产品，然后重新配置使用配置程序。</span><span class="sxs-lookup"><span data-stu-id="58321-125">If you suspect a wider configuration failure, unconfigure the product and then reconfigure using the configuration program.</span></span>  

- <span data-ttu-id="58321-126">或者可以使用 SSO 命令行工具 ssoconfig.exe SSO 安装目录，通常 C:\Program Files\Common Files\Enterprise Single Sign-on 中设置这些特定的缺失注册表项。</span><span class="sxs-lookup"><span data-stu-id="58321-126">Alternatively these specific missing registry entries can be set using the SSO command line tool, ssoconfig.exe located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="58321-127">SSO 安装目录中可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="58321-127">Your SSO installation directory may be different.</span></span> <span data-ttu-id="58321-128">使用 **-setDB**选项设置的所需的 SQL Server 和 SSO 数据库名称。</span><span class="sxs-lookup"><span data-stu-id="58321-128">Use the **-setDB** option to set the required SQL Server and SSO database names.</span></span>  

  <span data-ttu-id="58321-129">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="58321-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="58321-130">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="58321-130">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
