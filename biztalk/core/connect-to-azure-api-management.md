---
title: 发布 SOAP 终结点 API 管理 |Microsoft Docs
description: 使用功能包 1 和功能包 2，以公开 BizTalk WCF 基本 HTTP 接收与 API 管理中的 SOAP 终结点的位置。 可以使用 BizTalk 管理控制台中，执行此操作，也可以将你直接在 API 管理中的终结点粘贴在 Azure 门户中。
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: 2
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: c8bdb3cb3f2d0fc247ea607a1b34623006315754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993710"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a><span data-ttu-id="e19d2-104">在 API 管理中发布 BizTalk SOAP 终结点</span><span class="sxs-lookup"><span data-stu-id="e19d2-104">Publish BizTalk SOAP endpoints in API Management</span></span>

<span data-ttu-id="e19d2-105">将 BizTalk SOAP 终结点公开为 API 管理中的服务。</span><span class="sxs-lookup"><span data-stu-id="e19d2-105">Expose your BizTalk SOAP endpoints as services within Azure API Management.</span></span> 

<span data-ttu-id="e19d2-106">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 1**，可以公开 SOAP 终结点通过从 BizTalk 的 API 管理。</span><span class="sxs-lookup"><span data-stu-id="e19d2-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, you can expose a SOAP endpoint through API Management from BizTalk.</span></span> <span data-ttu-id="e19d2-107">您可以执行此操作在 Azure 门户中使用 API 管理。</span><span class="sxs-lookup"><span data-stu-id="e19d2-107">You can do this using  API Management in the Azure portal.</span></span> 

<span data-ttu-id="e19d2-108">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，可以公开 Wcf-basichttp 接收位置作为使用 BizTalk 管理 Azure API 管理中的终结点。</span><span class="sxs-lookup"><span data-stu-id="e19d2-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can expose a WCF-BasicHTTP receive location as an endpoint within Azure API Management using BizTalk Administration.</span></span> 

