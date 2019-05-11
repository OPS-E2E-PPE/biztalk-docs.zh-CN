---
title: 安装面向服务的解决方案之前 |Microsoft Docs
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
ms.openlocfilehash: ed78cdffeb93f22bb42f3af999608ea01559d7b6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530509"
---
# <a name="before-installing-the-service-oriented-solution"></a>然后再安装面向服务的解决方案
以下系统必备组件必须有可供一台计算机上安装面向服务的解决方案的存根版本：  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 的用户。  
  
- 支持的软件[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]。  
  
- 最新版本的 IBM WebSphere MQ 客户端的 Windows  
  
  > [!NOTE]
  >  MQSeries 服务器不需要为解决方案的存根版本。  
  
  > [!NOTE]
  >  可以从 IBM 网站下载 IBM WebSphere MQ 客户端的 Windows。  
  
  对于一台计算机上安装面向服务的解决方案的内联和适配器版本：  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] 的用户。  
  
  > [!NOTE]
  >  所需的域帐户映射的企业单一登录 (SSO) 的凭据。 我们建议为 BizTalk 服务和 ENTSSO 服务帐户使用域帐户。  
  
- 支持的软件[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]。  
  
- 对运行 MQSeries 服务器的计算机访问的本地计算机上的 MQSeries 服务器。 对于内联版本，MQSeries 客户端 Api 必须在运行解决方案的业务流程的 BizTalk 服务器上可用。  
  
  > [!NOTE]
  >  MQSeries 服务器的版本必须与 BizTalk Server MQSeries 适配器所需的版本匹配。 这可以包括 IBM WebSphere MQ Fix Pack 10 (CSD10) 或更高版本的 Windows 版本 5.3。  
  
  > [!NOTE]
  >  使用 MQSeries 这样对服务器的分布式组件对象模型 (DCOM) 调用如功能时，请确保你没有启用了-基于网络地址转换 (NAT） 防火墙。 客户端必须能够访问服务器的实际 IP 地址，并基于 NAT 的防火墙将此地址为客户端将无法识别的内容。  
  
- IBM 大型机使用 CICS 和 Transaction X，如果您使用的解决方案，则需要大型机的变体。 在这种情况下，必须在大型机上安装 CICS 应用程序 （COBOL 代码） 和 Microsoft Host Integration Server (HIS) 所需访问大型机。  
  
   如果没有大型机可用于该解决方案，则可以修改要使用存根挂起事务的 Web 服务的端口绑定。 Web 服务生成本地模拟大型机事务的事务。 有关如何修改为存根挂起事务 Web 服务端口绑定的详细信息，请参阅[如何安装的内联版本和适配器版本的面向服务的解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)。  
  
- 在 host Integration Server 需要连接到大型机。  
  
  > [!NOTE]
  >  在 host Integration Server 是作为 BizTalk Server 的一部分。  
  
- Web 服务器配置为使用 HTTPS 连接证书。  
  
## <a name="see-also"></a>请参阅  
 [如何安装该服务的存根版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [如何运行该服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)