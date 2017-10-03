---
title: "安全使用 Oracle 数据库适配器编程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials
- adapter, security considerations when programming on
- credentials, setting in code
- credentials, protecting
- security
ms.assetid: 06213c14-42b8-4d4a-b238-0aedbc27ab6a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dab171bf2eef81221e6dde15756dc7b011c7ee92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-programming-with-the-oracle-database-adapter"></a>Oracle 数据库适配器使用的安全编程
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>当我使用时如何保护凭据添加适配器服务引用 Visual Studio 插件？  
 当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，必须提供用户名和密码用于 Oracle 数据库。 你应当只做这从**安全**选项卡上**配置适配器**对话框。 通过输入 Oracle 凭据从**安全**选项卡而不是直接插入**配置 URI**字段中，你请确保满足以下：  
  
-   凭据将不会显示在**Uri**字段[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]计算机屏幕访问任何人都可以读取对话框。  
  
-   凭据不会出现在配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
 有关如何通过使用生成 WCF 客户端的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何输入 Oracle 数据库用户名和密码，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>在代码中设置凭据的最佳实践有哪些？  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供**ClientCredentials**类来帮助你配置的客户端通信对象，如凭据**ChannelFactory**，用于验证自己身份的服务。 通过使用**ClientCredentials**类，则确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。  
  
 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]承载进程内使用其使用方应用程序，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。 它，但是，考虑这样做的好办法。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]鼓励使用**ClientCredentials**类。 此属性指定适配器是否将接受的用户名和密码连接 URI 中的 Oracle 数据库。 **AcceptCredentialsInUri**默认为**false**，这意味着，如果连接 URI 包含凭据，该适配器将引发异常。 你可以设置**AcceptCredentialsInUri**到**true**连接 URI 中提供凭据。  
  
 下面的示例演示如何使用**凭据**属性上设置用于 Oracle 数据库的凭据**ChannelFactory**。  
  
```  
// Create binding and endpoint  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress endpointAddress = new EndpointAddress("oracleDB://Adapter");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the channel factory  
factory.Open();  
```  
  
 下面的示例演示如何使用**ClientCredentials**类来设置在 WCF 客户端上的 Oracle 数据库的凭据。  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
SQLEXECUTEClient sqlExecuteClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE");  
  
// Set user name and password  
sqlExecuteClient.ClientCredentials.UserName.UserName = "SCOTT";  
sqlExecuteClient.ClientCredentials.UserName.Password = "TIGER";  
  
// Open the client  
sqlExecuteClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>我如何是否能提供更安全的数据交换的跨进程边界？  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]托管进程的应用程序或服务使用它。 由于托管适配器在进程与使用者，就无需使用者之间交换的消息提供安全和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 但是，如果使用的应用程序或服务发送包含敏感的数据库信息跨进程边界到另一个服务或客户端的消息，你应采取措施以提供足够保护你的环境中的此数据。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供用于帮助客户端和服务之间发送的安全消息的许多选项。 有关帮助客户端和服务之间发送的安全消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 有关安全性的更多常规信息功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。 
  
## <a name="see-also"></a>另请参阅  
[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[最佳做法](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)