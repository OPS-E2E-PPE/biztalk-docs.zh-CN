---
title: 生成 WCF 客户端或 WCF 服务协定用于 Oracle 数据库解决方案项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model programming, creating a proxy
- how to, create a proxy
- creating a proxy
- proxy programming, creating a proxy
ms.assetid: 3e832ae9-e253-4476-9f25-8cf0de12f469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e24b9efeab379d425d098c4323239bc5a943aad8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376614"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-database-solution-artifacts"></a>生成 WCF 客户端或 WCF 服务协定用于 Oracle 数据库解决方案项目
可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或针对 Oracle 数据库项目上的所选操作的 WCF 服务协定 （接口）。 您还可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类或 WCF 服务协定;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开 ServiceModel Metadata Utility Tool 通过标准的 Microsoft Windows 界面的功能。 它还提供浏览和搜索功能所不具备使用 svcutil.exe 工具中，并生成一个基于连接到 Oracle 数据库时选择的绑定属性的配置文件。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的客户端类添加适配器服务引用插件  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[检索用于 Oracle 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)以连接到 Oracle 数据库并浏览和搜索操作。 若要创建你选择的操作的 WCF 客户端类，务必**客户端 （出站操作）** 从所选**选择协定类型**下拉列表 （这是默认值）。  
  
3. 选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
- **OracleDBBindingClient.cs**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。  
  
- **App.config**。此文件包含的绑定配置和客户端终结点配置。 这些配置根据配置的绑定和连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的 WCF 服务协定添加适配器服务引用插件  
 该适配器公开启用 Oracle 数据库，以将消息发送到适配器客户端的入站的操作。 对于此类操作，则必须生成的 WCF 服务协定。 例如，适配器将公开一个入站的 POLLINGSTMT 操作来轮询 Oracle 数据库。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行指定的查询**PollingStatement**绑定属性，并将结果设置为 POLLINGSTMT 消息中使用的应用程序。 在此方案中，使用方应用程序充当服务和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]充当客户端。 因此，必须实现可以 POLLINGSTMT 操作接收来自适配器的 WCF 服务。 若要执行此操作，应使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]来生成表示适配器为 POLLINGSTMT 操作显示的服务约定的.NET 接口。 此.NET 接口也被称为 WCF 服务约定。 然后实现此接口可创建可用于接收 POLLINGSTMT 操作的 WCF 服务。  
  
 本部分介绍如何生成 WCF 服务协定使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开的适配器的入站操作。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>若要生成 WCF 服务协定的入站操作  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[检索用于 Oracle 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)来连接到 Oracle 数据库。 有多个绑定属性，你可能想要连接到 Oracle 数据库的入站操作时将设置一个 URI 属性。 例如，对于入站的轮询操作 (**POLLINGSTMT**)，则必须指定**PollingStatement**绑定属性时配置 Oracle 数据库的连接。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此属性中指定的 SQL SELECT 语句来生成表示 POLLINGSTMT 操作返回的结果集的类。  
  
3. 已连接到 Oracle 数据库后，选择**服务 （入站操作）** 从**选择协定类型**下拉列表。  
  
4. 在中**选择一个类别**框中，单击根节点 (**/**)，并浏览到你想要生成服务协定的操作。 例如，对于轮询操作中，选择**POLLINGSTMT**从**可用类别和操作**框中，然后依次**添加**。  
  
5. 若要生成 POLLINGSTMT 操作的 WCF 服务协定，请单击**确定**。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
- **OracleDBBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口），并为 POLLINGSTMT 操作的帮助器代码。  
  
- **OracleDBBindingService.cs**. 此文件包含实现 OracleDBBindingInterface.cs 中定义的接口的类。 可实现业务逻辑，用于处理此类中的 POLLINGSTMT 方法中的轮询查询返回的记录。  
  
- **App.config**。此文件包含的绑定配置、 终结点行为，以及基于配置的绑定和连接时所做的选择的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>使用 svcutil.exe 生成 WCF 客户端类或 WCF 服务约定  
 可以使用 svcutil.exe 为你的应用程序生成 WCF 客户端类或 WCF 服务接口。 必须配置 svcutil.exe 与其一起使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关详细信息，有关配置和使用与 svcutil.exe [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[对 Oracle 数据库的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)。  
  
 Svcutil.exe 生成输出文件中的 WCF 客户端类或 WCF 服务协定。 默认文件名称为 output.cs。 您必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [在使用 WCF 服务模型的 SQL 中执行基本的 Insert、 Update、 Delete 和 Select 操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model.md)