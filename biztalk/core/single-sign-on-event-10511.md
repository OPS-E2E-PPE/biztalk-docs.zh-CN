---
title: 单一登录： 事件 10511 |Microsoft Docs
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
ms.openlocfilehash: 828dab394e773f99b31ca23f19b2816ab8558a10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992086"
---
# <a name="single-sign-on-event-10511"></a><span data-ttu-id="72f22-102">单一登录： 事件 10511</span><span class="sxs-lookup"><span data-stu-id="72f22-102">Single Sign-On: Event 10511</span></span>
## <a name="details"></a><span data-ttu-id="72f22-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="72f22-103">Details</span></span>  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="72f22-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="72f22-104">Product Name</span></span>   |                                                     <span data-ttu-id="72f22-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="72f22-105">Enterprise Single Sign-On</span></span>                                                     |
| <span data-ttu-id="72f22-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="72f22-106">Product Version</span></span> |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    <span data-ttu-id="72f22-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="72f22-107">Event ID</span></span>     |                                                               <span data-ttu-id="72f22-108">10511</span><span class="sxs-lookup"><span data-stu-id="72f22-108">10511</span></span>                                                               |
|  <span data-ttu-id="72f22-109">事件源</span><span class="sxs-lookup"><span data-stu-id="72f22-109">Event Source</span></span>   |                                                              <span data-ttu-id="72f22-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="72f22-110">ENTSSO</span></span>                                                               |
|    <span data-ttu-id="72f22-111">组件</span><span class="sxs-lookup"><span data-stu-id="72f22-111">Component</span></span>    |                                                                <span data-ttu-id="72f22-112">N\A</span><span class="sxs-lookup"><span data-stu-id="72f22-112">N\A</span></span>                                                                |
|  <span data-ttu-id="72f22-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="72f22-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="72f22-114">SSO_ERROR_NO_DSN</span><span class="sxs-lookup"><span data-stu-id="72f22-114">SSO_ERROR_NO_DSN</span></span>                                                          |
|  <span data-ttu-id="72f22-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="72f22-115">Message Text</span></span>   | <span data-ttu-id="72f22-116">注册表中找不到 SQL Server 和 SSO 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="72f22-116">The SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="72f22-117">使用 SSO 管理工具来配置这些值。</span><span class="sxs-lookup"><span data-stu-id="72f22-117">Use the SSO administration tools to configure these values.</span></span> |

## <a name="explanation"></a><span data-ttu-id="72f22-118">解释</span><span class="sxs-lookup"><span data-stu-id="72f22-118">Explanation</span></span>  
 <span data-ttu-id="72f22-119">此错误事件表明注册表中找不到 SQL Server 和 SSO 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="72f22-119">This Error event indicates that the SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="72f22-120">该 SSO 服务需要使用此信息才能连接到 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="72f22-120">The SSO service requires this information so it can connect to the SSO database.</span></span> <span data-ttu-id="72f22-121">此信息在配置过程中在注册表中设置。</span><span class="sxs-lookup"><span data-stu-id="72f22-121">This information is set in the registry during configuration.</span></span> <span data-ttu-id="72f22-122">这可能指示配置未正确完成，或者配置完成后这些注册表项已删除。</span><span class="sxs-lookup"><span data-stu-id="72f22-122">This may indicate that configuration did not complete correctly or that the registry entries have been deleted after configuration was completed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="72f22-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="72f22-123">User Action</span></span>  
 <span data-ttu-id="72f22-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="72f22-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="72f22-125">如果您担心发生更大范围的配置故障，请对该产品取消配置，然后使用配置程序重新配置。</span><span class="sxs-lookup"><span data-stu-id="72f22-125">If you suspect a wider configuration failure, unconfigure the product and then reconfigure using the configuration program.</span></span>  

- <span data-ttu-id="72f22-126">也可以使用 SSO 安装目录（通常为 C:\Program Files\Common Files\Enterprise Single Sign-On）中的 SSO 命令行工具 ssoconfig.exe 来设置这些具体的缺失注册表项。</span><span class="sxs-lookup"><span data-stu-id="72f22-126">Alternatively these specific missing registry entries can be set using the SSO command line tool, ssoconfig.exe located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="72f22-127">您的 SSO 安装目录可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="72f22-127">Your SSO installation directory may be different.</span></span> <span data-ttu-id="72f22-128">使用 **-setDB**选项设置的所需的 SQL Server 和 SSO 数据库名称。</span><span class="sxs-lookup"><span data-stu-id="72f22-128">Use the **-setDB** option to set the required SQL Server and SSO database names.</span></span>  

  <span data-ttu-id="72f22-129">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="72f22-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="72f22-130">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="72f22-130">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
