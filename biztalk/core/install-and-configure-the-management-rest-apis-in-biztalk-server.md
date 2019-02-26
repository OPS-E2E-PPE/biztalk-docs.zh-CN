---
title: 安装和配置管理 REST Api |Microsoft Docs
description: 查询在 BizTalk Server 功能包中使用管理数据 REST Api 在 BizTalk 环境中的项目
ms.custom: fp1
ms.date: 02/25/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 680b7390462a7a64d3064f621b2011952ba2551c
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56828562"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="f3be0-103">安装和配置 BizTalk Server 中的管理 REST Api</span><span class="sxs-lookup"><span data-stu-id="f3be0-103">Install and configure the management REST APIs in BizTalk Server</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="f3be0-104">管理数据的 Api 有哪些？</span><span class="sxs-lookup"><span data-stu-id="f3be0-104">What are management data APIs</span></span>
<span data-ttu-id="f3be0-105">管理数据的 Api 是允许您远程更新、 添加和查询中的不同产物的状态的终结点在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="f3be0-105">Management data APIs are endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="f3be0-106">终结点将添加使用 REST，并附带 swagger 定义。</span><span class="sxs-lookup"><span data-stu-id="f3be0-106">The endpoints are added using REST, and come with a swagger definition.</span></span> 

<span data-ttu-id="f3be0-107">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，没有安装这些 REST Api 和它们的 swagger 定义的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f3be0-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="f3be0-108">这些 Api 进行 REST 调用来远程管理端口、 业务流程、 合作伙伴、 协议、 管道和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3be0-108">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

