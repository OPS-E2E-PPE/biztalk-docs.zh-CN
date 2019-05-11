---
title: 连接到使用适配器 Oracle E-business Suite |Microsoft Docs
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
ms.openlocfilehash: 00f944cb0cf52b9e50a6e587e1e9b465ec558af6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375649"
---
# <a name="connect-to-oracle-e-business-suite-using-the-adapter"></a>连接到 Oracle E-business Suite 使用适配器
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET 11.1.0.7 用于连接到 Oracle E-business Suite。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI)，以连接到 Oracle E-business Suite 的连接。 在内部，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]对通过 URI 基础的 Oracle 数据库连接。 使用一个连接 URI，适配器客户端可以指定连接参数，以连接到外部系统。  

## <a name="connectivity-to-oracle-ebs"></a>与 Oracle EBS 的连接  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够连接到 Oracle E-business Suite 中的以下两种方法：  
  
- **使用 tnsnames.ora**:连接由适配器客户端提供的 URI 包含 tnsnames.ora 文件中指定的网络服务名称。 适配器从 tnsnames.ora 文件中的 net 服务名称条目提取如服务器名称、 服务名称和端口号的连接参数。 若要使用此方法，运行 Oracle 客户端的计算机必须配置为在 tnsnames.ora 文件中包含的 Oracle 数据库的 net 服务名称。  
  
  > [!IMPORTANT]
  >  由于 Oracle 客户端限制， **DataSourceName**中的参数 （net 服务名称）[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)不能包含超过 39 个字符，如果您正在执行操作在事务中。 因此，请确保为指定的值**DataSourceName**参数是小于或等于 39 个字符如果您将在事务中执行的操作。  
  
- **而无需使用 tnsnames.ora**:连接由适配器客户端提供的 URI 包含如服务器名称、 服务名称和端口号的连接参数。 在这种情况下，net 服务名称在 tnsnames.ora 文件或实际 tnsnames.ora 文件本身，不需要在客户端计算机上显示。 如果有大量用户连接到 Oracle 数据库中你的组织，并添加/更新服务器不会导致手动添加/更新每个客户端计算机上的 tnsnames.ora 文件中的连接详细信息，这非常有用。  
  
  > [!IMPORTANT]
  >  如果你在事务中执行操作，则不支持这种模式的连接。 这是由于 Oracle 客户端的限制。  
  
  有关连接到 Oracle E-business Suite 的详细信息，请参阅[创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。  
  
  请确保符合安全指导原则建立与 Oracle E-business Suite 的连接时。 请参阅[保护 Oracle EBS 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)。
  
## <a name="enter-client-credentials"></a>输入客户端凭据  
 在[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，可以提供凭据以连接到 Oracle E-business Suite 在以下两个位置：  
  
- 上**安全**选项卡**配置适配器**对话框。 您可以找到在此对话框[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
- 在中**OracleUserName**并**OraclePassword**上的绑定属性**绑定属性**选项卡中**配置适配器**对话框。 您可以找到在此对话框[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 在这种情况下，凭据存储在绑定文件中的纯文本。  
  
  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**允许您指定的一组将用于连接到 Oracle E-business Suite 的凭据 （Oracle E-business Suite 或 Oracle 数据库） 的属性绑定。  
  
- 若要使用 Oracle 数据库凭据进行连接，指定**ClientCredentialType**绑定属性作为**数据库**，然后在**安全**选项卡上，指定数据库中的凭据**用户名**并**密码**文本框。  如果您将执行的任何 Oracle E-business Suite 项目 （接口表、 界面视图、 并发程序、 请求集或 Oracle E-business Suite PL/SQL Api） 上的操作，还必须提供中的 Oracle E-business Suite 凭据**OracleUserName**并**OraclePassword**绑定属性。  
  
- 若要使用 Oracle E-business Suite 凭据进行连接，指定**ClientCredentialType**绑定属性作为**EBusiness**，然后指定 Oracle E-business Suite 中的凭据**用户名称**并**密码**上的文本框**安全**选项卡。您还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。  
  
  有关指定客户端凭据的详细信息，请参阅[适用于 Oracle E-business Suite 中配置单一登录凭据](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)。  
  
## <a name="using-windows-authentication"></a>使用 Windows 身份验证  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持 Windows 身份验证，同时将连接到 Oracle E-business Suite。 使用 Windows 身份验证，适配器客户端可以确定用户的标识基于 Windows 登录凭据，并且可以利用内置的 Windows 环境的安全性。 有关使用 Windows 身份验证连接到 Oracle E-business Suite 的信息，请参阅[连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
## <a name="see-also"></a>请参阅  
[了解用于 Oracle 电子商务花色 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)