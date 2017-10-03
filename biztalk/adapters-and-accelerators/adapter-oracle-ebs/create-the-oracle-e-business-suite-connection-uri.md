---
title: "创建 Oracle E-business Suite 连接 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91eb49fa-2a69-470b-b96d-dc3a6ffafef6
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3f6e3be6604e8786ff9481ab463f27a31bf1e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-oracle-e-business-suite-connection-uri"></a>创建 Oracle E-business Suite 连接 URI
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]连接 URI 包含适配器用于建立与 Oracle E-business Suite 和实质上是基础的 Oracle 数据库的连接的属性。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持连接到基础的 Oracle 数据库的两种方法： 使用 tnsnames.ora 和不使用 tnsnames.ora。 根据连接方法的类型，是也不同连接 URI 的格式。 本主题提供有关 Oracle 连接 URI 的信息，并还提供了指向其他主题的说明如何在不同的编程方案中指定一个 URI。  
  
 Oracle E-business Suite 是，接口的基础的 Oracle 数据库，并划分为不同的应用程序，如财务和 HR，基于在组织内不同的需求的应用程序层。 每个应用程序提供了各种"形式"，使用户能够输入到基础的 Oracle 数据库的数据。 对这些窗体的访问权限受到将用户与应用程序上下文，它包含用户所属的组织 ID 与用户和 Oracle E-business Suite 应用程序的名称关联的"责任"关联的用户想要调用。 对 Oracle E-business Suite 项目执行操作时，即使该适配器直接连接到基础数据库，并且不使用窗体与 Oracle E-business Suite 进行沟通，设置应用程序上下文是强制性。 因此，为了连接到 Oracle E-business suite，和基础 Oracle 数据库，使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你必须：  
  
-   指定要连接到 Oracle E-business Suite 和基础的 Oracle 数据库 URI 的连接。 时建立的连接，你可以选择为 Oracle E-business Suite 或基础的 Oracle 数据库中指定的凭据。  
  
-   为用户设置的应用程序上下文。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开接受凭据并承担相应责任某些绑定属性。 有关这些绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 本部分提供有关如何指定要连接到基础数据库使用 tnsnames.ora 和不使用 tnsnames.ora URI 的连接信息。 它还提供有关使用连接 URI 以连接到 Oracle E-business Suite 的信息。  
  
## <a name="connect-using-tnsnamesora"></a>使用 tnsnames.ora 连接  
  
> [!IMPORTANT]
>  -   有关此方法，你必须安装了适配器客户端，在计算机上的 tnsnames.ora 文件中添加 net 服务名称条目。 有关 net 服务名称条目的信息，请参阅[配置 Oracle 客户端为 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)。  
> -   由于 Oracle 客户端存在的限制， **DataSourceName**连接 URI 中的参数 （net 服务名称） 不能包含超过 39 个字符，如果你在事务中执行操作。 因此，请确保为指定的值**DataSourceName**参数是否小于或等于 39 个字符如果你将在事务中执行操作。  
  
 连接 URI 可包含用于标识你想要连接 Oracle E-business Suite 服务 Oracle net 服务名称。 Oracle 客户端根据你配置它以使用的 Oracle 命名方法的层次结构中解析到适用于 Oracle E-business Suite 服务，连接信息连接 URI 中提供的 Oracle net 服务名称。 一种通用的命名方法称为本地命名。 在本地命名 Oracle 客户端使用调用 tnsnames.ora 文件来解析 Oracle net 服务名称。  
  
 典型的终结点地址 URI 中的[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams`，其中：  
  
-   方案是方案名称。  
  
-   userauthparams 是终结点进行用户身份验证所需的参数名称 / 值集合。  
  
-   hostinfoparams 是建立与主机; 的连接所需的信息例如，net 服务名称。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  
  
```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]  
```  
  
 下表介绍了连接 URI 中包含的属性。  
  
|连接 URI 属性|类别|Description|  
|-----------------------------|--------------|-----------------|  
|[用户名]|userauthparams|要用于身份验证的用户名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立连接的 Oracle 客户端凭据类型的属性。 可能值**ClientCredentialType**绑定属性是**数据库**和**EBusiness**。 根据此绑定属性的值，则必须指定相关的凭据。 有关详细信息，请参阅[Oracle 凭据和连接 URI](#BKMK_OraCreds)。 **注意：**必须设置**AcceptCredentialsInUri**属性绑定到**true**在连接 URI 中指定用户名和密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的用户名连接到 Oracle E-business Suite 时的值的大小写。 用户名称传递给 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的用户名称的大小写或你想要输入用户名称包含特殊字符，你必须指定在双引号内的值。|  
|[PASSWORD]|userauthparams|要用于身份验证的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立连接的 Oracle 客户端凭据类型的属性。 如果**ClientCredentialType**属性设置为**数据库**，客户端必须指定 Oracle 数据库用户的密码。 如果**ClientCredentialType**属性设置为**EBusiness**，客户端必须指定 Oracle E-business Suite 用户的密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的密码时它连接到 Oracle E-business Suite 的值的大小写。 用户名称传递给 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。|  
|[NET_SERVICE_NAME]|hostinfoparams|在计算机上的 tnsnames.ora 文件中指定的网络服务名称其中[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]安装。 有关 net 服务名称和 tnsnames.ora 的信息，请参阅[配置 Oracle 客户端为 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)。|  
  
## <a name="connect-without-using-tnsnamesora"></a>连接而无需使用 tnsnames.ora  
  
> [!IMPORTANT]
>  -   有关此方法，你不需要在 tnsnames.ora 具有 net 服务名称条目。 此外，你甚至不必具有安装了适配器客户端计算机上的 tnsnames.ora 文件。  
> -   如果你在事务中执行操作，则不支持这种模式的连接。 这是因为 Oracle 客户端的限制。  
  
 典型的终结点地址 URI 中的[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams`，其中：  
  
