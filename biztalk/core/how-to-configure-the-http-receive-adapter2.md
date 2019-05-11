---
title: 如何配置 HTTP 接收 Adapter2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73b04356f7c09d8aa2a24d816f02dc66e5d414d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340843"
---
# <a name="how-to-configure-the-http-receive-adapter"></a>如何配置 HTTP 接收适配器
您可以使用 HTTP 接收适配器将消息提交给 BizTalk Server。 HTTP 接收适配器是在 IIS 进程中托管的 Internet 信息服务 (IIS) ISAPI 扩展。  
  
### <a name="to-configure-the-http-receive-adapter"></a>若要配置 HTTP 接收适配器  
  
1.  将 HTTP 接收适配器 (BTSHTTPReceive.dll) 从 **\<BizTalk2010 > \HttpReceive >** 包含单一登录 (SSO) 项目的文件夹 (例如， **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。  
  
    1.  添加新的 Web 服务扩展添加到 mySSODemo。  
  
    2.  浏览到并复制 < BizTalk_install > \HttpReceive 到文件夹包含 SSO 项目，例如，  
  
         <Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.  
  
    3.  将 mySSODemo Web 服务扩展到的状态设置**允许**。  
  
2.  重新启动 IIS 以确保所有更改都都生效。  
  
## <a name="see-also"></a>请参阅  
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)