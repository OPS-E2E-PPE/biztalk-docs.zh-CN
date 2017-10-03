---
title: "HTTPSolicitResponse |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59f5c2821af02fb87727a4096f4b6e586bfd5b4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="httpsolicitresponse"></a>HTTPSolicitResponse
HTTPSolicitResponse 示例演示如何创建 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]利用 ASP.NET 应用程序以帮助处理 orchestration 数据的业务流程。 在本示例中，业务流程利用请求/响应端口将消息发送到 ASP.NET 应用程序以及检索响应。 使用 HTTP 适配器，您可以在 BizTalk Server 业务流程和 ASP.NET 应用程序之间实现集成。 有关详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例包括通过以下步骤序列接收包含两个数字相乘的请求并满足该请求的 BizTalk Server 业务流程：  
  
1.  BizTalk Server 业务流程从特定文件夹检索 .xml 输入文件。  
  
2.  业务流程使用 HTTP 请求将文件中的 XML 转发到乘数 ASP.NET 应用程序。  
  
3.  乘数 ASP.NET 应用程序通过执行乘法并在 HTTP 响应中返回 XML 形式的结果，响应 HTTP 请求。  
  
4.  业务流程在 HTTP 响应中接收 XML 形式的结果，并将该结果写入特定文件夹中的 .xml 文件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*> \AdaptersUsage\HTTPSolicitResponse  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|HttpSolicitResponse.btproj、HttpSolicitResponse.sln|提供 BizTalk 项目的项目和源文件，该项目包含使用乘数 ASP.NET 应用程序、关联架构等的业务流程。|  
|HttpSolicitResponseBinding.xml|用于进行自动设置，如端口绑定。|  
|MultiplyRequest.xsd、MultiplyResponse.xsd|分别提供乘法请求和响应 XML 消息的架构。|  
|MultiplyTwoIntegers.odx|提供接收请求乘法运算的 .xml 文件，将请求转发到乘数 ASP.NET 应用程序，并将其响应写入文件的 BizTalk Server 业务流程。|  
|request_in.xml|示例输入文件。|  
|Setup.bat|生成并初始化本示例。|  
|在 \Multiplier 文件夹中：<br /><br /> Multiplier.aspx、 Multiplier.aspx.cs，Multiplier.sln|包含构成实现乘数服务的 ASP.NET 应用程序的文件，其中包括项目和解决方案文件、ASPX 文件以及 Microsoft Visual C# .NET 源文件等。|  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化本示例  
 使用以下过程可以生成并初始化 HTTPSolicitResponse 示例。  
  
> [!NOTE]
>  如果接收位置的名称包含任何大写字符，则本示例无法运行。  
  
#### <a name="to-build-and-initialize-the-sample"></a>生成并初始化示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \AdaptersUsage\HTTPSolicitResponse  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   为本示例创建输入和输出文件夹：  
  
         \<*示例路径*> \AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput  
  
         \<*示例路径*> \AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput  
  
    -   编译并配置本示例使用的 ASP.NET 应用程序。  
  
        > [!NOTE]
        >  在创建应用程序池在 IIS 管理器，设置**DefaultAppPool**到.NET Framework 版本**.Net Framework v4.0**。  
  
    -   编译并部署本示例中使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。  
  
    -   创建并绑定必需的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置和端口。  
  
        > [!NOTE]
        >  在创建并绑定端口时，本示例将显示以下警告：  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
    -   启用接收位置并启动发送端口。  
  
        > [!NOTE]
        >  本示例中的业务流程使用双向端口与 ASP.NET 应用程序进行 HTTP 交互。  
  
        > [!NOTE]
        >  在尝试运行本示例之前，应确认在生成和初始化过程中 BizTalk 未报告任何错误。  
  
        > [!NOTE]
        >  如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。 使用该密钥对可以对生成的程序集签名。  
  
        > [!NOTE]
        >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程可以运行 HTTPSolicitResponse 示例。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  将文件 request_in.xml 的副本粘贴到文件夹 HttpSolicitResponseInput 中。  
  
2.  查看在 HttpSolicitResponseOutput 文件夹中创建的 .xml 文件。 此 .xml 文件是根据消息 ID GUID 命名的。 此文件包含 XML 格式的乘法运算结果。  
  
    > [!NOTE]
    >  若要执行不同的乘法运算，可以更改输入文件中的操作数的值。  
  
## <a name="comments"></a>注释  
 可以调整本示例以与公开 HTTP 接口的不同外部系统进行通信。  
  
 文件 MultiplyRequest.xsd 和 MultiplyResponse.xsd 是为乘数 ASP.NET 应用程序定义输入和输出数据格式的 XML 架构。 业务流程使用这些文件定义请求和响应消息类型。  
  
## <a name="see-also"></a>另请参阅  
 [HTTP 适配器示例](../core/http-adapter-samples.md)