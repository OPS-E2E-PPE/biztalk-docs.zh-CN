---
title: 将连接到 Oracle E-business Suite 使用适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80ff31d4-be4c-42d7-a321-8f01b40dd71e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8551c0f09d65d50b87248a6b0dc4030a612fc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217861"
---
# <a name="connect-to-oracle-e-business-suite-using-the-adapter"></a>将连接到 Oracle E-business Suite 使用适配器
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET 11.1.0.7 用于连接到 Oracle E-business Suite。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI)，以连接到 Oracle E-business Suite 的连接。 在内部，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接到通过 URI 基础的 Oracle 数据库。 通过连接 URI 适配器客户端可以指定要连接到外部系统的连接参数。  

## <a name="connectivity-to-oracle-ebs"></a>连接到 Oracle EBS  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够连接到 Oracle E-business Suite 中的以下两种方法：  
  
-   **使用 tnsnames.ora**： 连接适配器客户端提供的 URI 包含仅在 tnsnames.ora 文件中指定的 net 服务名称。 适配器从 tnsnames.ora 文件中的 net 服务名称条目提取如服务器名称、 服务名称和端口号的连接参数。 若要使用此方法，必须配置运行 Oracle 客户端的计算机为 tnsnames.ora 文件中包括 Oracle 数据库的 net 服务名称。  
  
    > [!IMPORTANT]
    >  由于 Oracle 客户端存在的限制， **DataSourceName**中的参数 （net 服务名称）[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)不能包含超过 39 个字符，如果您正在执行操作在中的事务。 因此，请确保为指定的值**DataSourceName**参数是否小于或等于 39 个字符如果你将在事务中执行操作。  
  
-   **而无需使用 tnsnames.ora**： 连接 URI 的适配器客户端提供包含如服务器名称、 服务名称和端口号的连接参数。 在这种情况下，在 tnsnames.ora 文件中或实际 tnsnames.ora 文件本身，net 服务名称不必存在于客户端计算机上。 如果有大量的用户连接到 Oracle 数据库中您的组织，并添加/更新服务器不会导致手动添加/更新每个客户端计算机上的 tnsnames.ora 文件中的连接详细信息，这非常有用。  
  
    > [!IMPORTANT]
    >  如果你在事务中执行操作，则不支持这种模式的连接。 这是因为 Oracle 客户端的限制。  
  
 有关将连接到 Oracle E-business Suite 的详细信息，请参阅[创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。  
  
 请确保您遵守安全指导原则建立与 Oracle E-business Suite 的连接时。 请参阅[确保 Oracle EBS 应用的安全](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)。
  
## <a name="enter-client-credentials"></a>输入客户端凭据  
 在[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你可以提供凭据以连接到 Oracle E-business Suite 在以下两个位置：  
  
-   上**安全**选项卡中**配置适配器**对话框。 你可以找到此对话框在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-   在**OracleUserName**和**OraclePassword**绑定属性**绑定属性**选项卡中**配置适配器**对话框。 你可以找到此对话框在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 在这种情况下，在绑定文件中的纯文本存储的凭据。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定允许你指定的一组将用于连接到 Oracle E-business Suite 的凭据 （Oracle E-business Suite 或 Oracle 数据库） 的属性。  
  
-   若要使用 Oracle 数据库凭据进行连接，指定**ClientCredentialType**绑定属性作为**数据库**，然后在**安全**选项卡上，指定数据库中的凭据**用户名**和**密码**文本框。  如果你将执行任何 Oracle E-business Suite 项目 （接口表、 接口视图、 并发程序、 请求集或 Oracle E-business Suite PL/SQL Api） 上的操作，你还必须提供中的 Oracle E-business Suite 凭据**OracleUserName**和**OraclePassword**绑定属性。  
  
-   若要使用 Oracle E-business Suite 凭据进行连接，指定**ClientCredentialType**绑定属性作为**EBusiness**，然后指定中的 Oracle E-business Suite 凭据**用户名称**和**密码**文本框上**安全**选项卡。你还必须指定用于的 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。  
  
 有关指定客户端凭据的详细信息，请参阅[为 Oracle E-business Suite 配置登录凭据](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)。  
  
## <a name="using-windows-authentication"></a>使用 Windows 身份验证  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将连接到 Oracle E-business Suite 时，支持 Windows 身份验证。 使用 Windows 身份验证适配器客户端可以确定用户的标识基于的 Windows 登录凭据，而且可以利用 Windows 环境的内置安全性。 有关使用 Windows 身份验证连接到 Oracle E-business Suite 的信息，请参阅[连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
## <a name="see-also"></a>另请参阅  
[为 Oracle E-business 适合了解 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)