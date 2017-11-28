---
title: "安装和配置管理 REST Api |Microsoft 文档"
description: "查询中使用 BizTalk Server 中的功能包的管理数据 REST Api 你 BizTalk 环境的项目"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c207b0aca5f2673e615167f75f7f1c7c3fb0e042
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="00e0b-103">安装和配置 BizTalk Server 中的管理 REST Api</span><span class="sxs-lookup"><span data-stu-id="00e0b-103">Install and configure the management REST APIs in BizTalk Server</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="00e0b-104">管理数据 Api 有哪些？</span><span class="sxs-lookup"><span data-stu-id="00e0b-104">What are management data APIs</span></span>
<span data-ttu-id="00e0b-105">管理数据 Api 是终结点，可以远程更新、 添加和查询中的不同项目的状态你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="00e0b-105">Management data APIs are endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="00e0b-106">终结点将添加使用 REST，并附带 swagger 定义。</span><span class="sxs-lookup"><span data-stu-id="00e0b-106">The endpoints are added using REST, and come with a swagger definition.</span></span> 

<span data-ttu-id="00e0b-107">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，没有安装这些 REST Api 和其 swagger 定义的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="00e0b-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="00e0b-108">这些 Api 进行 REST 调用来远程管理端口、 业务流程、 合作伙伴、 协议、 管道，和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="00e0b-108">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="00e0b-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="00e0b-109">Prerequisites</span></span>
* <span data-ttu-id="00e0b-110">安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00e0b-110">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="00e0b-111">在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00e0b-111">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="00e0b-112">在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。</span><span class="sxs-lookup"><span data-stu-id="00e0b-112">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="00e0b-113">请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="00e0b-113">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> <span data-ttu-id="00e0b-114">确认打开 BizTalk 服务器上安装 IIS **Internet Information Services Manager**。</span><span class="sxs-lookup"><span data-stu-id="00e0b-114">Confirm IIS is installed on the BizTalk Server by opening **Internet Information Services Manager**.</span></span> 

## <a name="step-1-install-the-rest-apis"></a><span data-ttu-id="00e0b-115">步骤 1： 安装 REST Api</span><span class="sxs-lookup"><span data-stu-id="00e0b-115">Step 1: Install the REST APIs</span></span>

1. <span data-ttu-id="00e0b-116">以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。</span><span class="sxs-lookup"><span data-stu-id="00e0b-116">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="00e0b-117">转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="00e0b-117">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="00e0b-118">在以下文本，将`Default Web Site`， `mgmtServiceAppPool`， `domain/user`， `password`，和`domain\group`用你的值：</span><span class="sxs-lookup"><span data-stu-id="00e0b-118">In the following text, replace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    <span data-ttu-id="00e0b-119">在以下示例中，我们使用`Default Web Site`，创建名为应用程序池`RESTAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，然后让 BizTalk Server Administrators 组权限。</span><span class="sxs-lookup"><span data-stu-id="00e0b-119">In the following example, we use the `Default Web Site`, create an application pool named `RESTAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the BizTalk Server Administrators group permissions.</span></span> <span data-ttu-id="00e0b-120">请务必输入以下、 包括单报价周围用带空格的值：</span><span class="sxs-lookup"><span data-stu-id="00e0b-120">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="00e0b-121">完成后， **BizTalkManagementService**在 IIS 内创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="00e0b-121">When complete, the **BizTalkManagementService** application is created within IIS:</span></span>  
    <span data-ttu-id="00e0b-122">![BizTalkManagementService 应用程序](../core/media/biztalkmanagementservice-apppool.png)</span><span class="sxs-lookup"><span data-stu-id="00e0b-122">![BizTalkManagementService application](../core/media/biztalkmanagementservice-apppool.png)</span></span>

4. <span data-ttu-id="00e0b-123">若要确认它是否工作，请浏览到`http://localhost/BizTalkManagementService/swagger`。</span><span class="sxs-lookup"><span data-stu-id="00e0b-123">To confirm it’s working, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span> <span data-ttu-id="00e0b-124">如果你提示登录，请使用是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="00e0b-124">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

