---
title: "如何配置 HTTP 接收 Adapter2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c39e55ca233ef9875d3d56d25312ef879e3c539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a>如何配置 HTTP 接收适配器
您可以使用 HTTP 接收适配器将消息提交到 BizTalk Server。 HTTP 接收适配器是承载于 IIS 进程的 Internet 信息服务 (IIS) ISAPI 扩展。  
  
### <a name="to-configure-the-http-receive-adapter"></a>若要配置 HTTP 接收适配器，请执行以下操作：  
  
1.  复制 HTTP 从接收适配器 (BTSHTTPReceive.dll)  **\<BizTalk2010 > \HttpReceive >**到包含你的单一登录 (SSO) 项目的文件夹 (例如， **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。  
  
    1.  将新的 Web 服务扩展添加到 mySSODemo。  
  
    2.  例如，浏览到 <BizTalk_install>\HttpReceive，并将其复制到包含 SSO 项目的文件夹。  
  
         <Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll。  
  
    3.  设置到 mySSODemo Web 服务扩展的状态**允许**。  
  
2.  重新启动 IIS 以确保所有更改都生效。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on3.md)