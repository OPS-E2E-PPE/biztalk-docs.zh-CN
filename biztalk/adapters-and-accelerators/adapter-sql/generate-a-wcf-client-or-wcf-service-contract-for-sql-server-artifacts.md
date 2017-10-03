---
title: "为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fa7d8c0-8ee4-41e7-9394-d22e87e09391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f961c3648e153847f5ac259c9902da5589b1486d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts"></a>为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定
你可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类目标的 SQL Server 项目上的所选操作。 此外可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开通过标准的 Microsoft Windows 界面 ServiceModel 元数据实用工具的功能。 它还提供浏览和搜索功能，使用 svcutil.exe 工具中，未提供，并生成基于你选择在连接到 SQL Server 数据库时的绑定属性的配置文件。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成 WCF 客户端类添加插件的适配器服务引用  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[为使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)能够连接到 SQL Server，并浏览和搜索操作。 若要创建的操作，你选择一个 WCF 客户端类，请确保**客户端 （出站操作）**从选择**选择协定类型**下拉列表。 （这是默认值）。  
  
3.  选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
-   **WCF 客户端代码文件**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。 首次运行[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，它将生成此文件具有默认名称**SQLAdapterBindingClient.cs**。 如果再次运行，将调用它生成的下一个文件**SQLAdapterBindingClient1.cs**。  数字后缀将增加 1 为你生成每个新文件。  你还可以更改默认的前缀**SQLBinding**通过输入在不同的前缀**文件名前缀**字段[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]之前选择**确定**到生成文件。  
  
-   **App.config**。此文件包含的绑定配置和客户端终结点配置的基于配置的连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的 WCF 服务协定添加插件的适配器服务引用  
 实现轮询 SQL Server 数据库或从数据库中，接收通知等的入站操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行客户端应用程序 （如果轮询） 所指定的查询或查询注册 （中的情况下的 SQL Server通知）。 在这两种情况下，适配器发送入站的消息到使用从 SQL Server 数据库中。 在这种情况下，消费应用程序充当服务和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]充当客户端。 因此，必须实现的 WCF 服务，可以从适配器接收入站的操作。 若要执行此操作，请使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成.NET 接口表示的适配器的入站操作显示的服务协定。 此.NET 接口也被称为 WCF 服务协定。 然后，则实现此接口可创建可用于接收入站的操作的 WCF 服务。  
  
 执行以下步骤以使用生成的 WCF 服务协定[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>若要生成 WCF 服务协定的入站操作  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[连接到 Visual Studio 使用添加适配器服务引用插件中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md)来连接到 SQL Server 数据库。  
  
    > [!IMPORTANT]
    >  如果正在生成 WCF 服务约定以**TypedPolling**入站的操作，你必须指定**InboundID**作为连接 URI 的一部分和**PollingStatement**绑定属性。  
  
3.  你已连接到 SQL Server 数据库后，选择**服务 （入站操作）**从**选择协定类型**下拉列表。  
  
4.  在**选择类别**框中，单击根节点 (**/**)，选择从入站的操作**可用类别和操作**框中，然后单击**添加**。  
  
5.  若要生成入站操作的 WCF 服务协定，请单击**确定**。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
-   **SqlAdapterBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口） 和入站操作的帮助器代码。  
  
-   **SqlAdapterBindingService.cs**。 此文件包含实现 SqlAdapterBindingInterface.cs 中定义的接口的类。 你可以实现业务逻辑处理入站操作返回的记录。  
  
-   **app.config**。此文件包含的绑定配置、 终结点行为和基于你所做的选择时配置的绑定和连接的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>使用 svcutil.exe 生成 WCF 客户端类  
 要为你的应用程序生成 WCF 客户端类，可以使用 svcutil.exe。 你必须配置 svcutil.exe 以将它与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 Svcutil.exe 在默认的文件名的输出文件在生成 WCF 客户端类**output.cs**。 你必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。 Svcutil.exe 有关的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)