---
title: 如何运行服务面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c33b914ecbb9f385e5546d100b7572b4b48b6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973811"
---
# <a name="how-to-run-the-service-oriented-solution"></a>如何运行面向服务的解决方案
以下步骤介绍了如何在单台计算机上运行和验证面向服务的解决方案。 启动付款跟踪模拟程序之后，可以使用 SOAP 或 MQSeries 传输发送请求（对于面向服务的解决方案的适配器和内联版本，需要使用不同的过程）。  
  
-   [将请求发送的 SOAP 传输使用客户端应用程序 （存根 （stub） 版本）](#step1)  
  
-   [发送请求使用客户端应用程序 （适配器版本）](#step3)  
  
-   [发送请求使用客户端应用程序 （内联版本）](#step5)  
  
##  <a name="step1"></a>将请求发送的 SOAP 传输使用客户端应用程序 （存根 （stub） 版本）  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a>可以使用客户端应用程序 （存根 （stub） 版本） 的 SOAP 传输的发送请求  
  
1.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，并再次运行 BTSScnSOSimpleClient.exe。  
  
2.  键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。  
  
3.  键入在任何 16 位数字**帐号**文本框。  
  
4.  选择**SOAP （WS 调用）** 和**存根 （stub)** 中**选择传输协议和参数**分组框。  
  
5.  键入以下 URL **URL**文本框中，例如：  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
8.  类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
9. 单击**获取我余额**。  
  
10. 响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。  
  
     ![运行的客户端应用程序的存根 （stub） 版本](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")  
  
##  <a name="step3"></a>发送请求使用客户端应用程序 （适配器版本）  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a>使用客户端应用程序发送请求（适配器版本）  
  
1.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug 和，然后运行以下命令以启动PaymentTracker 模拟器：  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*队列管理器名称* `> 5 [<` *通道定义*`>]`  
  
    > [!NOTE]
    >  如果不是远程 MQSeries 服务器，则通道定义为可选项。  
  
    -   使付款跟踪模拟程序处于运行状态。  
  
2.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，并再次运行 BTSScnSOSimpleClient.exe。  
  
3.  在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 SOAP 传输发送请求：  
  
    1.  键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。  
  
    2.  键入在任何 16 位数字**帐号**文本框。  
  
    3.  选择**SOAP （WS 调用）** 和**适配器**中**选择传输协议和参数**分组框。  
  
    4.  键入以下 URL **URL**文本框中，例如：  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    6.  类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    7.  单击**获取我余额**。  
  
    8.  响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。  
  
         ![运行的客户端应用程序的适配器版本](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")  
  
4.  在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 MQSeries 传输发送请求：  
  
    1.  键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。  
  
    2.  键入中的 16 位数字**帐号**文本框。  
  
    3.  选择**MQSeries**中**选择传输协议和参数**分组框。  
  
    4.  类型\<*队列管理器名称*\>中**队列管理器**文本框。 QM_\<*您的计算机名称*\>默认值为\<*队列管理器名称*\>。  
  
    5.  类型`AdapterSOAInputQueue`中**输入队列**文本框。  
  
    6.  类型`AdapterSOAOutputQueue`中**输出队列**文本框。  
  
    7.  类型\<*通道定义*\>中**通道定义**框。 S_\<*您的计算机名称*\>/TCP/\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。  
  
    8.  类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    9. 类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    10. 单击**获取我余额**。  
  
    11. 响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。  
  
         ![运行的客户端应用程序的适配器版本](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")  
  
##  <a name="step5"></a>发送请求使用客户端应用程序 （内联版本）  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a>发送请求，使用客户端应用程序 （内联版本）  
  
1.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug，并运行以下命令，以启动PaymentTracker 模拟器：  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*队列管理器名称* `> 5 [<` *通道定义*`>]`  
  
    > [!NOTE]
    >  如果不是远程 MQSeries 服务器，则通道定义为可选项。  
  
    > [!NOTE]
    >  如果付款跟踪模拟程序已运行，请跳过此步骤。  
  
    -   使付款跟踪模拟程序处于运行状态。  
  
2.  在**BizTalk Server 管理控制台**，展开**BTSScn.SO.CustomerService**，单击**接收位置**，右键单击**PaymentTrackingSystemOutputQueue**在右窗格中，然后单击**禁用**。  
  
    > [!NOTE]
    >  适配器版本和内联版本使用同一个 MQSeries 队列，即 LastPaymentsOutputQueue。 为避免这两个版本之间发生争用情况，请禁用适配器版本对 MQSeries 队列的接收位置侦听。  
  
3.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，并再次运行 BTSScnSOSimpleClient.exe。  
  
4.  在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 SOAP 传输发送请求：  
  
    1.  键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。  
  
    2.  键入在任何 16 位数字**帐号**文本框。  
  
    3.  选择**SOAP （WS 调用）** 和**内联**中**选择传输协议和参数**分组框。  
  
    4.  键入以下 URL **URL**文本框中，例如：  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    6.  类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    7.  单击**获取我余额**。  
  
    8.  响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。  
  
         ![运行的客户端应用程序的内联版本](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")  
  
5.  在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 MQSeries 传输发送请求：  
  
    1.  键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。  
  
    2.  键入中的 16 位数字**帐号**文本框。  
  
    3.  选择**MQSeries**中**选择传输协议和参数**分组框。  
  
    4.  类型\<*队列管理器名称*\>中**队列管理器**文本框。 QM_\<*您的计算机名称*\>默认值为\<*队列管理器名称*\>。  
  
    5.  类型`InlineSOAInputQueue`中**输入队列**文本框。  
  
    6.  类型`InlineSOAOutputQueue`中**输出队列**文本框。  
  
    7.  类型\<*通道定义*\>中**通道定义**框。 S_\<*您的计算机名称*\>/TCP/\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。  
  
    8.  类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    9. 类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    10. 单击**获取我余额**。  
  
    11. 响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。  
  
         ![运行的客户端应用程序的内联版本](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")  
  
## <a name="see-also"></a>另请参阅  
 [在安装之前面向服务解决方案](../core/before-installing-the-service-oriented-solution.md)   
 [如何安装服务的存根 （stub） 版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [如何安装内联和服务的适配器版本面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)