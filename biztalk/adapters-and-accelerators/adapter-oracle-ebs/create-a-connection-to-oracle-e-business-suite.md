---
title: 创建与 Oracle E-business Suite 的连接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeeab604-155e-4806-b77a-45319a3f8cc0
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0da85f6c0968eb7257e980bdbd65a48fcf734f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973302"
---
# <a name="create-a-connection-to-oracle-e-business-suite"></a>创建与 Oracle E-business Suite 的连接
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 在这种情况下，它支持到 Oracle E-business Suite 通过 WCF 终结点地址的通信。 WCF 中的终结点地址标识服务的网络位置，并通常都表示为统一资源标识符 (URI)。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于建立与 Oracle E-business Suite 的连接。 必须指定连接 URI 时您：  
  
- 创建通道工厂或通道侦听器使用的 WCF 通道模型或创建 WCF 客户端或服务主机使用 WCF 服务模型时。  
  
- 创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]BizTalk Server 解决方案。  
  
- 使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  

## <a name="ways-to-connect-to-oracle"></a>如何连接到 Oracle  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持两种方法来建立与基础的 Oracle 数据库的连接：  
  
-   **使用 tnsnames.ora**。 在此方法中，连接由适配器客户端提供的 URI 包含仅输入 tnsnames.ora 文件中的 net 服务名称。 适配器从文件中的 net 服务名称条目中提取的连接参数，如服务器名称、 服务名称、 端口号等。 若要使用此方法，运行 Oracle 客户端的计算机必须配置为在 tnsnames.ora 文件中包含的 Oracle 数据库的 net 服务名称。  
  
    > [!IMPORTANT]
    >  由于 Oracle 客户端限制， **DataSourceName**中的参数 （net 服务名称）[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)如果您不能包含超过 39 个字符在事务中执行操作。 因此，如果要在事务中执行操作，请确保**DataSourceName**参数值是否小于或等于 39 个字符。  
  
-   **而无需使用 tnsnames.ora**。 在此方法时，适配器客户端输入直接在连接 URI 中的连接参数。 这不需要网络服务名称必须包含在客户端计算机上的 tnsnames.ora 文件中。 这种方法甚至不需要在客户端计算机上显示的 tnsnames.ora 文件。  
  
    > [!IMPORTANT]
    >  如果你在事务中执行操作，则不支持这种模式的连接。 这是由于 Oracle 客户端的限制。  

## <a name="in-this-section"></a>本节内容    
 以下主题介绍如何建立之间的连接[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]和 Oracle E-business Suite:  
  
-   [配置 Oracle 客户端 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)： 有关使用 tnsnames.ora 到 cconfiguring Oracle 客户端 （使用 tnsnames.ora 才能建立连接时才需要） 的信息  
  
-   [创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)： 连接属性和 Oracle E-business Suite 连接 URI 的结构信息
  
-   [连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)： 连接到 Oracle 使用 Windows 身份验证的信息
  