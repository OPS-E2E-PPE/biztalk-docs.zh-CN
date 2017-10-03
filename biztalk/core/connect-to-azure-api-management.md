---
title: "连接到 Azure API 管理使用 BizTalk Server |Microsoft 文档"
description: "使用 BizTalk 功能包 1 BizTalk Server 中连接到 API 管理"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d0c5e4cd2a0ebbd7108845ea15de468d0e0a5a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-azure-api-management"></a><span data-ttu-id="9881a-103">连接到 Azure API 管理</span><span class="sxs-lookup"><span data-stu-id="9881a-103">Connect to Azure API Management</span></span>
<span data-ttu-id="9881a-104">现在，你可以轻松地公开你通过从 BizTalk 的 API 管理的 SOAP 终结点。</span><span class="sxs-lookup"><span data-stu-id="9881a-104">You can now easily expose your SOAP endpoint through API Management from BizTalk.</span></span>

## <a name="what-is-azure-api-management"></a><span data-ttu-id="9881a-105">Azure API Management 是什么</span><span class="sxs-lookup"><span data-stu-id="9881a-105">What is Azure API Management</span></span>
<span data-ttu-id="9881a-106">Azure API 管理用于将 Api 发布到外部和内部客户用作的成套解决方案中。</span><span class="sxs-lookup"><span data-stu-id="9881a-106">Use Azure API Management as a turnkey solution for publishing APIs to external and internal customers.</span></span> <span data-ttu-id="9881a-107">快速创建一致和现代 API 网关，用于任何位置，托管的现有后端服务安全和保护它们免受滥用行为和过度使用，并获取深入了解使用情况和运行状况。</span><span class="sxs-lookup"><span data-stu-id="9881a-107">Quickly create consistent and modern API gateways for existing back-end services hosted anywhere, secure and protect them from abuse and overuse, and get insights into usage and health.</span></span> <span data-ttu-id="9881a-108">此外，自动化和扩展开发人员载入有助于使 API 程序，启动和运行。</span><span class="sxs-lookup"><span data-stu-id="9881a-108">Plus, automate and scale developer onboarding to help get your API program up and running.</span></span> 

<span data-ttu-id="9881a-109">请参阅[API 管理](https://azure.microsoft.com/en-us/services/api-management/)若要了解有关 API 管理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9881a-109">See [API Management](https://azure.microsoft.com/en-us/services/api-management/) to learn more about API Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9881a-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="9881a-110">Prerequisites</span></span>
* <span data-ttu-id="9881a-111">配置并设置[Azure API 管理](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="9881a-111">Configure and set up [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="9881a-112">创建[虚拟网络](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet)BizTalk 机和 API 管理实例之间</span><span class="sxs-lookup"><span data-stu-id="9881a-112">Create a [virtual network](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet) between your BizTalk Machine and the API Managemenet instance</span></span>


1. <span data-ttu-id="9881a-113">在 Azure 门户中，打开你的 API 管理，然后选择**Api**从菜单：</span><span class="sxs-lookup"><span data-stu-id="9881a-113">In the Azure portal, open up your API management, and select **APIs** from the menu:</span></span>

    ![选择 BizTalk API](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="9881a-115">选择的选项**WSDL**新的 API 部分中：</span><span class="sxs-lookup"><span data-stu-id="9881a-115">Select the option for **WSDL** in the New API section:</span></span>

    ![选择 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="9881a-117">若要连接到 API 管理应用于 BizTalk WSDL，请将 URL 复制到计算机 BizTalk SOAP 终结点的完整 URI。</span><span class="sxs-lookup"><span data-stu-id="9881a-117">To connect to API Management to your BizTalk WSDL, copy the URL to your BizTalk computer with the full URI to your SOAP endpoint.</span></span> <span data-ttu-id="9881a-118">例如，复制`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:</span><span class="sxs-lookup"><span data-stu-id="9881a-118">For example, copy `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:</span></span>

    ![从 WSDL BizTalk 创建 API](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="9881a-120">如果你想要使用选择**SOAP 传递**，或设置**到 REST SOAP**服务。</span><span class="sxs-lookup"><span data-stu-id="9881a-120">Select if you want to use a **SOAP pass-through**, or set up a **SOAP to REST** service.</span></span>
5. <span data-ttu-id="9881a-121">输入**名称**你的 api，**说明**，和**API Url 后缀**为你的服务。</span><span class="sxs-lookup"><span data-stu-id="9881a-121">Enter the **name** of your API, the **Description**, and the **API Url suffix** for your service.</span></span>
6. <span data-ttu-id="9881a-122">选择**创建**创建到后端 SOAP 终结点的通信。</span><span class="sxs-lookup"><span data-stu-id="9881a-122">Select **Create** to create the communication to your backend SOAP endpoint.</span></span>

## <a name="see-also"></a><span data-ttu-id="9881a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9881a-123">See also</span></span>
[<span data-ttu-id="9881a-124">配置功能包</span><span class="sxs-lookup"><span data-stu-id="9881a-124">Configure the feature pack</span></span>](configure-the-feature-pack.md)