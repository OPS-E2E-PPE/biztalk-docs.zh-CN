---
title: "安全使用 Oracle EBS 适配器编程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35b494f8-cb21-45c2-9bb4-097ba59ec52c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a51a163c12a14fc58bdcefc5ffe6aab7df6d9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-programming-with-the-oracle-ebs-adapter"></a>使用 Oracle EBS 适配器安全编程
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>当我使用时如何保护凭据添加适配器服务引用 Visual Studio 插件？  
 当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]要创建 WCF 客户端，但是您必须提供用户名和密码用于 Oracle E-business Suite。 你应当只做这从**安全**选项卡上**配置适配器**对话框。 通过输入 Oracle 凭据从**安全**选项卡而不是直接插入**配置 URI**字段中，你请确保满足以下：  
  
-   凭据将不会显示在**配置 URI**字段[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]计算机屏幕访问任何人都可以读取对话框。  
  
-   凭据不会出现在配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
 有关如何通过使用生成 WCF 客户端的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何为 Oracle E-business Suite 输入用户名和密码，请参阅[获取 Visual Studio中的OracleE-businessSuite操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>在代码中设置凭据的最佳实践有哪些？  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供**ClientCredentials**类来帮助你配置的客户端通信对象，如凭据**ChannelFactory**，用于验证自己身份的服务。 通过使用**ClientCredentials**类，则确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。  
  
 因为[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]承载进程内使用其使用方应用程序，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。 它，但是，考虑这样做的好办法。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]鼓励使用**ClientCredentials**类。 此属性指定适配器是否将接受的用户名和密码连接 URI 中的 Oracle 数据库。 **AcceptCredentialsInUri**默认为**false**，这意味着，如果连接 URI 包含凭据，该适配器将引发异常。 你可以设置**AcceptCredentialsInUri**到**true**中提供凭据连接 URI，如果需要在客户端应用程序。  
  
 下面的示例演示如何使用**凭据**属性来为 Oracle E-business Suite 上设置凭据**ChannelFactory**。  
  
```  
// Create binding and endpoint  
OracleEBSBinding binding = new OracleEBSBinding();  
EndpointAddress address = new EndpointAddress("oracleebs://ebs-instance");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 下面的示例演示如何使用**ClientCredentials**类设置的 Oracle E-business Suite 的 WCF 客户端的凭据。  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
ConcurrentPrograms_ARClient client =   
  new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>我如何是否能提供更安全的数据交换的跨进程边界？  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]托管进程的应用程序或服务使用它。 由于托管适配器在进程与使用者，就无需使用者之间交换的消息提供安全和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 但是，如果使用的应用程序或服务发送包含敏感的数据库信息跨进程边界到另一个服务或客户端的消息，你应采取措施以提供足够保护你的环境中的此数据。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供用于帮助客户端和服务之间发送的安全消息的许多选项。 有关帮助客户端和服务之间发送的安全消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅"保护服务和客户端"，网址[http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725)。 有关安全性的更多常规信息功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供，请参阅"Windows Communication Foundation 安全性"，网址[http://go.microsoft.com/fwlink/?LinkId=89726](http://go.microsoft.com/fwlink/?LinkId=89726)。  
  
## <a name="see-also"></a>另请参阅  
 [保护 Oracle EBS 应用程序](secure-your-oracle-ebs-applications.md)