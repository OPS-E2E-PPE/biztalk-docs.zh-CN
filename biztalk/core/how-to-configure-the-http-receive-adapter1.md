---
title: "如何配置 HTTP 接收 Adapter1 |Microsoft 文档"
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
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6356a130b412ea849c79213ab55b000ea827f3a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a>如何配置 HTTP 接收适配器
您可以使用 HTTP 接收适配器将消息提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 HTTP 接收适配器是承载于 IIS 进程的 Internet 信息服务 (IIS) ISAPI 扩展。  
  
### <a name="to-configure-the-http-receive-adapter"></a>若要配置 HTTP 接收适配器，请执行以下操作：  
  
1.  复制 HTTP 从接收适配器 (BTSHTTPReceive.dll)  **\<BizTalk > \HttpReceive >**包含你的单一登录 (SSO) 项目，例如的文件夹：  
  
     **< Adapter_install > \biztalk\SSO\mySSODemo**  
  
    1.  将新的 Web 服务扩展添加到 mySSODemo。  
  
    2.  查找并复制**< BizTalk_install > \HttpReceive**例如包含 SSO 项目的文件夹：  
  
         **< Adapter_install > \biztalk\SSO\mySSODemo\BTSHTTPReceive.dll。**  
  
    3.  设置到 mySSODemo Web 服务扩展的状态**允许**。  
  
2.  重新启动 IIS 将应用所有更改。  
  
## <a name="see-also"></a>另请参阅  
 [安全适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)