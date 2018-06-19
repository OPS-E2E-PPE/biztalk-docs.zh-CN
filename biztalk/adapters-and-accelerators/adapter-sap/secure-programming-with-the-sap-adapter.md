---
title: SAP 适配器使用的安全编程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, considerations when programming on the adapter
- security, secure data exchange
- security, setting credentials in code
ms.assetid: bd5da271-90f1-4a64-9138-a51048a16648
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2be84abdc7b645d9b2aaeea87e5ccabf0075e76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218021"
---
# <a name="secure-programming-with-the-sap-adapter"></a>SAP 适配器使用的安全编程
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>当我使用时如何保护凭据添加适配器服务引用 Visual Studio 插件？  
 当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，必须提供用户名和密码 SAP 系统。 你应当只做这从**安全**选项卡上**配置适配器**对话框。 通过输入 SAP 凭据从**安全**选项卡而不是直接插入**Uri**字段中，你请确保满足以下：  
  
-   凭据将不会显示在**Uri**字段[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]计算机屏幕访问任何人都可以读取对话框。  
  
-   凭据不会出现在配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
 有关如何通过使用生成 WCF 客户端的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何的 SAP 系统输入用户名和密码，请参阅[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>在代码中设置凭据的最佳实践有哪些？  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供**ClientCredentials**类来帮助你配置的客户端通信对象，如凭据**ChannelFactory**，用于验证自己身份的服务。 通过使用**ClientCredentials**类，则确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。  
  
 因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]承载进程内使用其使用方应用程序，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。 它，但是，考虑这样做的好办法。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]鼓励使用**ClientCredentials**类通过**AcceptCredentialsInUri**绑定属性。 此属性指定的用户名和密码连接 URI 中的 SAP 系统是否将接受该适配器。 **AcceptCredentialsInUri**默认为**false**，这意味着，如果连接 URI 包含凭据，该适配器将引发异常。 你可以设置**AcceptCredentialsInUri**到**true**连接 URI 中提供凭据。 事实上，你必须执行此操作在某些情况下;例如，当指定连接 URI 的服务主机终结点或**IReplyChannel**在入站方案中。  
  
 下面的示例演示如何使用**ClientCredentials**类来设置在 WCF 客户端上的 SAP 系统的凭据。  
  
```  
SAPBinding binding = new SAPBinding();  
  
// Set endpoint address  
EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
// Create client and set credentials  
RfcClient rfcClient = new RfcClient(binding, endpointAddress);  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>我如何是否能提供更安全的数据交换的跨进程边界？  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]托管进程的应用程序或服务使用它。 由于托管适配器在进程与使用者，就无需使用者之间交换的消息提供安全和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 但是，如果使用的应用程序或服务发送包含敏感的数据库信息跨进程边界到另一个服务或客户端的消息，你应采取措施以提供足够保护你的环境中的此数据。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供用于帮助客户端和服务之间发送的安全消息的许多选项。 有关帮助客户端和服务之间发送的安全消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 有关安全性的更多常规信息功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。  
  
## <a name="see-also"></a>另请参阅  
[最佳做法来保护 SAP 适配器](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[保护你的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   