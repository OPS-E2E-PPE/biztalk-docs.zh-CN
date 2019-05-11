---
title: 使用 SQL 适配器的安全编程 |Microsoft Docs
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
ms.openlocfilehash: 6241a6e36b15c7e7efc1a796662782f783676318
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368035"
---
# <a name="secure-programming-with-the-sql-adapter"></a>使用 SQL 适配器进行安全编程
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>在使用时如何保护凭据添加适配器服务参考 Visual Studio 插件？  
 当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，您可能需要提供用户名和密码的 SQL Server 数据库。 必须输入的凭据**安全**选项卡上**配置适配器**对话框。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不提供一个选项以指定的用户名和密码连接 URI 的一部分。 这可确保：  
  
- 凭据不会显示在**配置 URI**字段**添加适配器服务引用插件**有权访问您的计算机屏幕的任何人都可以读取的对话框。  
  
- 凭据不会出现在配置文件的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
  详细了解如何使用生成 WCF 客户端[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何为 SQL Server 数据库中输入用户名和密码，请参阅[获取 Visual Studio 中使用 SQL 适配器中的SQLServer操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>在代码中设置凭据的最佳做法是什么？  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供了**ClientCredentials**类来帮助你配置客户端通信对象，例如凭据**ChannelFactory**，用于验证自己身份的服务。 通过使用**ClientCredentials**类中，确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。  
  
 因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]托管在其使用方应用程序的进程，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。 但是，认为是很好的做法执行此操作。  
  
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
  
 下面的示例演示如何使用**ClientCredentials**类在 WCF 客户端上设置 SQL Server 数据库的凭据。  
  
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
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>如何提供更安全的数据交换跨进程边界？  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]托管进程的应用程序或服务，使用它。 因为适配器的宿主的进程中使用者，则无需使用者之间交换的消息上提供的安全性和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 但是，如果使用的应用程序或服务发送消息的跨进程边界到另一个服务或客户端包含敏感的数据库的信息，应采取措施来提供充分的保护环境中的此数据。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] 提供了多种用来帮助来保护客户端和服务之间发送的消息。 有关帮助来保护客户端和服务之间发送的消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 有关更多常规信息安全功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。
  
## <a name="see-also"></a>请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)