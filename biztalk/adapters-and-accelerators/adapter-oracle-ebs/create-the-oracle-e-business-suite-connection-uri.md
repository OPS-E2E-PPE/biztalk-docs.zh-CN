---
title: 创建 Oracle E-business Suite 连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91eb49fa-2a69-470b-b96d-dc3a6ffafef6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5673f0ee4a64b96157a403cc4abad6b867413b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375570"
---
# <a name="create-the-oracle-e-business-suite-connection-uri"></a>创建 Oracle E-business Suite 连接 URI
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]连接 URI 包含适配器用来建立与 Oracle E-business Suite 和实质上是基础的 Oracle 数据库的连接属性。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持连接到基础的 Oracle 数据库的两种方法： 使用 tnsnames.ora，无需使用 tnsnames.ora。 基于一种连接方法，连接 URI 的格式也不相同。 本主题提供有关 Oracle 连接 URI 的信息，并还提供了指向其他主题的解释如何在不同的编程方案中指定一个 URI。  

 Oracle E-business Suite 的应用程序层与基础 Oracle 数据库，并划分为不同的应用程序，例如财务和人力资源、 基于组织内不同的需求。 每个这些应用程序提供各种"forms"，使用户能够为基础的 Oracle 数据库输入数据。 对这些窗体的访问受到限制，将用户与包含属于用户的组织 ID"责任"用户和 Oracle E-business Suite 应用程序的名称与相关联的应用程序上下文关联的用户想要调用。 对 Oracle E-business Suite 项目执行操作时，即使适配器直接连接到基础数据库，并且不使用窗体以便与 Oracle E-business Suite，设置应用程序上下文是强制性。 因此，若要连接到 Oracle E-business suite 中，和基础 Oracle 数据库，使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，您必须：  

- 指定连接 URI 连接到 Oracle E-business Suite 和基础的 Oracle 数据库。 建立连接时，你可以选择用于 Oracle E-business Suite 或基础的 Oracle 数据库中指定的凭据。  

- 为用户设置应用程序上下文。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开接受的凭据，并负责特定绑定属性。 有关这些绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

  本部分提供有关如何指定连接 URI 连接到基础数据库使用 tnsnames.ora，无需使用 tnsnames.ora 的信息。 它还提供有关使用的连接 URI 以连接到 Oracle E-business Suite 的信息。  

## <a name="connect-using-tnsnamesora"></a>使用 tnsnames.ora 进行连接  

> [!IMPORTANT]
> - 对于这种方法，必须在计算机上的 tnsnames.ora 文件中添加 net 服务名称项，安装了适配器客户端。 有关 net 服务名称条目的信息，请参阅[E-business Suite 适配器将 Oracle 客户端配置](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)。  
>   -   由于 Oracle 客户端限制， **DataSourceName**连接 URI 中的参数 （net 服务名称） 不能包含超过 39 个字符，如果您在事务中执行的操作。 因此，请确保为指定的值**DataSourceName**参数是小于或等于 39 个字符如果您将在事务中执行的操作。  

 连接 URI 可以包含用来标识你想要连接的 Oracle E-business Suite 服务 Oracle 网络服务名称。 Oracle 客户端根据层次结构的 Oracle 配置为使用命名方法解析 URI 连接到 Oracle E-business Suite 服务的连接信息中提供的 Oracle net 服务名称。 一种通用的命名方法称为本地命名。 在本地命名 Oracle 客户端使用一个名为 tnsnames.ora 文件 Oracle net 服务名称解析。  

 典型的终结点地址中的 URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams`，其中：  

- 方案为方案名称。  

- userauthparams 是终结点进行用户身份验证所需的参数名称值集合。  

- hostinfoparams 是建立与主机; 的连接所需的信息例如，网络服务名称。  

  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  

```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]  
```  

 下表介绍了连接 URI 中包含的属性。  


| 连接 URI 属性 |    Category    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [USER_NAME]       | userauthparams | 要用于身份验证的用户名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立的连接的 Oracle 客户端凭据类型的属性。 可能的值**ClientCredentialType**绑定属性是**数据库**并**EBusiness**。 根据此绑定属性的值，则必须指定相关的凭据。 有关详细信息，请参阅[Oracle 凭据和连接 URI](#BKMK_OraCreds)。 **注意：** 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留到 Oracle E-business Suite 连接时输入的用户名的值的大小写。 用户名称传递给 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的用户名的大小写或你想要输入用户名称包含特殊字符，必须指定在双引号内的值。 |
|       [PASSWORD]        | userauthparams |                                                                                要用于身份验证的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立的连接的 Oracle 客户端凭据类型的属性。 如果**ClientCredentialType**属性设置为**数据库**，客户端必须指定 Oracle 数据库用户的密码。 如果**ClientCredentialType**属性设置为**EBusiness**，客户端必须指定 Oracle E-business Suite 用户的密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留到 Oracle E-business Suite 连接时输入的密码的值的大小写。 用户名称传递给 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。                                                                                |
|   [NET_SERVICE_NAME]    | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                    Net 服务名称在计算机上的 tnsnames.ora 文件中指定其中[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]安装。 有关 net 服务名称和 tnsnames.ora 的信息，请参阅[E-business Suite 适配器将 Oracle 客户端配置](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)。                                                                                                                                                                                                                                                                                                                                                                                                     |

## <a name="connect-without-using-tnsnamesora"></a>不使用 tnsnames.ora 连接  

> [!IMPORTANT]
> - 这种方法，您不需要的 net 服务名称条目 tnsnames.ora 中。 此外，您甚至不必具有 tnsnames.ora 文件的计算机上安装了适配器客户端。  
>   -   如果你在事务中执行操作，则不支持这种模式的连接。 这是由于 Oracle 客户端的限制。  

 典型的终结点地址中的 URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams`，其中：  

