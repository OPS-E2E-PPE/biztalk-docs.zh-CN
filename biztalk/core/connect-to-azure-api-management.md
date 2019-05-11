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
ms.openlocfilehash: fd316e66519446be59e6ba0ff6cf66799c7f9523
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390458"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a>在 API 管理中发布 BizTalk SOAP 终结点

将 BizTalk SOAP 终结点公开为 API 管理中的服务。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 1**，可以公开 SOAP 终结点通过从 BizTalk 的 API 管理。 您可以执行此操作在 Azure 门户中使用 API 管理。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，可以公开 Wcf-basichttp 接收位置作为使用 BizTalk 管理 Azure API 管理中的终结点。 

> [!TIP]
> [什么是 API 管理？](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)是一个不错的资源以了解并了解有关此 Azure 服务的详细信息。

## <a name="prerequisites"></a>先决条件
* 配置和设置[Azure API 管理](https://docs.microsoft.com/azure/api-management/api-management-get-started)
* 创建[虚拟网络](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk 计算机和 API 管理实例之间
* 安装[功能包 2](https://aka.ms/bts2016fp2) BizTalk 服务器上

## <a name="create-using-api-management-in-azure-portal"></a>创建在 Azure 门户中使用 API 管理 
1. 在中[Azure 门户](https://portal.azure.com)，打开 API 管理，并选择**Api**:

    ![选择 biztalk API](../core/media/select-api-for-biztalk.png)
    
2. 选择**WSDL**:

    ![选择 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. 配置您的 WSDL 属性： 

   1. **WSDL 规范**:输入你的 BizTalk SOAP 终结点的完整 URI。 例如，输入类似`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`或`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`。  

   2. **SOAP 传递**或**SOAP 到 REST** :选择您的首选项： 
       * **SOAP 到 REST**:从现有的基于 SOAP 的 web 服务创建基于 REST 的 HTTP Api
       * **SOAP 直通**:可作为 SOAP API 的代理 

   3. 输入你首选**显示名称**，**名称**，**说明**， **API Url 后缀**，**产品**，并**版本**。

      完成后，您的 WSDL 配置看起来类似于以下内容： 

      ![从 WSDL BizTalk 创建 API](../core/media/create-api-from-wsdl-biztalk.png)

4. 选择“创建”。

## <a name="create-using-the-biztalk-administration"></a>创建使用 BizTalk 管理

> [!NOTE] 
> 此功能支持使用 Wcf-basichttp 接收位置。 

1. 在 BizTalk 管理控制台中，右击你 Wcf-basichttp 接收位置，然后选择**发布到 API 管理**:  

    ![发布菜单选项](../core/media/publish-to-api-management-option.png)
 
2. 配置您的 API 管理属性： 

   1. **单一登录**到 Azure 订阅，选择**订阅**并**资源组**具有您的 API 管理服务，，然后选择你的服务。

   2. **WSDL 规范链接**WSDL 文件自动进行填充。 替换**localhost**具有 DNS 名称或 IP 地址的 BizTalk Server。 

   3. 选择**SOAP 直通**或**SOAP 到 REST**:  
      * **SOAP 到 REST**:从现有的基于 SOAP 的 web services 创建基于 REST 的 HTTP Api
      * **SOAP 直通**:可作为 SOAP API 的代理 

        API 可以通过更改发布这两种方式**API URL 后缀**，然后再将使用不同的 API 类型再次发布。

   4. **API 名称**会自动填充的接收位置名称。

   5. 选择**API URL 后缀**，是由使用者的 api。 

      完成后，您的属性类似于以下：  
      ![将发布到 API 窗口](../core/media/api-management-publish-window.png)


3. 选择**发布**。 登录成功时，接收位置显示为中的 API 管理中的服务[Azure 门户](https://portal.azure.com)。 

## <a name="do-more"></a>执行更多操作
Azure API 管理是功能强大的服务，可通过很多 Azure 服务，包括逻辑应用。 API 管理包括许多功能，包括速率限制和配额，有权访问你的 Api、 缓存、 和的详细信息。 请参阅[什么是 API 管理？](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)若要开始。

## <a name="see-also"></a>另请参阅
[配置功能包](configure-the-feature-pack.md)
