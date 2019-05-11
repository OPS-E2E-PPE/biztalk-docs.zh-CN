---
title: 为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fa7d8c0-8ee4-41e7-9394-d22e87e09391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a5ff4da00e0ba5c5012b6b13eb8bc5748584f91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369422"
---
# <a name="generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts"></a>为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定
可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]针对所选操作对 SQL Server 项目生成 WCF 客户端类。 此外可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开 ServiceModel Metadata Utility Tool 通过标准的 Microsoft Windows 界面的功能。 它还提供浏览和搜索功能，使用 svcutil.exe 工具中，未提供，并生成一个基于连接到 SQL Server 数据库时选择的绑定属性的配置文件。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成 WCF 客户端类添加适配器服务引用插件  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)以连接到 SQL Server 和浏览和搜索操作。 若要创建你选择的操作的 WCF 客户端类，务必**客户端 （出站操作）** 从所选**选择协定类型**下拉列表。 （这是默认值）。  
  
3. 选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
- **WCF 客户端代码文件**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。 首次运行[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，它将生成此文件，其默认名称**SQLAdapterBindingClient.cs**。 如果再次运行，将调用的下一个文件，它将生成**SQLAdapterBindingClient1.cs**。  数字后缀将增加 1 为您生成每个新文件。  您还可以更改默认前缀**SQLBinding**通过输入中的不同前缀**文件名前缀**字段[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]选择前**确定**到生成的文件。  
  
- **App.config**。此文件包含的绑定配置和客户端终结点配置的基于配置的连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的 WCF 服务协定添加适配器服务引用插件  
 如轮询 SQL Server 数据库或从数据库中接收通知的入站操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行客户端应用程序 （如果轮询） 指定的查询或查询注册 （中的情况下的 SQL Server通知）。 在这两种情况下，适配器发送入站的消息到使用从 SQL Server 数据库中。 在这种情况下，使用方应用程序充当服务和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]充当客户端。 因此，必须实现 WCF 服务可以接收来自适配器的入站的操作。 若要执行此操作，应使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]来生成表示为适配器提供的入站操作的服务约定的.NET 接口。 此.NET 接口也被称为 WCF 服务约定。 然后实现此接口可创建的 WCF 服务的可用于接收入站的操作。  
  
 执行以下步骤以使用生成的 WCF 服务协定[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>若要生成 WCF 服务协定的入站操作  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[连接到 Visual Studio 使用添加适配器服务引用插件中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md)来连接到 SQL Server 数据库。  
  
   > [!IMPORTANT]
   >  如果要生成的 WCF 服务协定**TypedPolling**入站的操作，必须指定**InboundID**连接 URI 的一部分并**PollingStatement**绑定属性。  
  
3. 已连接到 SQL Server 数据库后，选择**服务 （入站操作）** 从**选择协定类型**下拉列表。  
  
4. 在**选择一个类别**框中，单击根节点 (**/**)，选择从的入站的操作**可用类别和操作**框中，然后单击**添加**。  
  
5. 若要生成入站操作的 WCF 服务协定，请单击**确定**。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
- **SqlAdapterBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口） 和入站操作的帮助器代码。  
  
- **SqlAdapterBindingService.cs**. 此文件包含实现 SqlAdapterBindingInterface.cs 中定义的接口的类。 可实现业务逻辑处理入站操作返回的记录。  
  
- **App.config**。此文件包含的绑定配置、 终结点行为，以及基于配置的绑定和连接时所做的选择的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>使用 svcutil.exe 生成 WCF 客户端类  
 可以使用 svcutil.exe 为你的应用程序生成 WCF 客户端类。 必须配置 svcutil.exe 与其一起使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 Svcutil.exe 生成 WCF 客户端类中包含的默认文件名的输出文件**output.cs**。 您必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。 有关 svcutil.exe 的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)