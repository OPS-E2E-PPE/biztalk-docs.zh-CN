---
title: 如何配置 HTTP 接收 Adapter1 |Microsoft Docs
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
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd00bdb0b37de46e04e4568019a4f35318e264ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340885"
---
# <a name="how-to-configure-the-http-receive-adapter"></a>如何配置 HTTP 接收适配器
您可以使用 HTTP 接收适配器将消息提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 HTTP 接收适配器是在 IIS 进程中托管的 Internet 信息服务 (IIS) ISAPI 扩展。  
  
### <a name="to-configure-the-http-receive-adapter"></a>若要配置 HTTP 接收适配器  
  
1.  将 HTTP 接收适配器 (BTSHTTPReceive.dll) 从**\<BizTalk\>\HttpReceive\>** 文件夹包含你的单一登录 (SSO) 项目，例如：  
  
     **<Adapter_install>\biztalk\SSO\mySSODemo**  
  
    1.  添加新的 Web 服务扩展添加到 mySSODemo。  
  
    2.  找到并复制 **< BizTalk_install > \HttpReceive**到包含 SSO 项目，例如文件夹：  
  
         **<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**  
  
    3.  将 mySSODemo Web 服务扩展到的状态设置**允许**。  
  
2.  重新启动 IIS 以应用所有更改。  
  
## <a name="see-also"></a>请参阅  
 [保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)