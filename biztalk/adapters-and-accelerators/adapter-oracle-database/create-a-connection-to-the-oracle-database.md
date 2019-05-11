---
title: 创建与 Oracle 数据库的连接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, connecting to the Oracle Database
ms.assetid: 95f7905a-abad-4841-85c4-62cf0cc1e044
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dddc8a375672227358ee82c54035382ae0838da3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529289"
---
# <a name="create-a-connection-to-the-oracle-database"></a>创建与 Oracle 数据库的连接
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 在这种情况下，它支持到 Oracle 数据库通过 WCF 终结点地址的通信。 在 WCF 中，终结点地址通常表示为统一资源标识符 (URI)，用于标识该服务的网络位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]用于建立与 Oracle 数据库的连接。  
  
 必须指定连接 URI 时您：  
  
- 创建通道工厂或通道侦听器使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型或创建使用 WCF 客户端或服务主机时[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型。  
  
- 创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务接口[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型解决方案。  
  
- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持建立与 Oracle 数据库的连接的两种方法：  
  
- **使用 tnsnames.ora**。 在此方法中，连接由适配器客户端提供的 URI 包含 tnsnames.ora 文件中指定的网络服务名称。 适配器提取连接参数，如服务器名称、 服务名称、 端口号，从该文件中的 net 服务名称条目等。 若要使用此方法，运行 Oracle 客户端的计算机必须配置为在 tnsnames.ora 文件中包含的 Oracle 数据库的 net 服务名称。  
  
  > [!IMPORTANT]
  >  由于 Oracle 客户端限制， **DataSourceName**中的参数 （net 服务名称）[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)不能包含超过 39 个字符，如果您正在执行在事务中的操作。 因此，请确保为指定的值**DataSourceName**参数是小于或等于 39 个字符如果您将在事务中执行的操作。  
  
- **而无需使用 tnsnames.ora**。 在此方法时，适配器客户端指定直接在连接 URI 中的连接参数。 这不需要网络服务名称必须包含在客户端计算机上的 tnsnames.ora 文件中。 这种方法甚至不需要在客户端计算机上显示的 tnsname.ora 文件。  
  
  > [!IMPORTANT]
  >  如果你在事务中执行操作，则不支持这种模式的连接。 这是由于 Oracle 客户端的限制。  
  
  在本部分中的主题介绍如何建立之间的连接[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]和，它可以提供与 Oracle 数据库：  
  
- 有关配置 Oracle 客户端的信息。  
  
- 有关连接属性和 Oracle 连接 URI 的结构信息。  
  
- 演示如何通过使用建立的连接的主题的链接[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
- 有关连接到 Oracle 数据库使用 Windows 身份验证的信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 Oracle 数据库适配器的 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a>请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)