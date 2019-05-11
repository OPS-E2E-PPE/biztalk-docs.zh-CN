---
title: 使用 Oracle E-business Suite 适配器的 WCF 通道模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3afd2a97-5734-4c25-87a3-702d8461898b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54402a6ea9040d8821912214a6b206ed075628f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375124"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a>使用 Oracle E-business Suite 适配器的 WCF 通道模型概述
若要在调用操作[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，你的代码可用作 WCF 客户端，并将出站操作发送到适配器。 在 WCF 通道模型中，你的代码的通道上发送请求消息来调用在适配器上的操作。  
  
 若要调用入站的操作，例如接收基于轮询的数据更改消息使用**轮询**操作适配器提供的你的代码可用作 WCF 服务，并接收来自适配器的入站的操作。 换而言之，你的代码的请求消息从适配器接收通过通道。  
  
 在本部分中的主题提供使用概述[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 WCF 通道模型。  
  
## <a name="wcf-channel-model-overview"></a>WCF 通道模型概述  
 通过交换 SOAP 消息，客户端和服务进行通信。 WCF 通道模型是此消息交换的低级别抽象。 它提供了接口和类型，您可以发送和接收消息，通过使用分层的协议堆栈，称为通道堆栈。 堆栈中的每个层组成的一个通道，并且从 WCF 绑定创建的每个通道。 在最低层是传输通道。 传输通道可实现服务和客户端之间的基础传输机制并显示每条消息到较高的层 （和最终使用方应用程序），并且**System.ServiceModel.Message**。 WCF**消息**类是抽象的 SOAP 消息。 WCF 提供了多个通道接口，名为的基本 SOAP 消息交换模式进行建模，例如请求-答复或单向通道形状。 WCF 传输绑定提供的实现的一个或更高版本层的详细通道形状可用于发送和接收消息。 有关 WCF 通道模型的详细信息，请参阅"通道模型概述"处[ http://go.microsoft.com/fwlink/?LinkId=82614 ](http://go.microsoft.com/fwlink/?LinkId=82614)。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是公开 Oracle E-business Suite 项目作为 WCF 服务的 WCF 自定义传输绑定。  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a>支持 Oracle E-business Suite 适配器的通道形状  
 适配器实现以下 WCF 通道形状：  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**接口实现请求-答复消息交换的客户端。 可以使用**IRequestChannel**若要执行你想要使用响应的操作，例如若要执行 SELECT 查询在界面表。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 此形状实现单向消息交换的客户端。 可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如若要调用具有不带参数的过程。  
  
  > [!IMPORTANT]
  >  适配器对 Oracle 客户端的所有基础的调用是同步的。 这包括调用 Oracle 客户端通过调用操作的结果**IOutputChannel**。 当你使用**IOutputChannel**，适配器将放弃从 Oracle 客户端收到的响应。  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 此形状实现单向消息交换在服务端。 您使用**IInputChannel**以接收来自适配器的入站的消息。  
  
  像任何 WCF 绑定，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用工厂模式来提供到应用程序代码的通道。 您使用**Microsoft.Adapters.OracleEBSBinding**对象创建的实例：  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用来调用在适配器上的请求-响应操作。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用来调用在适配器上的单向操作。  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>** 提供**IInputChannel**可用于接收来自适配器的入站的消息的通道。  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a>正在创建 WCF 通道模型中的 Oracle 企业业务解决方案的消息  
 在 WCF **System.ServiceModel.Channels.Message**类提供了内存中 SOAP 消息的表示形式。 您创建**消息**实例通过调用静态**Message.Create**方法。  
  
 有两个重要部分，你必须指定当您创建的 SOAP 消息**消息**实例将发送到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
- 消息操作是一个字符串，是 SOAP 消息标头的一部分。 消息操作标识应在 Oracle E-business Suite 中调用的操作。 下面的示例演示指定要调用的消息操作**的客户界面**下的并发程序**应收帐款**Oracle E-business Suite 中应用程序： `ConcurrentPrograms/AR/RACUST`。  
  
- 消息正文包含操作的参数数据。 消息正文组成对应于所需的消息架构的格式正确的 XML[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]对请求的操作。 以下消息正文指定要调用的请求消息**的客户界面**并发程序。  
  
  ```  
  <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
    <Description>Customer Interface Program</Description>  
    <StartTime></StartTime>  
    <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
    <ORG_ID>203</ORG_ID>  
  </RACUST>  
  
  ```  
  
  璝惠[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消息架构和消息操作的操作，请参见[消息和消息架构用于 Oracle E-business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。  
  
  **创建**方法被重载并提供许多不同的提供消息正文选项。 下面的代码演示如何创建**消息**通过使用实例**XmlReader**提供消息正文。 在此代码中，从文件中读取消息正文。  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 其中，ConProgRequest.xml 包含请求消息。  
  
> [!IMPORTANT]
>  必须提供中的消息操作，你**消息**实例。 这通常是何时**消息**创建实例。  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)