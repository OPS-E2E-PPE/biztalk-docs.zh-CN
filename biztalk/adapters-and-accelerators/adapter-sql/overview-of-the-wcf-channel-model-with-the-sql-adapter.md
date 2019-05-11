---
title: 与 SQL 适配器的 WCF 通道模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e5f77c-c922-4039-92c7-38d2b7638459
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85557014b9df46bf939e23894a8e6453c9580c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368579"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sql-adapter"></a>与 SQL 适配器的 WCF 通道模型概述
若要在调用操作[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，你的代码可用作 WCF 客户端，并将出站操作发送到适配器。 在 WCF 通道模型中，你的代码的通道上发送请求消息来调用在适配器上的操作。  
  
 若要接收基于轮询的数据更改消息使用的适配器，您的代码可用作 WCF 服务，并接收入站**轮询**， **TypedPolling**，或**通知**来自适配器的操作。 换而言之，你的代码用于这些操作的请求消息从适配器接收通过通道。  
  
 在本部分中的主题提供使用概述[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 WCF 通道模型。  
  
## <a name="wcf-channel-model-overview"></a>WCF 通道模型概述  
 通过交换 SOAP 消息，客户端和服务进行通信。 WCF 通道模型是此消息交换的低级别抽象。 它提供了接口和类型，您可以发送和接收消息，通过使用分层的协议堆栈，称为通道堆栈。 堆栈中的每个层组成的一个通道，并且从 WCF 绑定创建的每个通道。 在最低层是传输通道。 传输通道可实现服务和客户端之间的基础传输机制并显示每条消息到较高的层 （和最终使用方应用程序），并且**System.ServiceModel.Message**。 WCF**消息**类是抽象的 SOAP 消息。 WCF 提供了多个通道接口，名为的基本 SOAP 消息交换模式进行建模，例如请求-答复或单向通道形状。 WCF 传输绑定提供的实现的一个或更高版本层的详细通道形状可用于发送和接收消息。 有关 WCF 通道模型的详细信息，请参阅[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是公开为 WCF 服务的 SQL Server 数据库的 WCF 自定义传输绑定。  
  
## <a name="supported-channel-shapes-for-the-sql-server-adapter"></a>支持的 SQL Server 适配器的通道形状  
 适配器实现以下 WCF 通道形状：  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**接口实现请求-答复消息交换的客户端。 可以使用**IRequestChannel**若要执行你想要使用响应的操作，例如若要执行 SELECT 查询的表。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 此形状实现单向消息交换的客户端。 可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如调用没有返回参数的过程。  
  
  > [!IMPORTANT]
  >  适配器对 SQL Server 客户端的所有基础的调用是同步的。 这包括 SQL Server 客户端通过调用操作的结果调用**IOutputChannel**。 当你使用**IOutputChannel**，适配器将放弃从 SQL Server 客户端收到的响应。  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 此形状实现单向消息交换在服务端。 您使用**IInputChannel**接收消息的入站操作，如**轮询**或**通知**，从适配器。  
  
  像任何 WCF 绑定，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用工厂模式来提供到应用程序代码的通道。 您使用**Microsoft.Adapters.SQLBinding**对象创建的实例：  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用来调用在适配器上的请求-响应操作。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用来调用在适配器上的单向操作。  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>** 提供**IInputChannel**通道可用于接收消息的入站操作，如**轮询**或**通知**，从适配器。  
  
### <a name="creating-messages-for-the-sql-server-database-adapter-in-the-wcf-channel-model"></a>为 SQL Server 数据库适配器的 WCF 通道模型中创建消息  
 在 WCF **System.ServiceModel.Channels.Message**类提供了内存中 SOAP 消息的表示形式。 您创建**消息**实例通过调用静态**Message.Create**方法。  
  
 有两个重要部分，你必须指定当您创建的 SOAP 消息**消息**实例将发送到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 消息操作是一个字符串，是 SOAP 消息标头的一部分。 消息操作标识应在数据库调用的操作。 下面的示例演示指定要调用的 Employee 表上的选择操作的消息操作： `TableOp/Select/dbo/Employee`。  
  
- 消息正文包含操作的参数数据。 消息正文组成对应于所需的消息架构的格式正确的 XML[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]对请求的操作。 以下消息正文指定针对 Employee 表的选择操作 (选择 * 从员工 WHERE Employee_ID = 10001)。  
  
  ```  
  <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Columns>*</Columns>  
    <Query>where Employee_ID=10001</Query>  
  </Select>  
  
  ```  
  
  璝惠[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]消息架构和消息操作的操作，请参见[消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。  
  
  这**创建**方法被重载并提供许多不同的提供消息正文选项。 下面的代码演示如何创建**消息**通过使用实例**XmlReader**提供消息正文。 在此代码中，从文件中读取消息正文。  
  
```  
XmlReader readerIn = XmlReader.Create("SelectInput.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "TableOp/Select/dbo/Employee",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  必须提供中的消息操作，你**消息**实例。 这通常是何时**消息**创建实例。  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)