-   方案是方案名称。  
  
-   userauthparams 是终结点进行用户身份验证所需的参数名称 / 值集合。  
  
-   hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称、 端口号，等等。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  
  
```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/[SERVICE_TYPE]   
```  
  
 下表介绍了连接 URI 中包含的属性。  
  
|连接 URI 属性|类别|Description|  
|-----------------------------|--------------|-----------------|  
|[用户名]|userauthparams|要用于身份验证的用户名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立连接的 Oracle 客户端凭据类型的属性。 可能值**ClientCredentialType**绑定属性是**数据库**和**EBusiness**。 根据此绑定属性的值，则必须指定相关的凭据。 有关详细信息，请参阅[Oracle 凭据和连接 URI](#BKMK_OraCreds)。 **注意：**必须设置**AcceptCredentialsInUri**属性绑定到**true**在连接 URI 中指定用户名和密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的用户名连接到 Oracle E-business Suite 时的值的大小写。 用户名称传递给 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的用户名称的大小写或你想要输入用户名称包含特殊字符，你必须指定在双引号内的值。|  
|[PASSWORD]|userauthparams|要用于身份验证的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**ClientCredentialType**绑定指定的客户端指定要建立连接的 Oracle 客户端凭据类型的属性。 如果**ClientCredentialType**属性设置为**数据库**，客户端必须指定 Oracle 数据库用户的密码。 如果**ClientCredentialType**属性设置为**EBusiness**，客户端必须指定 Oracle E-business Suite 用户的密码。 **注意：** [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的密码时它连接到 Oracle E-business Suite 的值的大小写。 用户名称传递给 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。|  
|[SERVER_NAME]|hostinfoparams|在其上运行 Oracle E-business Suite 的服务器的名称。 必须设置此项。|  
|[PORT_NUMBER]|hostinfoparams|Oracle Net 侦听器端口。 默认值 1521年中。|  
|[SERVICE_NAME]|hostinfoparams|Oracle 数据库服务名称。 必须设置此项。|  
|[SERVICE_TYPE]|hostinfoparams|Oracle 服务的类型。 可能的值为**专用**或**共享**。 专用的服务使用专用的服务器进程为只有一个用户进程提供服务。 共享的服务使用可以为多个用户进程提供服务的共享的服务器进程。 默认值是**专用**。|  
  
##  <a name="BKMK_OraCreds"></a>Oracle 凭据和连接 URI  
 默认情况下，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]连接 URI 中指定的 Oracle 凭据时引发异常。 这是因为这些凭据被表示为纯文本格式连接 URI，而这会带来安全风险。 你可以设置**AcceptCredentialsInUri**连接 URI 可以包含用于 Oracle 数据库的凭据是否将属性绑定到控件。 如果**AcceptCredentialsInUri**属性是**false**，这是默认设置，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]引发异常，如果连接 URI 包含 Oracle 凭据; 如果属性是**true**，不会引发异常。  
  
> [!IMPORTANT]
>  由于为纯文本字符串中传递凭据所带来安全风险，应避免在连接 URI 中指定 Oracle 数据库连接凭据。 有关如何更安全地提供 Oracle 数据库的凭据的详细信息，请参阅[保护 Oracle EBS 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)。  
  
 你还可以选择指定的数据库凭据或 Oracle E-business Suite 凭据建立到 Oracle E-business Suite 的连接。 适配器公开三个绑定属性，以启用此行为： **ClientCredentialType**， **OracleUserName**， **OraclePassword**。  
  
 可能值**ClientCredentialType**绑定属性是**数据库**和**EBusiness**。  
  
-   如果**ClientCredentialType**属性设置为**数据库**，客户端必须指定数据库凭据。  
  
-   如果**ClientCredentialType**属性设置为**EBusiness**，客户端必须指定 Oracle E-business Suite 凭据。 在这种情况下，适配器客户端还必须指定的数据库凭据**OracleUserName**和**OraclePassword**绑定属性。  
  
> [!IMPORTANT]
>  在方案中的适配器客户端在其中指定的数据库凭据以通过设置连接到 Oracle E-business Suite **ClientCredentialType**属性绑定到**数据库**，但调用 Oracle电子商务套件项目对于指定的值**OracleUserName**和**OraclePassword**绑定属性用来设置应用程序上下文。 设置应用程序上下文是必需的调用中 Oracle E-business Suite 的项目。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>在连接 URI 中使用保留的字符  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持指定的连接具有任何参数值的特殊字符的 URI。 连接参数值包含特殊字符，请确保执行下列任一操作：  
  
-   如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，你必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
-   如果你创建一个发送时指定的 URI，或接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
## <a name="using-the-connection-uri-to-connect-to-oracle-e-business-suite"></a>用于连接到 Oracle E-business Suite 连接 URI  
 以下是一个连接 URI 的示例为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 tnsnames.ora。  
  
```  
oracleebs://ADAPTER  
```  
  
 在此示例中，适配器是与 tnsnames.ora 中的目标 Oracle 数据库的服务名称和连接信息相关联的 net 服务名称。  
  
 以下是一个连接 URI 的示例为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]而无需使用 tnsnames.ora。  
  
```  
oracleebs://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated  
```  
  
 在此示例中，服务器名称是"yourOracleServer"和服务名称是"yourOracleDatabaseServiceName"。  
  
 有关如何建立与 Oracle E-business Suite 的连接信息时您：  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
-   配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 Oracle 客户端为 E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
 [将连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)  
 [创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)