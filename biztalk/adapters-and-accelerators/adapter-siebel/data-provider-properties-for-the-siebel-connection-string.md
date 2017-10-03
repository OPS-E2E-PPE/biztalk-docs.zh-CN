---
title: "Siebel 连接字符串的数据提供程序属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- conncting, to the Siebel system
- Data Provider for Siebel, connection string
ms.assetid: 8ab0c29e-e06b-4e74-be4e-9aa862a05539
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1caedbc1e9560c1bc4d97669241046f0959c2db6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-provider-properties-for-the-siebel-connection-string"></a>Siebel 连接字符串的数据提供程序属性
[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]访问 Siebel 系统。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]反过来使用 Siebel COM 数据控件库来访问 Siebel 系统。 Siebel COM 数据控件与 Siebel Web 客户端捆绑。  
  
 若要建立到 Siebel 系统的连接，ADO.NET 客户端必须指定编码为数据库连接字符串的 Siebel 连接属性。 这是必需的因为[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]实现**DbConnection**来访问基础[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定。  
  
 要连接到 Siebel 系统使用的连接字符串[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]包含以下属性。  
  
|属性|Description|  
|--------------|-----------------|  
|密码|Siebel 系统; 上的用户密码此值是区分大小写。 **注意：** [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]保留在打开 Siebel 系统上的连接时输入的密码的值的大小写。|  
|用户名|Siebel 系统; 上的用户名此值是区分大小写。 **注意：** [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]保留在打开 Siebel 系统上的连接时输入的用户名的值的大小写。|  
|压缩|要使用之间的压缩算法[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]和 Siebel 系统。 支持的值为**无**或**zlib**。 此参数可选。 如果未指定，则 Siebel 系统将提供默认值 (**zlib**)。|  
|加密|之间使用的加密类型[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]和 Siebel 系统。 支持的值为**无**， **mscrypto**，或**rsa**。 此参数可选。 如果未指定，则 Siebel 系统将提供默认值 (**无**)。|  
|语言|对象管理器的语言。 一个示例值是**enu**。 此参数是必需的。|  
|SiebelEnterpriseServer|Siebel 企业服务器的名称。 此参数是必需的。|  
|SiebelGateway|Siebel 服务器 IP 和端口组成。 例如，Siebel_Server:1234。|  
|SiebelObjectManager|企业服务器上的 Siebel 对象管理器的名称。 此参数是必需的。|  
|SiebelRepository|Siebel 存储库。 所需服务器; 上是否存在多个存储库否则为可选。 **注意：**如果多个存储库服务器上是否存在，则必须 SiebelRepository 参数中指定目标存储库。|  
|SiebelServer|Siebel 服务器中。 所需的所有 Siebel 7.5 服务器连接;否则，不设置此参数。|  
|Transport|传输;仅**tcpip**支持。 此参数可选。 如果未指定，则 Siebel 系统将提供默认值 (**tcpip**)。|  
  
 例如：  
  
```  
Username=YourUserName;Password=YourPassword;SiebelGateway=Siebel_Server:1234;SiebelObjectManager=obj_mgr;SiebelEnterpriseServer=ent_server;Language=enu;SiebelRepository=siebel_rep  
```  
  
## <a name="see-also"></a>另请参阅  
 [.NET Framework 数据提供程序用于 Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)