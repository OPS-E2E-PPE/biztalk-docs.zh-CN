---
title: "安装和配置管理 REST Api |Microsoft 文档"
description: "查询中使用 BizTalk Server 中的功能包 1 管理数据 REST Api 你 BizTalk 环境的项目的状态"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 009b3b0bb333b8f92f6235da57b0c3e9f5daca96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="b7ce6-103">安装和配置 BizTalk Server 中的管理 REST Api</span><span class="sxs-lookup"><span data-stu-id="b7ce6-103">Install and configure the management REST APIs in BizTalk Server</span></span>
<span data-ttu-id="b7ce6-104">使用 Windows PowerShell 脚本来启用远程管理的 REST Api 你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-104">Use a Windows PowerShell script to enable REST APIs that remotely manage your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="b7ce6-105">管理数据 Api 有哪些？</span><span class="sxs-lookup"><span data-stu-id="b7ce6-105">What are Management data APIs</span></span>
<span data-ttu-id="b7ce6-106">管理数据 Api 是终结点，可以远程更新、 添加和查询中的不同项目的状态你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-106">Management data APIs are the endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="b7ce6-107">终结点将添加使用 REST，并附带 Swagger 定义。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-107">The endpoints are added using REST, and come with a Swagger definition.</span></span> 

<span data-ttu-id="b7ce6-108">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，没有安装这些 REST Api 和其 swagger 定义的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="b7ce6-109">这些 Api 进行 REST 调用来远程管理端口、 业务流程、 合作伙伴、 协议、 管道，和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-109">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

<span data-ttu-id="b7ce6-110">本主题演示了如何安装 REST Api。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-110">This topic shows you how to install the REST APIs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b7ce6-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="b7ce6-111">Prerequisites</span></span>
* <span data-ttu-id="b7ce6-112">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ce6-112">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="b7ce6-113">在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-113">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b7ce6-114">在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-114">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="b7ce6-115">请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-115">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="enable-the-rest-apis"></a><span data-ttu-id="b7ce6-116">启用 REST Api</span><span class="sxs-lookup"><span data-stu-id="b7ce6-116">Enable the REST APIs</span></span>

1. <span data-ttu-id="b7ce6-117">以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-117">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="b7ce6-118">浏览到 BizTalk 文件夹下**Program Files (x86)/Microsoft BizTalk Server 2016**</span><span class="sxs-lookup"><span data-stu-id="b7ce6-118">Browse to the BizTalk folder under **Program Files (x86)/Microsoft BizTalk Server 2016**</span></span>
3. <span data-ttu-id="b7ce6-119">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-119">Run the following command.</span></span> <span data-ttu-id="b7ce6-120">请务必更新你`website`， `domain/user`， `password`，和`domain\group`用你的值：</span><span class="sxs-lookup"><span data-stu-id="b7ce6-120">Be sure to update your `website`, `domain/user`, `password`, and `domain\group` with your values:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```
4. <span data-ttu-id="b7ce6-121">运行该脚本后，浏览新 IIS 应用程序：</span><span class="sxs-lookup"><span data-stu-id="b7ce6-121">After you run the script, browse the new IIS application:</span></span>  
    1. <span data-ttu-id="b7ce6-122">打开 web 浏览器</span><span class="sxs-lookup"><span data-stu-id="b7ce6-122">Open your web browser</span></span>
    2. <span data-ttu-id="b7ce6-123">浏览到**http://localhost/OperationalDataService/swagger**</span><span class="sxs-lookup"><span data-stu-id="b7ce6-123">Browse to **http://localhost/OperationalDataService/swagger**</span></span>

5. <span data-ttu-id="b7ce6-124">Swagger 定义加载。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-124">The Swagger definitions loads.</span></span> <span data-ttu-id="b7ce6-125">你还可以更改谁有权通过更新**web.config**管理应用程序的根文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-125">You can also change who has access by updating the **web.config** file in the root folder of the Management Application.</span></span>

<span data-ttu-id="b7ce6-126">REST Api 公开，通过该计算机，和可以访问和执行其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7ce6-126">The REST APIs are exposed through the machine, and can be accessed and executed by other applications.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b7ce6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7ce6-127">See also</span></span>
 [<span data-ttu-id="b7ce6-128">配置功能包</span><span class="sxs-lookup"><span data-stu-id="b7ce6-128">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)