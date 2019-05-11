---
title: 使用 Oracle E-business Suite 中配置动态端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8471e89381e1fea161dcc27d6f35889d9423c231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375703"
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a>使用 Oracle E-business Suite 中配置动态端口
在中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以配置有关的动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。 因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是基于 WCF 的适配器，您可以动态地配置的端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过使用消息上下文属性。  
  
 有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，可能会确定传入消息上的属性，然后中指定 URI、 操作和绑定**表达式**形状，如下面的示例中所示：  
  
```  
Request2=Request1;  
Request2(WCF.Action)="InterfaceTables/Insert/OFA/FA/FA_BOOKS";  
Request2(WCF.BindingType)="oracleEBSBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracleebs://ebs_instance";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
> [!NOTE]
>  使用中的 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`，其中**OracleEBSAdapter**是添加中的 WCF OracleEBS 适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 在前面的示例中，  
  
- 正在从 Request1 消息创建请求 2 消息。 这两个消息映射到操作架构，这在生成使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
- 发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。  
  
  **表达式**形状是 BizTalk 业务流程的一部分。 部署业务流程还会创建 Wcf-custom 发送端口。  
  
  有关配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。
  
## <a name="see-also"></a>请参阅  
[若要创建 Oracle E-business Suite 的应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)