> [!WARNING]
> <span data-ttu-id="00e0b-125">在 IIS 中的 BizTalkManagementService 应用程序使用 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="00e0b-125">The BizTalkManagementService application in IIS uses a web.config file.</span></span> <span data-ttu-id="00e0b-126">Web.config 中的元素**区分大小写**。</span><span class="sxs-lookup"><span data-stu-id="00e0b-126">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="00e0b-127">因此当你执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。</span><span class="sxs-lookup"><span data-stu-id="00e0b-127">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="00e0b-128">如果你不确定的这种情况，下面是找出的简单办法：</span><span class="sxs-lookup"><span data-stu-id="00e0b-128">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="00e0b-129">打开**计算机管理**，然后展开**本地用户和组**。</span><span class="sxs-lookup"><span data-stu-id="00e0b-129">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="00e0b-130">选择**组**，向下滚动到**SQLServer...**</span><span class="sxs-lookup"><span data-stu-id="00e0b-130">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="00e0b-131">组。</span><span class="sxs-lookup"><span data-stu-id="00e0b-131">groups.</span></span> 
> 3. <span data-ttu-id="00e0b-132">在下面的示例，请注意**BOOTCAMPBTS2016**处于全部大写。</span><span class="sxs-lookup"><span data-stu-id="00e0b-132">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="00e0b-133">如果看到全部大写，然后在全部大写中输入计算机名称。</span><span class="sxs-lookup"><span data-stu-id="00e0b-133">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![计算机名显示在全部大写](../core/media/groups-case.png)

<span data-ttu-id="00e0b-135">现在，通过 IIS 公开 REST Api，它们可以访问和执行其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="00e0b-135">Now that the REST APIs are exposed through IIS, they can be accessed and executed by other applications.</span></span> 

<span data-ttu-id="00e0b-136">你可以更改谁有权通过手动更新**web.config**文件，它是管理应用程序的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="00e0b-136">You can change who has access by manually updating the **web.config** file, which is in the root folder of the management application.</span></span> <span data-ttu-id="00e0b-137">例如，使用以下命令以允许任何人访问 swagger 输出：</span><span class="sxs-lookup"><span data-stu-id="00e0b-137">For example, use the following to allow anyone access to the swagger output:</span></span> 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a><span data-ttu-id="00e0b-138">步骤 2： 测试 Api</span><span class="sxs-lookup"><span data-stu-id="00e0b-138">Step 2: Test the APIs</span></span>

1. <span data-ttu-id="00e0b-139">在 BizTalk Server 中，浏览到`http://localhost/BizTalkManagementService/swagger`。</span><span class="sxs-lookup"><span data-stu-id="00e0b-139">On the BizTalk Server, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span>

2. <span data-ttu-id="00e0b-140">滚动到**主机**，然后选择**显示/隐藏**。</span><span class="sxs-lookup"><span data-stu-id="00e0b-140">Scroll to **Hosts**, and select **Show/Hide**.</span></span> <span data-ttu-id="00e0b-141">没有 GET 命令;单击此行：</span><span class="sxs-lookup"><span data-stu-id="00e0b-141">There is a GET command; click this row:</span></span>  
<span data-ttu-id="00e0b-142">![获取所有主机](../core/media/managment-rest-apis-hosts-get.png)</span><span class="sxs-lookup"><span data-stu-id="00e0b-142">![GET all hosts](../core/media/managment-rest-apis-hosts-get.png)</span></span>

3. <span data-ttu-id="00e0b-143">它显示的详细信息。</span><span class="sxs-lookup"><span data-stu-id="00e0b-143">It shows the details.</span></span> <span data-ttu-id="00e0b-144">选择**试试看**:</span><span class="sxs-lookup"><span data-stu-id="00e0b-144">Select **Try it out**:</span></span>  
<span data-ttu-id="00e0b-145">![进行试用](../core/media/managment-rest-apis-hosts-tryitout.png)</span><span class="sxs-lookup"><span data-stu-id="00e0b-145">![Try it out](../core/media/managment-rest-apis-hosts-tryitout.png)</span></span>

4. <span data-ttu-id="00e0b-146">响应正文将返回所有主机：</span><span class="sxs-lookup"><span data-stu-id="00e0b-146">The Response Body returns all the hosts:</span></span>  
![响应](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> <span data-ttu-id="00e0b-148">如果浏览到`http://localhost/BizTalkManagementService`，你应收到一个 500 错误。</span><span class="sxs-lookup"><span data-stu-id="00e0b-148">If you browse to `http://localhost/BizTalkManagementService`, you should get a 500 error.</span></span> <span data-ttu-id="00e0b-149">这是一件好事。</span><span class="sxs-lookup"><span data-stu-id="00e0b-149">That’s a good thing.</span></span> <span data-ttu-id="00e0b-150">只需添加`/swagger`到末尾的 URL，并且你将看到可用的 REST Api。</span><span class="sxs-lookup"><span data-stu-id="00e0b-150">Just add `/swagger` to the end of URL, and you’ll see the available REST APIs.</span></span> 


## <a name="see-also"></a><span data-ttu-id="00e0b-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00e0b-151">See also</span></span>
 [<span data-ttu-id="00e0b-152">配置功能包</span><span class="sxs-lookup"><span data-stu-id="00e0b-152">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)