---
title: "生成 WCF 客户端或 WCF 服务协定的 Oracle 数据库解决方案项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model programming, creating a proxy
- how to, create a proxy
- creating a proxy
- proxy programming, creating a proxy
ms.assetid: 3e832ae9-e253-4476-9f25-8cf0de12f469
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e729adec26aca98df80ecc7917ab0558faa6632e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-database-solution-artifacts"></a>生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定
你可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或目标的 Oracle 数据库项目上的所选操作的 WCF 服务协定 （接口）。 你还可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务协定;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开通过标准的 Microsoft Windows 界面 ServiceModel 元数据实用工具的功能。 它还提供了使用 svcutil.exe 工具中，未提供的浏览和搜索功能并生成基于你选择在连接到 Oracle 数据库时的绑定属性的配置文件。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的客户端类添加插件的适配器服务引用  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[检索用于 Oracle 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)连接到 Oracle 数据库和浏览和搜索操作。 若要创建的操作，你选择一个 WCF 客户端类，请确保**客户端 （出站操作）**从选择**选择协定类型**（这是默认值） 的下拉列表。  
  
3.  选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
-   **OracleDBBindingClient.cs**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。  
  
-   **App.config**。此文件包含的绑定配置和客户端终结点配置。 这些配置基于配置的绑定和连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的 WCF 服务协定添加插件的适配器服务引用  
 适配器公开启用 Oracle 数据库，以将消息发送到适配器客户端的入站的操作。 对于这类操作，则必须生成的 WCF 服务协定。 例如，适配器公开一个入站的 POLLINGSTMT 操作以轮询 Oracle 数据库。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行由指定的查询**PollingStatement**绑定属性，并将结果设置为在 POLLINGSTMT 消息使用方应用程序。 在这种情况下，消费应用程序充当服务和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]充当客户端。 因此，必须实现的 WCF 服务，可以从适配器接收 POLLINGSTMT 操作。 若要执行此操作，请使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成.NET 接口表示 POLLINGSTMT 操作的适配器显示的服务协定。 此.NET 接口也被称为 WCF 服务协定。 然后，则实现此接口可创建可用于接收 POLLINGSTMT 操作的 WCF 服务。  
  
 本部分提供有关如何生成 WCF 服务协定使用的信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]为公开的适配器的入站操作。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>若要生成 WCF 服务协定的入站操作  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[检索用于 Oracle 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)来连接到 Oracle 数据库。 有几个绑定属性和一个 URI 属性，你可能想要设置连接到 Oracle 数据库入站操作时。 例如，对于入站的轮询操作 (**POLLINGSTMT**)，必须指定**PollingStatement**绑定属性时配置到 Oracle 数据库的连接。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此属性中指定的 SQL SELECT 语句来生成表示 POLLINGSTMT 操作返回的结果集的类。  
  
3.  你已连接到 Oracle 数据库后，选择**服务 （入站操作）**从**选择协定类型**下拉列表。  
  
4.  在**选择类别**框中，单击根节点 (**/**)，并浏览到你要为其生成服务协定的操作。 例如，对于轮询操作中，选择**POLLINGSTMT**从**可用类别和操作**框中，并依次**添加**。  
  
5.  若要生成 POLLINGSTMT 操作的 WCF 服务协定，请单击**确定**。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
-   **OracleDBBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口） 和 POLLINGSTMT 操作的帮助器代码。  
  
-   **OracleDBBindingService.cs**。 此文件包含实现 OracleDBBindingInterface.cs 中定义的接口的类。 你可以实现业务逻辑处理此类中的 POLLINGSTMT 方法中的轮询查询所返回的记录。  
  
-   **App.config**。此文件包含的绑定配置、 终结点行为和基于你所做的选择时配置的绑定和连接的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>使用 svcutil.exe 生成 WCF 客户端类或 WCF 服务协定  
 要为你的应用程序生成 WCF 客户端类或 WCF 服务接口，可以使用 svcutil.exe。 你必须配置 svcutil.exe 以将它与[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关详细信息，有关配置和使用与 svcutil.exe [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[ServiceModel 元数据实用工具使用 BizTalk 适配器将用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)。  
  
 Svcutil.exe 生成输出文件中的 WCF 客户端类或 WCF 服务协定。 默认文件名称为 output.cs。 你必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [在使用 WCF 服务模型的 SQL 中执行基本的插入、 更新、 删除和选择操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model.md)