- 方案为方案名称。  

- userauthparams 是终结点进行用户身份验证所需的参数名称值集合。  

- hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称、 端口号，等等。  

  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  

```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/[SERVICE_TYPE]   
```  

 下表介绍了连接 URI 中包含的属性。  


| 连接 URI 属性 |    Category    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [USER_NAME]       | userauthparams | 要用于身份验证的用户名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立的连接的 Oracle 客户端凭据类型的属性。 可能的值**ClientCredentialType**绑定属性是**数据库**并**EBusiness**。 根据此绑定属性的值，则必须指定相关的凭据。 有关详细信息，请参阅[Oracle 凭据和连接 URI](#BKMK_OraCreds)。 **注意：** 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留到 Oracle E-business Suite 连接时输入的用户名的值的大小写。 用户名称传递给 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的用户名的大小写或你想要输入用户名称包含特殊字符，必须指定在双引号内的值。 |
|       [PASSWORD]        | userauthparams |                                                                                要用于身份验证的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立的连接的 Oracle 客户端凭据类型的属性。 如果**ClientCredentialType**属性设置为**数据库**，客户端必须指定 Oracle 数据库用户的密码。 如果**ClientCredentialType**属性设置为**EBusiness**，客户端必须指定 Oracle E-business Suite 用户的密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留到 Oracle E-business Suite 连接时输入的密码的值的大小写。 用户名称传递给 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。                                                                                |
|      [SERVER_NAME]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 在其运行 Oracle E-business Suite 的服务器的名称。 这是必需的。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|      [PORT_NUMBER]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 Oracle Net 侦听器端口。 默认值 1521年。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|     [SERVICE_NAME]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Oracle 数据库的服务名称。 这是必需的。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|     [SERVICE_TYPE]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Oracle 服务的类型。 可能的值为**专用**或**共享**。 专用的服务使用专用的服务器进程为只有一个用户进程提供服务。 共享的服务使用可以为多个用户进程提供服务的共享的服务器进程。 默认值是**专用**。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

##  <a name="BKMK_OraCreds"></a> Oracle 凭据和连接 URI  
 默认情况下，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接 URI 中指定的 Oracle 凭据时，将引发异常。 这是因为这些凭据被表示为纯文本形式的连接 URI，而这会带来安全风险。 可以设置**AcceptCredentialsInUri**属性绑定到控件是否连接 URI 可以包含用于 Oracle 数据库的凭据。 如果**AcceptCredentialsInUri**属性是**false**，这是默认设置，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]引发异常，如果连接 URI 中包含的 Oracle 凭据; 如果该属性为 **，则返回 true**，不会引发异常。  

> [!IMPORTANT]
>  由于通过在字符串中以明文形式传递凭据带来的安全风险，应避免在连接 URI 中指定 Oracle 数据库连接凭据。 有关如何更安全地提供 Oracle 数据库的凭据的详细信息，请参阅[保护 Oracle EBS 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)。  

 您还可以选择指定的数据库凭据或 Oracle E-business Suite 的凭据建立与 Oracle E-business Suite 的连接。 该适配器公开三个绑定属性，若要启用此行为：**ClientCredentialType**， **OracleUserName**， **OraclePassword**。  

 可能的值**ClientCredentialType**绑定属性是**数据库**并**EBusiness**。  

-   如果**ClientCredentialType**属性设置为**数据库**，客户端必须指定数据库凭据。  

-   如果**ClientCredentialType**属性设置为**EBusiness**，客户端必须指定 Oracle E-business Suite 凭据。 在这种情况下，适配器客户端还必须指定的数据库凭据**OracleUserName**并**OraclePassword**绑定属性。  

> [!IMPORTANT]
>  在适配器客户端在其中指定的数据库凭据，通过设置连接到 Oracle E-business Suite 的情况下**ClientCredentialType**属性绑定到**数据库**，但调用 Oracle电子商务套件项目，为指定值**OracleUserName**并**OraclePassword**绑定属性用于设置应用程序上下文。 设置应用程序上下文是必需的调用 Oracle E-business Suite 中的项目。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>在连接 URI 中使用保留的字符  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。 如果连接参数值包含特殊字符，请确保执行下列任一操作：  

- 如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

- 如果创建一个发送时指定的 URI 或接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

## <a name="using-the-connection-uri-to-connect-to-oracle-e-business-suite"></a>用于连接到 Oracle E-business Suite 连接 URI  
 以下是一个连接 URI 的示例为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 tnsnames.ora。  

```  
oracleebs://ADAPTER  
```  

 在此示例中，适配器是与目标 Oracle 数据库中 tnsnames.ora 的服务名称和连接信息相关联的 net 服务名称。  

 以下是一个连接 URI 的示例为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]而无需使用 tnsnames.ora。  

```  
oracleebs://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated  
```  

 在此示例中，服务器名称是"yourOracleServer"和服务名称是"yourOracleDatabaseServiceName"。  

 有关如何建立与 Oracle E-business Suite 的连接信息时您：  

- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  

- 配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  

## <a name="see-also"></a>请参阅  
 [配置 Oracle 客户端 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
 [连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)  
 [创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)