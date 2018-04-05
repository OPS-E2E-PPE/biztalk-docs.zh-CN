---
title: 安装服务面向解决方案之前 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, deployment prerequisites
ms.assetid: 865bd21c-e49a-4647-af91-fefee07ee806
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23f326a6fe028c5b7ea5edf60216c1933eccbdb6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="before-installing-the-service-oriented-solution"></a>在安装面向服务的解决方案之前
若要在单台计算机上安装面向服务的解决方案的存根版本，必须具备以下必备组件：  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]。  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 支持的软件。  
  
-   IBM WebSphere MQ Client for Windows 的最新版本  
  
    > [!NOTE]
    >  对于解决方案的存根版本，MQSeries 服务器不是必需的。  
  
    > [!NOTE]
    >  你可以从 IBM 网站下载 IBM WebSphere MQ Client for Windows。  
  
 对于在单台计算机上安装面向服务的解决方案的内联版本和适配器版本：  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]。  
  
    > [!NOTE]
    >  必须具备域帐户以为企业单一登录 (SSO) 映射凭据。 建议为 BizTalk 服务和 ENTSSO 服务帐户使用域帐户。  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 支持的软件。  
  
-   安装在本地计算机上的 MQSeries 服务器，或具有对运行 MQSeries 服务器的计算机的访问权限。 对于内联版本，在运行解决方案的业务流程的 BizTalk 服务器上，MQSeries 客户端 API 必须可用。  
  
    > [!NOTE]
    >  MQSeries 服务器的版本必须与 BizTalk Server MQSeries 适配器所需的版本。 这可以包括带有 Fix Pack 10 (CSD10) 或更高版本的 IBM WebSphere MQ Windows 版本 5.3。  
  
    > [!NOTE]
    >  当使用诸如 MQSeries 这样对服务器调用分布式组件对象模型 (DCOM) 的功能时，请确保未启用基于网络地址转换 (NAT) 的防火墙。 客户端必须能够通过其实际 IP 地址访问该服务器，并且基于 NAT 的防火墙将此地址翻译为客户端不能识别的地址。  
  
-   如果使用的是需要大型机的变体解决方案，则需要带有 CICS 和 Transaction X 的 IBM 大型机。 在这种情况下，必须在大型机上安装 CICS 应用程序（COBOL 代码），并且必须具备 Microsoft Host Integration Server (HIS) 以访问大型机。  
  
     如果没有大型机可用于该解决方案，则可以修改端口绑定以使用存根 Web Services 来模拟挂起事务。 该 Web Services 将在本地生成事务以模拟大型机事务。 有关如何修改存根 （stub） 挂起的事务 Web 服务的端口绑定的详细信息，请参阅[如何安装在内联和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)。  
  
-   必须具备 Host Integration Server 才能连接到大型机。  
  
    > [!NOTE]
    >  Host Integration Server 是 BizTalk Server 的一部分包括。  
  
-   配置有 HTTPS 连接证书的 Web 服务器。  
  
## <a name="see-also"></a>另请参阅  
 [如何安装服务的存根 （stub） 版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [如何安装内联和服务的适配器版本面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)