<span data-ttu-id="f3be0-109">若要查看可用的 Api，以及你可以操作，请参阅[功能包 REST API 参考](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)。</span><span class="sxs-lookup"><span data-stu-id="f3be0-109">To see the available APIs, and what you can do, see [Feature Pack REST API reference](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f3be0-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="f3be0-110">Prerequisites</span></span>
* <span data-ttu-id="f3be0-111">安装[功能包 2](https://aka.ms/bts2016fp2)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3be0-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="f3be0-112">上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f3be0-112">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f3be0-113">确认 IIS 已安装 BizTalk Server 上，通过打开**Internet Information Services Manager**。</span><span class="sxs-lookup"><span data-stu-id="f3be0-113">Confirm IIS is installed on the BizTalk Server by opening **Internet Information Services Manager**.</span></span> 

  <span data-ttu-id="f3be0-114">在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。</span><span class="sxs-lookup"><span data-stu-id="f3be0-114">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="f3be0-115">请参阅[硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="f3be0-115">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> 

## <a name="step-1-install-the-rest-apis"></a><span data-ttu-id="f3be0-116">步骤 1：安装 REST Api</span><span class="sxs-lookup"><span data-stu-id="f3be0-116">Step 1: Install the REST APIs</span></span>

1. <span data-ttu-id="f3be0-117">以管理员身份运行 Windows PowerShell (**启动**菜单 > 类型**PowerShell** > 右键单击 >**以管理员身份运行**)。</span><span class="sxs-lookup"><span data-stu-id="f3be0-117">Run Windows PowerShell as Administrator (**Start** menu > type **PowerShell** > right click > **Run as administrator**).</span></span> 
2. <span data-ttu-id="f3be0-118">转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="f3be0-118">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="f3be0-119">在以下文本替换`Default Web Site`， `mgmtServiceAppPool`， `domain/user`， `password`，和`domain\group`与你的值：</span><span class="sxs-lookup"><span data-stu-id="f3be0-119">In the following text, replace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    <span data-ttu-id="f3be0-120">在以下示例中，我们将使用`Default Web Site`，创建名为应用程序池`RESTAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，并授予 BizTalk Server Administrators 组的权限。</span><span class="sxs-lookup"><span data-stu-id="f3be0-120">In the following example, we use the `Default Web Site`, create an application pool named `RESTAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the BizTalk Server Administrators group permissions.</span></span> <span data-ttu-id="f3be0-121">确保输入以下信息，包括单个空格周围值加引号：</span><span class="sxs-lookup"><span data-stu-id="f3be0-121">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="f3be0-122">完成后， **BizTalkManagementService**在 IIS 中创建应用程序：</span><span class="sxs-lookup"><span data-stu-id="f3be0-122">When complete, the **BizTalkManagementService** application is created within IIS:</span></span>  
    <span data-ttu-id="f3be0-123">![BizTalkManagementService 应用程序](../core/media/biztalkmanagementservice-apppool.png)</span><span class="sxs-lookup"><span data-stu-id="f3be0-123">![BizTalkManagementService application](../core/media/biztalkmanagementservice-apppool.png)</span></span>

4. <span data-ttu-id="f3be0-124">若要确认其是否工作，请浏览到`http://localhost/BizTalkManagementService/swagger`。</span><span class="sxs-lookup"><span data-stu-id="f3be0-124">To confirm it’s working, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span> <span data-ttu-id="f3be0-125">如果系统会提示登录，是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="f3be0-125">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

> [!WARNING]
> <span data-ttu-id="f3be0-126">BizTalkManagementService 应用程序在 IIS 中的使用的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f3be0-126">The BizTalkManagementService application in IIS uses a web.config file.</span></span> <span data-ttu-id="f3be0-127">Web.config 中的元素**区分大小写**。</span><span class="sxs-lookup"><span data-stu-id="f3be0-127">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="f3be0-128">因此在执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。</span><span class="sxs-lookup"><span data-stu-id="f3be0-128">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="f3be0-129">如果您不确定的这种情况，下面是找出的简单办法：</span><span class="sxs-lookup"><span data-stu-id="f3be0-129">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="f3be0-130">打开**计算机管理**，然后展开**本地用户和组**。</span><span class="sxs-lookup"><span data-stu-id="f3be0-130">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="f3be0-131">选择**组**，向下滚动到**SQLServer...**</span><span class="sxs-lookup"><span data-stu-id="f3be0-131">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="f3be0-132">组。</span><span class="sxs-lookup"><span data-stu-id="f3be0-132">groups.</span></span> 
> 3. <span data-ttu-id="f3be0-133">在下面的示例，请注意**BOOTCAMPBTS2016**是在全大写形式。</span><span class="sxs-lookup"><span data-stu-id="f3be0-133">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="f3be0-134">如果您看到全部大写的则所有 caps 中输入计算机名称。</span><span class="sxs-lookup"><span data-stu-id="f3be0-134">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![计算机名称是在全大写形式](../core/media/groups-case.png)

<span data-ttu-id="f3be0-136">现在，通过 IIS 公开 REST Api，它们可以访问和执行由其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3be0-136">Now that the REST APIs are exposed through IIS, they can be accessed and executed by other applications.</span></span> <span data-ttu-id="f3be0-137">[功能包 REST API 参考](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)列出了 Api。</span><span class="sxs-lookup"><span data-stu-id="f3be0-137">[Feature Pack REST API reference](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016) lists the APIs.</span></span>

<span data-ttu-id="f3be0-138">您可以更改谁有权访问通过手动更新**web.config**文件，它是管理应用程序的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f3be0-138">You can change who has access by manually updating the **web.config** file, which is in the root folder of the management application.</span></span> <span data-ttu-id="f3be0-139">例如，使用以下命令以允许任何人访问 swagger 输出：</span><span class="sxs-lookup"><span data-stu-id="f3be0-139">For example, use the following to allow anyone access to the swagger output:</span></span> 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a><span data-ttu-id="f3be0-140">步骤 2：测试 Api</span><span class="sxs-lookup"><span data-stu-id="f3be0-140">Step 2: Test the APIs</span></span>

1. <span data-ttu-id="f3be0-141">在 BizTalk 服务器上，浏览到`http://localhost/BizTalkManagementService/swagger`。</span><span class="sxs-lookup"><span data-stu-id="f3be0-141">On the BizTalk Server, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span>

2. <span data-ttu-id="f3be0-142">滚动到**主机**，然后选择**显示/隐藏**。</span><span class="sxs-lookup"><span data-stu-id="f3be0-142">Scroll to **Hosts**, and select **Show/Hide**.</span></span> <span data-ttu-id="f3be0-143">GET 命令;单击此行：</span><span class="sxs-lookup"><span data-stu-id="f3be0-143">There is a GET command; click this row:</span></span>  
<span data-ttu-id="f3be0-144">![获取所有主机](../core/media/managment-rest-apis-hosts-get.png)</span><span class="sxs-lookup"><span data-stu-id="f3be0-144">![GET all hosts](../core/media/managment-rest-apis-hosts-get.png)</span></span>

3. <span data-ttu-id="f3be0-145">它显示的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3be0-145">It shows the details.</span></span> <span data-ttu-id="f3be0-146">选择**试试看**:</span><span class="sxs-lookup"><span data-stu-id="f3be0-146">Select **Try it out**:</span></span>  
<span data-ttu-id="f3be0-147">![进行试用](../core/media/managment-rest-apis-hosts-tryitout.png)</span><span class="sxs-lookup"><span data-stu-id="f3be0-147">![Try it out](../core/media/managment-rest-apis-hosts-tryitout.png)</span></span>

4. <span data-ttu-id="f3be0-148">响应正文将返回所有主机：</span><span class="sxs-lookup"><span data-stu-id="f3be0-148">The Response Body returns all the hosts:</span></span>  
![响应](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> <span data-ttu-id="f3be0-150">如果浏览到`http://localhost/BizTalkManagementService`，应收到一个 500 错误。</span><span class="sxs-lookup"><span data-stu-id="f3be0-150">If you browse to `http://localhost/BizTalkManagementService`, you should get a 500 error.</span></span> <span data-ttu-id="f3be0-151">这是一件好事。</span><span class="sxs-lookup"><span data-stu-id="f3be0-151">That’s a good thing.</span></span> <span data-ttu-id="f3be0-152">只需添加`/swagger`到末尾的 URL，并且您将看到可用的 REST Api。</span><span class="sxs-lookup"><span data-stu-id="f3be0-152">Just add `/swagger` to the end of URL, and you’ll see the available REST APIs.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f3be0-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3be0-153">See also</span></span>
 [<span data-ttu-id="f3be0-154">配置功能包</span><span class="sxs-lookup"><span data-stu-id="f3be0-154">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)