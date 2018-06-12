---
title: 发布 SOAP 终结点 API 管理 |Microsoft 文档
description: 使用功能包 1 和功能包 2，以公开 BizTalk WCF Basic HTTP 接收 SOAP 终结点在 API 管理中的位置。 你可以使用 BizTalk 管理控制台中，执行此操作，或在 Azure 门户中粘贴你直接在 API 管理中的终结点。
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
ms.openlocfilehash: eb716729dcdbac07c5b17cf267866cf282046a70
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848949"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a>在 API 管理中发布 BizTalk SOAP 终结点

将 BizTalk SOAP 终结点公开为 Azure API 管理中的服务。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 1**，可以公开 SOAP 终结点通过从 BizTalk 的 API 管理。 你可以执行此操作在 Azure 门户中使用 API 管理。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，您可以公开 WCF BasicHTTP 接收为终结点，使用 BizTalk 管理 Azure API 管理中的位置。 

> [!TIP]
> [什么是 API 管理](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)是一个很好的资源，若要了解，并了解有关此 Azure 服务的详细信息。

## <a name="prerequisites"></a>必要條件
* 配置并设置[Azure API 管理](https://docs.microsoft.com/azure/api-management/api-management-get-started)
* 创建[虚拟网络](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk 计算机和 API 管理实例之间
* 安装[功能包 2](https://aka.ms/bts2016fp2) BizTalk 服务器上

## <a name="create-using-api-management-in-azure-portal"></a>创建在 Azure 门户中使用 API 管理 
1. 在[Azure 门户](https://portal.azure.com)，打开你的 API 管理，然后选择**Api**:

    ![选择 BizTalk API](../core/media/select-api-for-biztalk.png)
    
2. 选择**WSDL**:

    ![选择 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. 配置 WSDL 属性： 

    1. **WSDL 规范**： 输入你的 BizTalk SOAP 终结点的完整 URI。 例如，输入类似`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`或`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`。  

    2. **SOAP 传递**或**到 REST SOAP** ： 选择您的首选项： 
        * **对其余部分的 SOAP**： 从现有的基于 SOAP 的 web 服务创建 REST 基于 HTTP Api
        * **SOAP 传递**： 充当 SOAP API 的代理 

    3. 输入你首选**显示名称**，**名称**，**说明**， **API Url 后缀**，**产品**，和**版本**。

    完成后，你 WSDL 配置看起来类似于以下内容： 

    ![从 WSDL BizTalk 创建 API](../core/media/create-api-from-wsdl-biztalk.png)

4. 选择“创建”。

## <a name="create-using-the-biztalk-administration"></a>创建使用 BizTalk 管理

> [!NOTE] 
> 此功能支持与 WCF BasicHTTP 接收位置。 

1. 在 BizTalk 管理控制台中，右击你 WCF BasicHTTP 接收位置，然后选择**发布到 API 管理**:  

    ![发布菜单选项](../core/media/publish-to-api-management-option.png)
 
2. 配置你的 API 管理属性： 

    1. **在登录**到 Azure 订阅，选择**订阅**和**资源组**具有你的 API 管理服务，，然后选择你的服务。

    2. **WSDL 规范链接**自动填充为 WSDL 文件。 替换**localhost**具有 DNS 名称或 IP 地址的 BizTalk Server。 

    3. 选择**SOAP 传递**或**到 REST SOAP**:  
        * **对其余部分的 SOAP**： 从现有的基于 SOAP 的 web 服务创建 REST 基于 HTTP Api
        * **SOAP 传递**： 充当 SOAP API 的代理 

        API 可以通过更改发布这两种方式**API URL 后缀**，然后再将发布再次使用不同的 API 类型。

    4. **API 名称**接收位置名称自动填充。

    5. 选择**API URL 后缀**那就是由使用者的 api。 

    完成后，你的属性类似于以下：  
    ![将发布到 API 窗口](../core/media/api-management-publish-window.png)


3. 选择**发布**。 接收位置成功后，将显示为中的 API 管理服务[Azure 门户](https://portal.azure.com)。 

## <a name="do-more"></a>执行更多操作
Azure API 管理是功能强大的服务所使用的 Azure 服务，包括 Logic Apps 很多。 API 管理包括许多功能，包括速率限制和配额，有权访问您的 Api、 缓存、 和的详细信息。 请参阅[API Management 是什么？](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)吧。

## <a name="see-also"></a>另请参阅
[配置功能包](configure-the-feature-pack.md)
