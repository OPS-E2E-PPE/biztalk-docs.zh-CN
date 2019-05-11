---
title: HTTPSolicitResponse | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67c5affc0714c17dab246e9f8de38644c1943d8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382871"
---
# <a name="httpsolicitresponse"></a>HTTPSolicitResponse
HTTPSolicitResponse 示例演示如何创建 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]利用 ASP.NET 应用程序以帮助处理业务流程数据的业务流程。 在此示例中，使业务流程使用的请求/响应端口将消息发送到 ASP.NET 应用程序，并检索响应。 通过使用 HTTP 适配器实现 BizTalk Server 业务流程和 ASP.NET 应用程序之间的集成。 有关详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例包含的 BizTalk Server 业务流程接收的请求，其中包含两个数字相乘，并满足该请求，使用以下步骤序列：  
  
1.  BizTalk Server 业务流程的特定文件夹检索.xml 输入的文件。  
  
2.  业务流程使用 HTTP 请求中文件的 XML 转发到乘数 ASP.NET 应用程序。  
  
3.  乘数 ASP.NET 应用程序通过执行乘法并在 HTTP 响应中以 XML 形式返回的结果来响应 HTTP 请求。  
  
4.  业务流程接收结果以 XML 形式在 HTTP 响应，并将该结果写入到特定文件夹中的.xml 文件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\AdaptersUsage\HTTPSolicitResponse  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|取消部署程序集，并将其从全局程序集缓存 (GAC) 中;删除发送和接收端口;根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|HttpSolicitResponse.btproj, HttpSolicitResponse.sln|提供包含使用乘数 ASP.NET 应用程序、 关联的架构等的业务流程的 BizTalk 项目的项目和源代码文件。|  
|HttpSolicitResponseBinding.xml|提供用于自动设置，如端口绑定。|  
|MultiplyRequest.xsd、 MultiplyResponse.xsd|分别提供架构乘法请求和响应 XML 消息。|  
|MultiplyTwoIntegers.odx|提供用于接收请求乘法运算，.xml 文件的 BizTalk Server 业务流程将请求转发到乘数 ASP.NET 应用程序，并将其响应文件写入。|  
|request_in.xml|示例输入的文件。|  
|Setup.bat|生成并初始化本示例。|  
|在 \Multiplier 文件夹中：<br /><br /> Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln|包含构成实现乘数服务，包括项目和解决方案文件、 ASPX 文件、 Microsoft Visual C#.NET 源文件等的 ASP.NET 应用程序的文件。|  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化示例  
 使用以下过程生成并初始化 HTTPSolicitResponse 示例。  
  
> [!NOTE]
>  如果接收位置的名称中包含的所有大写字符，此示例不起作用。  
  
#### <a name="to-build-and-initialize-the-sample"></a>若要生成并初始化示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\AdaptersUsage\HTTPSolicitResponse  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 创建此示例的输入和输出文件夹：  
  
      \<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput  
  
      \<*示例路径*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput  
  
   - 编译并配置此示例使用的 ASP.NET 应用程序。  
  
     > [!NOTE]
     >  在创建应用程序池在 IIS 管理器，设置**DefaultAppPool**到.NET Framework 版本 **.Net Framework v4.0**。  
  
   - 编译并部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此示例中使用的业务流程。  
  
   - 创建并绑定必需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置和端口。  
  
     > [!NOTE]
     >  此示例将显示以下警告时创建并绑定端口：  
  
     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
     > [!NOTE]
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
   - 启用该接收位置，并启动发送端口。  
  
     > [!NOTE]
     >  此示例中的业务流程进行 HTTP 交互与 ASP.NET 应用程序使用双向端口。  
  
     > [!NOTE]
     >  您应确认，BizTalk 未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
  
     > [!NOTE]
     >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
  
     > [!NOTE]
     >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行 HTTPSolicitResponse 示例。  
  
#### <a name="to-run-the-sample"></a>若要运行示例  
  
1.  将文件 request_in.xml 的副本粘贴到文件夹 httpsolicitresponseinput。  
  
2.  查看在 HttpSolicitResponseOutput 文件夹中创建的.xml 文件。 此.xml 文件的名称根据消息 ID GUID。 此文件包含 XML 格式的乘法运算结果。  
  
    > [!NOTE]
    >  你可以在要执行不同的乘法运算的输入文件中的操作数的值。  
  
## <a name="comments"></a>注释  
 您可以改写此示例与公开 HTTP 接口的不同外部系统进行通信。  
  
 文件 MultiplyRequest.xsd 和 MultiplyResponse.xsd 是定义的乘数 ASP.NET 应用程序的输入和输出数据格式的 XML 架构。 业务流程使用这些文件定义请求和响应消息类型。  
  
## <a name="see-also"></a>请参阅  
 [HTTP 适配器示例](../core/http-adapter-samples.md)