> [!TIP]
> <span data-ttu-id="e19d2-109">[什么是 API 管理？](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)是一个不错的资源以了解并了解有关此 Azure 服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e19d2-109">[What is API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) is a great resource to understand and learn more about this Azure service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e19d2-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="e19d2-110">Prerequisites</span></span>
* <span data-ttu-id="e19d2-111">配置和设置[Azure API 管理](https://docs.microsoft.com/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="e19d2-111">Configure and set up [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="e19d2-112">创建[虚拟网络](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk 计算机和 API 管理实例之间</span><span class="sxs-lookup"><span data-stu-id="e19d2-112">Create a [virtual network](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) between your BizTalk computer and the API Management instance</span></span>
* <span data-ttu-id="e19d2-113">安装[功能包 2](https://aka.ms/bts2016fp2) BizTalk 服务器上</span><span class="sxs-lookup"><span data-stu-id="e19d2-113">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on the BizTalk Server</span></span>

## <a name="create-using-api-management-in-azure-portal"></a><span data-ttu-id="e19d2-114">创建在 Azure 门户中使用 API 管理</span><span class="sxs-lookup"><span data-stu-id="e19d2-114">Create using API Management in Azure portal</span></span> 
1. <span data-ttu-id="e19d2-115">在中[Azure 门户](https://portal.azure.com)，打开 API 管理，并选择**Api**:</span><span class="sxs-lookup"><span data-stu-id="e19d2-115">In the [Azure portal](https://portal.azure.com), open up your API management, and select **APIs**:</span></span>

    ![选择 biztalk API](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="e19d2-117">选择**WSDL**:</span><span class="sxs-lookup"><span data-stu-id="e19d2-117">Select **WSDL**:</span></span>

    ![选择 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="e19d2-119">配置您的 WSDL 属性：</span><span class="sxs-lookup"><span data-stu-id="e19d2-119">Configure your WSDL properties:</span></span> 

   1. <span data-ttu-id="e19d2-120">**WSDL 规范**： 输入你的 BizTalk SOAP 终结点的完整 URI。</span><span class="sxs-lookup"><span data-stu-id="e19d2-120">**WSDL specification** : Enter the full URI to your BizTalk SOAP endpoint.</span></span> <span data-ttu-id="e19d2-121">例如，输入类似`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`或`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`。</span><span class="sxs-lookup"><span data-stu-id="e19d2-121">For example, enter something like `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` or `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span></span>  

   2. <span data-ttu-id="e19d2-122">**SOAP 传递**或**SOAP 到 REST** ： 选择您的首选项：</span><span class="sxs-lookup"><span data-stu-id="e19d2-122">**SOAP pass-through** or **SOAP to REST** : Select your preference:</span></span> 
       * <span data-ttu-id="e19d2-123">**SOAP 到 REST**： 从现有的基于 SOAP 的 web 服务创建 REST 基于 HTTP Api</span><span class="sxs-lookup"><span data-stu-id="e19d2-123">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web service</span></span>
       * <span data-ttu-id="e19d2-124">**SOAP 直通**： 充当 SOAP API 的代理</span><span class="sxs-lookup"><span data-stu-id="e19d2-124">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

   3. <span data-ttu-id="e19d2-125">输入你首选**显示名称**，**名称**，**说明**， **API Url 后缀**，**产品**，并**版本**。</span><span class="sxs-lookup"><span data-stu-id="e19d2-125">Enter your preferred **Display Name**, **Name**, **Description**, **API Url suffix**, **Products**, and **Version**.</span></span>

      <span data-ttu-id="e19d2-126">完成后，您的 WSDL 配置看起来类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="e19d2-126">When finished, your WSDL configuration looks something like the following:</span></span> 

      ![从 WSDL BizTalk 创建 API](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="e19d2-128">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="e19d2-128">Select **Create**.</span></span>

## <a name="create-using-the-biztalk-administration"></a><span data-ttu-id="e19d2-129">创建使用 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="e19d2-129">Create using the BizTalk Administration</span></span>

> [!NOTE] 
> <span data-ttu-id="e19d2-130">此功能支持使用 Wcf-basichttp 接收位置。</span><span class="sxs-lookup"><span data-stu-id="e19d2-130">This feature is supported with WCF-BasicHTTP receive locations.</span></span> 

1. <span data-ttu-id="e19d2-131">在 BizTalk 管理控制台中，右击你 Wcf-basichttp 接收位置，然后选择**发布到 API 管理**:</span><span class="sxs-lookup"><span data-stu-id="e19d2-131">In the BizTalk Administration Console, right-click your WCF-BasicHTTP receive location, and select **Publish to API Management**:</span></span>  

    ![发布菜单选项](../core/media/publish-to-api-management-option.png)
 
2. <span data-ttu-id="e19d2-133">配置您的 API 管理属性：</span><span class="sxs-lookup"><span data-stu-id="e19d2-133">Configure your API management properties:</span></span> 

   1. <span data-ttu-id="e19d2-134">**单一登录**到 Azure 订阅，选择**订阅**并**资源组**具有您的 API 管理服务，，然后选择你的服务。</span><span class="sxs-lookup"><span data-stu-id="e19d2-134">**Sign-in** to your Azure subscription, select the **Subscription** and **Resource Group** that has your API management service, and then select your service.</span></span>

   2. <span data-ttu-id="e19d2-135">**WSDL 规范链接**WSDL 文件自动进行填充。</span><span class="sxs-lookup"><span data-stu-id="e19d2-135">The **WSDL specification link** is automatically populated with your WSDL file.</span></span> <span data-ttu-id="e19d2-136">替换**localhost**具有 DNS 名称或 IP 地址的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="e19d2-136">Replace **localhost** with the DNS name or IP address of the BizTalk Server.</span></span> 

   3. <span data-ttu-id="e19d2-137">选择**SOAP 直通**或**SOAP 到 REST**:</span><span class="sxs-lookup"><span data-stu-id="e19d2-137">Select **SOAP pass-through** or **SOAP to REST**:</span></span>  
      * <span data-ttu-id="e19d2-138">**SOAP 到 REST**： 从现有的基于 SOAP 的 web 服务创建 REST 基于 HTTP Api</span><span class="sxs-lookup"><span data-stu-id="e19d2-138">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web services</span></span>
      * <span data-ttu-id="e19d2-139">**SOAP 直通**： 充当 SOAP API 的代理</span><span class="sxs-lookup"><span data-stu-id="e19d2-139">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

        <span data-ttu-id="e19d2-140">API 可以通过更改发布这两种方式**API URL 后缀**，然后再将使用不同的 API 类型再次发布。</span><span class="sxs-lookup"><span data-stu-id="e19d2-140">The API can be published both ways by changing the **API URL suffix**, and then publishing again using a different API type.</span></span>

   4. <span data-ttu-id="e19d2-141">**API 名称**会自动填充的接收位置名称。</span><span class="sxs-lookup"><span data-stu-id="e19d2-141">The **API name** is automatically populated with the receive location name.</span></span>

   5. <span data-ttu-id="e19d2-142">选择**API URL 后缀**，是由使用者的 api。</span><span class="sxs-lookup"><span data-stu-id="e19d2-142">Select an **API URL suffix** that is to be used by consumers of the API.</span></span> 

      <span data-ttu-id="e19d2-143">完成后，您的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="e19d2-143">When finished, your properties look similar to the following:</span></span>  
      ![将发布到 API 窗口](../core/media/api-management-publish-window.png)


3. <span data-ttu-id="e19d2-145">选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="e19d2-145">Select **Publish**.</span></span> <span data-ttu-id="e19d2-146">登录成功时，接收位置显示为中的 API 管理中的服务[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="e19d2-146">When successful, the receive location is displayed as a service in API Management in the [Azure portal](https://portal.azure.com).</span></span> 

## <a name="do-more"></a><span data-ttu-id="e19d2-147">执行更多操作</span><span class="sxs-lookup"><span data-stu-id="e19d2-147">Do more</span></span>
<span data-ttu-id="e19d2-148">Azure API 管理是功能强大的服务，可通过很多 Azure 服务，包括逻辑应用。</span><span class="sxs-lookup"><span data-stu-id="e19d2-148">Azure API Management is a powerful service that is used by a lot of Azure services, including Logic Apps.</span></span> <span data-ttu-id="e19d2-149">API 管理包括许多功能，包括速率限制和配额，有权访问你的 Api、 缓存、 和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e19d2-149">API Management includes many features, including rate limits and quotas, who has access to your APIs, caching, and more.</span></span> <span data-ttu-id="e19d2-150">请参阅[什么是 API 管理？](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)若要开始。</span><span class="sxs-lookup"><span data-stu-id="e19d2-150">See [What is API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) to get started.</span></span>

## <a name="see-also"></a><span data-ttu-id="e19d2-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e19d2-151">See also</span></span>
[<span data-ttu-id="e19d2-152">配置功能包</span><span class="sxs-lookup"><span data-stu-id="e19d2-152">Configure the feature pack</span></span>](configure-the-feature-pack.md)
