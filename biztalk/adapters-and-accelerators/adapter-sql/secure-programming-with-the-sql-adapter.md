---
title: 使用 SQL 适配器安全编程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44886b490ce63e8c34e1a5bdb41554c96a0873ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224021"
---
# <a name="secure-programming-with-the-sql-adapter"></a>使用 SQL 适配器安全编程
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>当我使用时如何保护凭据添加适配器服务引用 Visual Studio 插件？  
 当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，你可能需要提供用户名和密码的 SQL Server 数据库。 你必须输入凭据从**安全**选项卡上**配置适配器**对话框。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不提供某个选项以指定的用户名和密码作为连接 URI 的一部分。 这可确保以下项：  
  
-   凭据将不会显示在**配置 URI**字段**添加适配器服务引用插件**计算机屏幕访问任何人都可以读取对话框。  
  
-   凭据不会出现在配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
 有关如何通过使用生成 WCF 客户端的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何输入 SQL Server 数据库的用户名和密码，请参阅[为使用 SQL 适配器的VisualStudio中的SQLServer操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>在代码中设置凭据的最佳实践有哪些？  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供**ClientCredentials**类来帮助你配置的客户端通信对象，如凭据**ChannelFactory**，用于验证自己身份的服务。 通过使用**ClientCredentials**类，则确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。  
  
 因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]承载进程内使用其使用方应用程序，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。 它，但是，考虑这样做的好办法。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]需要使用**ClientCredentials**类以编程方式传递凭据。 **AcceptCredentialsInUri**绑定属性将被忽略[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以防止在 URI 中的传递凭据。  
  
 下面的示例演示如何使用**凭据**属性上设置 SQL Server 数据库的凭据**ChannelFactory**。  
  
```  
// Create binding and endpoint  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 下面的示例演示如何使用**ClientCredentials**类来在 WCF 客户端上设置 SQL Server 数据库的凭据。  
  
```  
// Initialize a new client for the SELECT operation on the Employee table   
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient(binding,address);  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>我如何是否能提供更安全的数据交换的跨进程边界？  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]托管进程的应用程序或服务使用它。 由于托管适配器在进程与使用者，就无需使用者之间交换的消息提供安全和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 但是，如果使用的应用程序或服务发送包含敏感的数据库信息跨进程边界到另一个服务或客户端的消息，你应采取措施以提供足够保护你的环境中的此数据。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供用于帮助客户端和服务之间发送的安全消息的许多选项。 有关帮助客户端和服务之间发送的安全消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 有关安全性的更多常规信息功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。
  
## <a name="see-also"></a>另请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)