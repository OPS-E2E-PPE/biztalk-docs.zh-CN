---
title: 与 Oracle E-business Suite 适配器的 WCF 通道模型概述 |Microsoft 文档
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
ms.openlocfilehash: f5317099b1a576c9dd4e0b13593c16f4ef3a6831
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963251"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a>与 Oracle E-business Suite 适配器的 WCF 通道模型概述
若要在调用操作[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，你的代码充当 WCF 客户端，并将出站操作发送到适配器。 在 WCF 通道模型中，你的代码时，将调用在适配器上的操作通过在通道上发送请求消息。  
  
 若要调用等基于轮询的数据更改使用接收消息的入站的操作**轮询**操作提供的适配器，通过你的代码充当 WCF 服务，并且从适配器接收入站的操作。 换而言之，你的代码的请求消息从适配器接收通过通道。  
  
 本部分中的主题提供使用的概述[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 WCF 通道模型。  
  
## <a name="wcf-channel-model-overview"></a>WCF 通道模型概述  
 通过交换 SOAP 消息，客户端和服务进行通信。 WCF 通道模型是此消息交换的低级别抽象。 它提供接口和使您能够发送和接收消息，通过使用调用的通道堆栈的分层的协议堆栈的类型。 堆栈的每个层组成一个通道，并且每个通道创建从 WCF 绑定。 在最低层是传输通道。 传输通道可实现服务和客户端之间的底层传输机制并显示到较高层 （和最终使用方应用程序） 的每条消息，并且**System.ServiceModel.Message**。 WCF**消息**类是 SOAP 消息的抽象。 WCF 提供了多个通道接口，调用的基本 SOAP 消息交换模式进行建模，如请求-答复或单向通道形状。 WCF 传输绑定提供的实现的一个或多个更高版本上层的通道形状可以用于发送和接收消息。 有关 WCF 通道模型的详细信息，请参阅"通道模型概述"在[http://go.microsoft.com/fwlink/?LinkId=82614](http://go.microsoft.com/fwlink/?LinkId=82614)。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是公开 Oracle E-business Suite 项目作为一个 WCF 服务的 WCF 自定义传输绑定。  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a>为 Oracle E-business Suite 适配器支持通道形状  
 适配器实现以下的 WCF 通道形状：  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**接口实现请求-答复消息交换的客户端。 你可以使用**IRequestChannel**若要执行你想要使用响应的操作，例如，若要执行 SELECT 查询接口表上。  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 此形状实现单向消息交换的客户端。 你可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如，调用过程没有 OUT 参数。  
  
    > [!IMPORTANT]
    >  适配器对 Oracle 客户端的所有基础的调用是同步的。 这包括调用 Oracle 客户端通过调用操作的结果**IOutputChannel**。 当你使用**IOutputChannel**，适配器放弃从 Oracle 客户端收到的响应。  
  
-   **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。 此形状实现单向消息交换的服务端。 你使用**IInputChannel**从适配器接收入站的消息。  
  
 如任何 WCF 绑定，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用工厂模式提供到应用程序代码的通道。 你使用**Microsoft.Adapters.OracleEBSBinding**对象创建的实例：  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用于调用在适配器上的请求-响应操作。  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用于调用在适配器上的单向操作。  
  
-   **System.ServiceModel.IChannelListener\<IInputChannel\>** 提供**IInputChannel**可用于从适配器接收的入站的消息的通道。  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a>正在创建的 WCF 通道模型中的 Oracle 企业业务解决方案消息  
 在 WCF 中**System.ServiceModel.Channels.Message**类提供内存中的 SOAP 消息的表示形式。 你创建**消息**实例通过调用静态**Message.Create**方法。  
  
 有两个重要部分，你必须指定当创建的 SOAP 消息**消息**实例将发送到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
-   消息操作是一个字符串，它的 SOAP 消息标头的一部分。 消息操作标识应在 Oracle E-business Suite 调用的操作。 下面的示例演示指定要调用的消息操作**客户接口**下的并发程序**应收帐款**中 Oracle E-business Suite 应用程序： `ConcurrentPrograms/AR/RACUST`。  
  
-   消息正文包含操作的参数数据。 消息正文组成对应于预期的消息架构的格式正确的 XML[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]请求的操作。 以下的消息正文指定要调用的请求消息**客户接口**并发程序。  
  
    ```  
    <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
      <Description>Customer Interface Program</Description>  
      <StartTime></StartTime>  
      <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
      <ORG_ID>203</ORG_ID>  
    </RACUST>  
  
    ```  
  
 璝惠[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消息架构和消息操作的操作，请参阅[消息和消息架构用于 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。  
  
 **创建**方法重载方法，提供了多种不同的选项，用于提供消息正文。 下面的代码演示如何创建**消息**实例使用**XmlReader**提供消息正文。 在此代码中，从文件中读取消息正文。  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 其中，ConProgRequest.xml 包含请求消息。  
  
> [!IMPORTANT]
>  必须提供中的消息操作你**消息**实例。 这通常完成时**消息**创建实例。  
  
## <a name="see-also"></a>另请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)